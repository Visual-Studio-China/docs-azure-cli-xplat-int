---
updated_at: 12/26/2016 8:43 AM
ms.date: 12/26/2016
content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/Authentication.md
original_content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/Authentication.md
gitcommit: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/2531b56dcebc9655773ee843d66f033cf4c7bcf5/azure-xplat/Conceptual/Authentication.md
---
## Authentication

Currently token based and cert based authentication mechanisms are supported in Xplat CLI.

* **Token** based authentication works in both **ASM** (Azure Service Management) & **ARM** (Azure Resource Manager) mode
  * Currently, only organizational accounts are supported. One cannot use an outlook, gmail, etc. account for authentication
  
```azure login -u $username -p $password```

* **Cert** based authentication works only in **ASM** mode
  * Download the publishsettings file (This cmd opens a browser in your machine)```azure account download```
    * One can manually download the publishettings file from [here](https://manage.windowsazure.com/publishsettings/index?client=xplat) 
  * Import the downloaded publishsettings file ```azure account import $path-to-publish-settings-file```

## Listing the subscriptions and Setting them

One can list the available subscriptions associated with an account and set a subscription as the default one

```
azure account list
azure account set "Subscription Name"
```

## Different Modes
One can flip between two modes of execution: **ASM | ARM**

```azure config mode [asm|arm] ```
