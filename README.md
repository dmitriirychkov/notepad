# notepad_teams
_________________________________________________________________________________________________________________________________________________________________________

Маршрут для добавления в таблицу:
ip route add xxx.xxx.xxx.xxx (куда) via xxx.xxx.xxx.xxx (через шлюз) dev *name (с какого девайса)
ip route add 192.168.124.236 via 192.168.104.254 dev bond0.43
_________________________________________________________________________________________________________________________________________________________________________

ping3:
hping3 192.168.103.103		--udp			--destport 5060		--interface eth0.770	--baseport 9080		--keep				--data 300		--fast
     [адрес назначения]	[заголовки пакетов]	[порт назначения]	[интерфейс источника]	[порт источника]	[не менять порт источника]	[размер тела пакета]	[10 п/с]
_________________________________________________________________________________________________________________________________________________________________________     

Версия дистриба Linux:
lsb_release -a
cat /etc/*-release
_________________________________________________________________________________________________________________________________________________________________________

Блокировка/разблокировка IP
iptables -I INPUT 1 -s 192.168.124.236 -j DROP
iptables -D INPUT -s 192.168.124.236 -j DROP
_________________________________________________________________________________________________________________________________________________________________________

Добавление правила для медиа rtp в цепочку MEDIA:
iptables -I MEDIA -p udp --dport 1025:65001 -d 192.168.104.91 -j ACCEPT
_________________________________________________________________________________________________________________________________________________________________________

Снятие .pcap
tcpdump -vv host 192.168.14.67 -w test.pcap
_________________________________________________________________________________________________________________________________________________________________________
