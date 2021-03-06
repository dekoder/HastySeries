# HastyNslookup
A post-explotation NSLOOKUP.exe command implemented in pure C#.

## Build 
All binaries in HastySeries are built targeting .NET 3.5, for windows 7+ support. The following build env should be used:

* Windows 10 - 1803
* Visual Studio 2017
* .NET 3.5 
* `choco install sysinternals` or strings from SysInternals in your current path

ALL HastySeries compiled binaries can be found on the github page with the most recent releases. NOTE: THESE have many static sigs.. dont drop to disk unless you are sure they are cleared via PSP testing.

## Operate
### Command Examples:
```cmd
C:\Users\rt\Desktop\HastySeries\bin\Release>HastyNslookup.exe -help
C:\Users\rt\Desktop\HastySeries\bin\Release>HastyNslookup.exe google.com
C:\Users\rt\Desktop\HastySeries\bin\Release>HastyNslookup.exe 1.1.1.1
```
### Expected Output:
```cmd
Host Name : google.com
Address 0 : 172.217.15.78
```

## OpSec
### Strings
To prevent some basic string matching, some basic precautions where taken. of course this is a example and if OpSec is upmost concern change static key and use the `HastyFixup` string fixup project to build new strings before re-compile.

1) All strings are XOR'd with a static key 
2) All strings are than encoded with Base64 
3) Strings are decoded at execution 
4) Strings are XOR'd with static key
5) String is presented to console 
