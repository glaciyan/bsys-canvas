|Hardware Requirements|Notes|
|-|-|
|Privileged mode|Needed to prevent user-mode processes from executing privileged operations|
|Base/bounds registers|Need pair of registers per CPU to support address translation and bounds checks|
|Ability to translate virtual addresses and check if within bounds|Circuitry to do translations and check limits; in this case, quite simple|
|Privileged instruction(s) to update base/bounds|OS must be able to set these values before letting a user program run|
|Privileged instruction(s) to register exception handlers|OS must be able to tell hardware what code to run if exception occurs|
|**Ability to raise exceptions**|When processes try to access privileged instructions or out-of-bounds memory|
