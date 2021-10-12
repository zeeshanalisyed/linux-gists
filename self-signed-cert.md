# Note replace mydomain.com with yourdomain.

Openssl
genrsa -out mydomain.com.key 2048
req -new -key mydomain.key -out mydomain.csr
x509 -req -days 1825 -in mydomain.com.csr -signkey mydomain.com.key -out mydomain.crt
sudo cat mydomain.com.key mydomain.com.crt >> mydomain.com.pem
