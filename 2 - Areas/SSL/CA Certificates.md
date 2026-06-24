## Basics
![[Certificate Chain - Root vs Intermediate]]

## Check a Certificate
```sh
openssl x509 -in root.crt    -noout -subject -issuer -dates -fingerprint -sha256
openssl x509 -in intermediate.crt   -noout -subject -issuer -dates -fingerprint -sha256
```

## See if the server has the certificate
Search the merged bundle:
```sh  
openssl crl2pkcs7 -nocrl -certfile /etc/ssl/certs/ca-certificates.crt \
  | openssl pkcs7 -print_certs \
  | awk 'BEGIN{cmd="openssl x509 -noout -subject -dates -fingerprint -sha256"}
         /-----BEGIN CERTIFICATE-----/{f=1; c=""}
         f{c=c $0 ORS}
         /-----END CERTIFICATE-----/{printf "%s", c | cmd; close(cmd); f=0}' \
  | paste - - - - \
  | grep -i '...the SHA456 fingerprint...'
```

Find out which file:
```sh
for f in /etc/ssl/certs/*.pem; do
  line=$(openssl x509 -in "$f" -noout -subject -issuer -dates -fingerprint -sha256 2>/dev/null | paste -sd'\t' -)
  printf '%s\t%s\n' "$f" "$line"
done | grep -i '...the SHA456 fingerprint...'
```

The symlinks should be created:
```sh
ls -l /etc/ssl/certs | grep -i sectigo
```

## See which root certificate is used
```sh
echo | openssl s_client -connect "api.equifax.ca":443 -servername "api.equifax.ca" -showcerts 2>/dev/null
```

## Add a certificate in the local CA dir
```sh
sudo cp root.crt  /usr/local/share/ca-certificates/some-meaningful-name-like-SectigoPublicServerAuthRootR46.crt
sudo cp intermediate.crt /usr/local/share/ca-certificates/some-meaningful-name-like-SectigoPublicServerAuthOVCAR36.crt

# Rebuild the trust store — APPENDS only, never removes existing certs
sudo update-ca-certificates

# Expect output like 2 added, 0 removed.
```

- Check [[#See if the server has the certificate]]
