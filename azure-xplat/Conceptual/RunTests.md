---
updated_at: 12/30/2016 7:30 AM
ms.date: 12/30/2016
content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/Documentaion/RunTests.md
original_content_git_url: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/dev/Documentaion/RunTests.md
gitcommit: https://github.com/Visual-Studio-China/azure-xplat-cli/blob/e782dc553e60b534e9d419a4511a9c54b4a47815/Documentaion/RunTests.md
---
## Running Xplat CLI Tests

#### Pre-requisite

* [Setup Environment Variables](./EnvironmentVariables.md)
* [Authentication and Account setup](./Authentication.md)

#### Run Tests
* Running tests for both the modes: ARM, ASM
This will execute all the tests mentioned in tests/testlist.txt and tests/testlistarm.txt
```
npm test
```

* Running **ASM** tests:
This will execute all the tests mentioned in tests/testlist.txt
```
npm -s run-script unit
```

* Running **ARM** tests:
This will execute all the tests mentioned in tests/testlistarm.txt
```
npm -s run-script unit-arm
```

* Running selective tests: Comment unrequired tests in test/testlist.txt or test/testlistarm.txt depending on which tests need to be run. A test can be commented by putting **#** at the start of a line in testlist[arm].txt.

#### Test Logs
Logs for each test run can be found in a time stamped .lof file under the **"/test/output/"** directory.
For example - **"/test/output/test_log_2015_3_25_14_14_26.log"**
