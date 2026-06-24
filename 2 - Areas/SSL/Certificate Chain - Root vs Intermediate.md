CA stands for Certificate Authority.
Certificate chain or chain of trust: end-user > intermediate > root certificate
- A CA issues SSL/digital certificate
	- certify the ownership of a public key (CSR) which is generated locally
- Install SSL certificate issued from CA1, this is called the end-user certificate
	- This certificate basically vouches for the CSR whihc is a URL and its registration info
- CA1 uses a certificate issued by CA2 and CA2 uses a certificate issued by CA3
- CA2's certificate is an intermediate CA
- CA3 is a root CA and its certificate is directly embedded in the web browser and is called root certificate since its CA is trusted by the browser
