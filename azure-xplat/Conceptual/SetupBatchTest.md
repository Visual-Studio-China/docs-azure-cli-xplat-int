---
updated_at: 12/28/2016 3:29 AM
ms.date: 12/28/2016
content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/SetupBatchTest.md
original_content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/azure-xplat/Conceptual/SetupBatchTest.md
gitcommit: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/4b784b671a398888f1429ebf723e4db7e535c161/azure-xplat/Conceptual/SetupBatchTest.md
---
###Setup Instructions

- Set the NOCK_OFF and AZURE_NOCK_RECORD environment variables appropriately for the desired test mode. https://github.com/Azure/azure-xplat-cli-pr/blob/master/Documentation/TestModes.md
- If recording, set the following environment variables. In playback mode, the account name and url will be read from the recorded file instead, and the key will be set to a default value.
  * AZURE_BATCH_ACCOUNT: The name of the Batch account you're using for recording.
  * AZURE_BATCH_ACCESS_KEY: The key for the Batch account.
  * AZURE_BATCH_ENDPOINT: The url of the account. 
- If recording, create the common test pool and wait for it to reach steady state.
  * Run the following command from the root to create the pool: "node bin\azure batch pool create .\test\data\batchCreateTestPool.json"
  * Run the following command from the root to create the shared linux pool: "node bin\azure batch pool create .\test\data\batchCreateTestLinuxPool.json"
  * Wait for the pool to reach active state, steady allocation state, and to have 3 VMs: "node bin\azure batch pool show xplatTestPool"
  * Some tests may change the size of the pool, so double check that you still have 3 VMs before recording again.
- To launch the tests, from the root run "node .\scripts\unit.js testlist-batch-live.txt"
