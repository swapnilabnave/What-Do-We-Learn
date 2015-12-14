```sh
openssl s_client -connect www.example.com:443 < /dev/null 2>/dev/null | openssl x509 -text -in /dev/stdin | grep "Signature Algorithm"
```
--


```sh
(openssl x509 -noout -modulus -in site.crt | openssl md5; openssl rsa -noout -modulus -in site.key | openssl md5) | uniq
```