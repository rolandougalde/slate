# OpenSSL

## Convert standard PEM to PKCS12

> OpenSSL parameters

```shell
openssl pkcs12 -export -out domain.name.pfx -inkey domain.name.key -in domain.name.crt -certfile gd-g2_iisintermediates.domain.name.p7b
```
