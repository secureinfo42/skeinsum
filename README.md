# skeinsum

Script that compute SKEIN hashes, uses pyskein

## Synopsis

```
Usage:

  skeinsum [-a 224|256*|384|512] [-f hex|raw|b64] [-k hmac_key] [file]

Exemples:

  # Compute hash of file '/bin/ls'
  skeinsum /bin/ls

  # Compute hash of stdin with the content of '/bin/ls'
  cat /bin/ls|skeinsum

  # Compute hash of stdin (can use `heredoc`)
  skeinsum

  # Compute hash of string, with sha3_512 and display digest as base64
  printf 'myPasswordisVeryLongAndSecret'|skeinsum -a 512 -f b64 -k 'P@ssw0rd'

Note:

  # SHA3 default algo is 256 (bits)

  # To get raw data from digest:
  printf "$(cat /bin/ls|skeinsum -a 512 -f raw)"|xxd
```
