---
updated_at: 12/28/2016 2:41 AM
ms.date: 12/28/2016
content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/DummyCerts.md
original_content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/DummyCerts.md
gitcommit: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/b5f1f48534a095fdf2852b504110001c0652d8b2/azure-xplat/Conceptual/DummyCerts.md
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
