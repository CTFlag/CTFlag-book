# VirtualBox Can't Start


## Call to WHvSetupPartition failed: ERROR_SUCCESS (Last=0xc000000d/87) (VERR_NEM_VM_CREATE_FAILED).
```
Result Code: E_FAIL (0x80004005)
Component: ConsoleWrap
Interface: IConsole {872da645-4a9b-1727-bee2-5585105b9eed}
```

### Solution
Firstly please execute the this instruction on your `CMD` of windows computer : `C:\Windows\system32>bcdedit /set hypervisorlaunchtype off`  then restart your computer bro.

> refer to:  https://www.cnblogs.com/a208606/p/10959243.html
