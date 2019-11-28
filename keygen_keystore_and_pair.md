### Generate Keystore

```sh
keytool -genkey -v -keystore keystore.jks -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
```

### Generate without any prompts

```sh
keytool -genkey -v -keystore keystore.jks -alias aliasname -dname "CN=unknown, OU=unknown, O=unknown, L=unknown, S=unknown, C=unknown" -storepass **** -keyalg RSA -keysize 2048 -validity 10000
```

### Use keystore to generate key pair

```sh
keytool -list -rfc --keystore keystore.jks | openssl x509 -inform pem -pubkey -noout
```

### generate without prompts

```sh
keytool -list -rfc --keystore keystore.jks -storepass deepwav | openssl x509 -inform pem -pubkey -noout > public.txt
```

> for windows give absolute path of openssl.exe (c:\bin\openssl\bin\openssl.exe)

> download from https://slproweb.com/products/Win32OpenSSL.html (it's safe!)
