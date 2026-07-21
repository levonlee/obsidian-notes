## Start a session
```sh
claude --bg --model opus --effort xhigh --permission-mode auto "fix the lint errors"
claude --bg --model fable --effort xhigh --permission-mode auto "fix the lint errors"
claude --bg --model sonnet --effort medium --permission-mode auto "fix the lint errors"
```

```sh
claude --bg --model opus --effort xhigh --permission-mode auto "$(cat <<'EOF'
line 1.
line 2. You can use `backticks`
EOF
)"
```