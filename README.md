# Daftar URL/IP Telkom yang perlu di blacklist

Telkom Indihome/Telkomsel meng-inject iklan di semua website yang menggunakan http, jadi jangan heran bila sewaktu main game, tiba-tiba muncul iklan :(

Solusi paling ampuh gunakan [DNSCrypt](https://github.com/jedisct1/dnscrypt-proxy), ataupun VPN. 

# DNS HIJACK

```
$ host afdakdsfjasfdasdf.aoisdfuaifdsasyufdsafd
afdakdsfjasfdasdf.aoisdfuaifdsasyufdsafd has address 36.86.63.182
afdakdsfjasfdasdf.aoisdfuaifdsasyufdsafd has address 36.86.63.182
afdakdsfjasfdasdf.aoisdfuaifdsasyufdsafd has address 36.86.63.182

$ host kodok.galau
kodok.galau has address 36.86.63.182
kodok.galau has address 36.86.63.182
kodok.galau has address 36.86.63.182
```

respon header dari browser
```
GET / HTTP/1.1
Host: kodok.galau
Connection: keep-alive
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (X11; Fedora; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/77.0.3865.90 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9

HTTP/1.0 302 Found
Location: http://mercusuar.uzone.id
Server: BigIP
Connection: Keep-Alive
Content-Length: 0
```

curl verbose
```
> curl -v http://kodok.galau -I
*   Trying 36.86.63.182:80...
* TCP_NODELAY set
* Connected to kodok.galau (36.86.63.182) port 80 (#0)
> HEAD / HTTP/1.1
> Host: kodok.galau
> User-Agent: curl/7.65.3
> Accept: */*
> 
* Mark bundle as not supporting multiuse
* HTTP 1.0, assume close after body
< HTTP/1.0 302 Found
HTTP/1.0 302 Found
< Location: http://mercusuar.uzone.id
Location: http://mercusuar.uzone.id
< Server: BigIP
Server: BigIP
* HTTP/1.0 connection set to keep alive!
< Connection: Keep-Alive
Connection: Keep-Alive
< Content-Length: 0
Content-Length: 0

< 
* Connection #0 to host kodok.galau left intact
```
