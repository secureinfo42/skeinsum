# skeinsum

Script that compute SKEIN hashes, uses pyskein

## Synopsis

```

Usage:

  skeinsum [-a 224|256*|384|512] [-n digests_bits] [-f hex|raw|b64] [-k hmac_key] [file]

Exemples:

  # Compute hash of file '/bin/ls'
  skeinsum /bin/ls

  # Compute hash of stdin with the content of '/bin/ls'
  cat /bin/ls|skeinsum

  # Compute hash of stdin (can use `heredoc`)
  skeinsum

  # Compute hash of stdin skein-512-384 and display digest as base64
  echo -n 'myPasswordisVeryLongAndSecret'|skeinsum -a 512 -f b64 -k 'P@ssw0rd' -n 384

Note:

  # SKEIN default algo is 1024 (bits), defaults digests_bits is 1024.

  # To get raw data from digest:
  echo -n "$(cat /bin/ls|skeinsum -n 512 -f raw)"|xxd


```
