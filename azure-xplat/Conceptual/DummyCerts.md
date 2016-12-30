---
updated_at: 12/30/2016 4:45 AM
ms.date: 12/30/2016
content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/DummyCerts.md
original_content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/DummyCerts.md
gitcommit: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/a279321f0a73c72eb40e8107a6580f28e289cd66/azure-xplat/Conceptual/DummyCerts.md
---
###Creating dummy certificates for testing purpose.

You will find this helpful while running some vm tests.

### Online Service
[Cert-Depot](http://www.cert-depot.com.) - It can create certificates in both unencrypted PEM format, and PFX.

### Openssl

* Install openssl package for your operating system from [here](https://www.openssl.org/related/binaries.html)

* Generating a private key: 
```openssl genrsa 2048 > private.pem```

* Generating the self signed certificate:
```openssl req -x509 -new -key private.pem -out public.pem```

* If required, creating PFX:
```openssl pkcs12 -export -in public.pem -inkey private.pem -out mycert.pfx```
