### Generate Keystore

```sh
keytool -genkey -v -keystore keystore.jks -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
```

### Use keystore to generate key pair

```sh
keytool -list -rfc --keystore keystore.jks | openssl x509 -inform pem -pubkey -noout
```

> for windows give absolute path of openssl.exe (c:\bin\openssl\bin\openssl.exe)

> download from https://slproweb.com/products/Win32OpenSSL.html (it's safe!)
