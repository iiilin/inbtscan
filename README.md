# inbtscan

Python nbtstat + smb_version without third party packages

用 Python 实现的一个类似 nbtscan 的东西，外边包了一层多线程

默认通过 NBNS 协议获取 NetBIOS Name，然后通过 139（默认） 或者 445 探测系统相关信息

写的比较粗糙，Python2 或 Python3 > 3.2 ~~目测~~ 都能用

## Usage：
```
python inbt.py ip [port 139|445]
```
## Example:
```
python inbt.py 172.16.9.0/24
```
## Result:
```
172.16.9.129    WORKGROUP\WIN-I8S0A16RCR7         # IP    Unique Name\Group Name
------------------------------------------------- # NetBIOS Names    U[Unique]/G[Group]    Service
WIN-I8S0A16RCR7	U	Server Service
WIN-I8S0A16RCR7	U	Workstation Service
WORKGROUP      	G	Domain Name
------------------------------------------------- # SMB Version Info
WORKGROUP\WIN-I8S0A16RCR7
Windows 7 Professional 7601 Service Pack 1|Windows 7 Professional 6.1|
Major Version: 6
Minor Version: 1
Bulid Number: 7601
NTLM Current Revision: 15
NetBIOS domain name: WIN-I8S0A16RCR7
NetBIOS computer name: WIN-I8S0A16RCR7
DNS domain name: WIN-I8S0A16RCR7
DNS computer name: WIN-I8S0A16RCR7
Time stamp: 2018-05-14 22:42:21.298930
```

## Reference:

[NetBIOS Over TCP/IP](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-2000-server/cc940063(v%3dtechnet.10))

[C#版本的smb_version](http://www.zcgonvh.com/post/CSharp_smb_version_Detection.html)

[NETBIOS主机名编码算法](http://weaponx.site/2017/06/07/NETBIOS%E4%B8%BB%E6%9C%BA%E5%90%8D%E7%BC%96%E7%A0%81%E7%AE%97%E6%B3%95/)

[RFC 1002](https://tools.ietf.org/html/rfc1002)