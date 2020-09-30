# DNS Information Collection

## IP Information Collection By DNS
### `dslook`
```shell
root@ctflag:~# nslookup ctflag.org
Server:		10.2.8.11
Address:	10.2.8.11#53

Non-authoritative answer:
Name:	ctflag.org
Address: 185.199.109.153
Name:	ctflag.org
Address: 185.199.108.153
```

### `dig`
```shell
root@ctflag:~# dig @8.8.8.8 xuegod.cn any

; <<>> DiG 9.11.5-P4-5.1+b1-Debian <<>> @8.8.8.8 xuegod.cn any
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 43771
;; flags: qr rd ra; QUERY: 1, ANSWER: 5, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;xuegod.cn.			IN	ANY

;; ANSWER SECTION:
xuegod.cn.		599	IN	A	101.200.128.35
xuegod.cn.		21599	IN	NS	dns8.hichina.com.
xuegod.cn.		21599	IN	NS	dns7.hichina.com.
xuegod.cn.		599	IN	MX	5 mxbiz1.qq.com.
xuegod.cn.		599	IN	MX	10 mxbiz2.qq.com.

;; Query time: 155 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Wed Sep 30 05:32:57 EDT 2020
;; MSG SIZE  rcvd: 152
```

```shell
root@ctflag:~# dig +noall +answer @8.8.8.8 xuegod.cn any
xuegod.cn.		599	IN	A	101.200.128.35
xuegod.cn.		21599	IN	NS	dns8.hichina.com.
xuegod.cn.		21599	IN	NS	dns7.hichina.com.
xuegod.cn.		599	IN	MX	5 mxbiz1.qq.com.
xuegod.cn.		599	IN	MX	10 mxbiz2.qq.com.
```


## DNS Version Information Collection
### `dslook` + `dig`
```shell
root@ctflag:~# dig +noall +answer @8.8.8.8 ctflag.org any
ctflag.org.		599	IN	A	185.199.108.153
ctflag.org.		599	IN	A	185.199.109.153
ctflag.org.		21599	IN	NS	f1g1ns2.dnspod.net.
ctflag.org.		21599	IN	NS	f1g1ns1.dnspod.net.
ctflag.org.		599	IN	SOA	f1g1ns1.dnspod.net. freednsadmin.dnspod.com. 1601027098 3600 180 1209600 180

root@ctflag:~# dig txt chaos VERSION.BIND @f1g1ns2.dnspod.net
;; Warning: query response not set
;; Warning: Message parser reports malformed message packet.

; <<>> DiG 9.11.5-P4-5.1+b1-Debian <<>> txt chaos VERSION.BIND @f1g1ns2.dnspod.net
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 24503
;; flags: rd ad; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; QUESTION SECTION:
;VERSION.BIND.			CH	TXT

;; ANSWER SECTION:
VERSION.BIND.		0	CH	TXT	"5.1.1912.05"

;; Query time: 13 msec
;; SERVER: 162.14.24.230#53(162.14.24.230)
;; WHEN: Wed Sep 30 05:46:45 EDT 2020
;; MSG SIZE  rcvd: 54
```
> So we got the DNS( f1g1ns2.dnspod.net ) version : "5.1.1912.05", It's often be used to find the vulnerability such as DoS Attack.


## Whois Information Collection
### `whois`
```shell
root@ctflag:~# whois xuegod.cn
Domain Name: xuegod.cn
ROID: 20140908s10001s72166376-cn
Domain Status: ok
Registrant: 北京学神科技有限公司
Registrant Contact Email: jianmingbasic@163.com
Sponsoring Registrar: 阿里云计算有限公司（万网）
Name Server: dns7.hichina.com
Name Server: dns8.hichina.com
Registration Time: 2014-09-08 10:52:31
Expiration Time: 2021-09-08 10:52:31
DNSSEC: unsigned
```
