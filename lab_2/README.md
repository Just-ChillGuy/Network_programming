# Ход работы

Сначала я склонировал CHR, потом арендовал виртуальный сервер на том же Hostkey. В общем то первый CHR соединить с новой машиной было несложно, вторую пришлось настраивать, как и в первой лабораторной. 

В целом потребовалось всё то же самое: создание интерфейса, пира, настройка фаерволла.

```
[admin@chr2] > /interface wireguard add name=wg0 listen-port=51820
0  R name="wg0" mtu=1420 listen-port=51820  
     private-key="WGkf61kZ9/HJqSVQFh096K14JXpNI/9JpuKfXP6maEo="  
     public-key="0ZDkDilWlXbY7zgHLr1/+T6+/oV8+HwyB0VF/QkQmSI=" [
admin@chr2] > /ip address add address=10.20.0.3/24 interface=wg0
[admin@chr2] > /interface wireguard peers add \
\...     interface=wg0 \
\...     public-key="G1Xr3ClRFILqOW4p3HaHH8VPoTdtjSm3u77DKC3pc0U=" \
\...     endpoint-address=91.210.106.55 \
\...     endpoint-port=51820 \
\...     allowed-address=10.20.0.0/24 \
\...     persistent-keepalive=25s
```

IP у CHR2 10.20.0.3, проверка пинга: 
