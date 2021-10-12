#### Note replace mydomain.com with yourdomain.

- Install Openssl
- run `openssl` to open openssl shell
- run below command to generate the key
```bash
genrsa -out mydomain.com.key 2048
```
- generate certificate request
```bash
req -new -key mydomain.key -out mydomain.csr
```
- generate certificate with slef signed key
```bash
x509 -req -days 1825 -in mydomain.com.csr -signkey mydomain.com.key -out mydomain.crt
```
- exit openssl shell
- generate pem file
```bash
sudo cat mydomain.com.key mydomain.com.crt >> mydomain.com.pem
```
