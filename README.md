sudo nano /etc/bind/named.conf.local
// установка ключа, чтобы устранить нежелательное обновление этого DNS сервера неизвестными (в данной лаборатоной необязательно)
//key DHCP_UPDATER {
//algorithm HMAC­MD5.SIG­ALG.REG.INT; //secret "4GD8OIb8pZk4vAueACAfUQ==";
//};
// прямая зона
zone "lab.loc" { type master;
file "/var/lib/bind/db.lab.loc";
//allow­update { key DHCP_UPDATER; }; };
// обратная зоная
zone "0.168.192.in­addr.arpa" { type master;
file "/var/lib/bind/db.192";
//allow­update { key DHCP_UPDATER; }; };
