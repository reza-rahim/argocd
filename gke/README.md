## Create CA secret key 
openssl genpkey -algorithm RSA -out ca.key

## Create a CA   
openssl req -new -x509 -days 18000  -key ca.key -out cacert.crt

## Create a CSR to based on myserver.cnf 
openssl req -new -config myserver.cnf -keyout myserver.key -out myserver.csr

## Create a server key and cert
openssl x509 -req -days 18000 -in myserver.csr -CA cacert.crt  -CAkey ca.key   -out myserver.crt
