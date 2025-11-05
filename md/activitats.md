# Activitats

## Activitat: Bloc 2

1. Llista els quatre paràmetres més importants de la configuració d'una xarxa IP.
2. Dibuixa i explica com es comuniquen client i servidor per a negociar una nova configuració IP, indicant els ports involucrats, el nom del missatge, l’emissor i el destinatari.
3. Què és una concessió? I una reserva?
4. Indica quina de les següents afirmacions referents al servei DHCP és vertadera:
	1. Segueix el model client/servidor i utilitza els ports TCP 67 i 68.
	2. Permet assignar una adreça IP a una màquina concreta en funció de la seua MAC.
	3. Permet la resolució de noms de host de forma dinàmica.
	4. Utilitza un missatge de tipus DHCPACK en el que envia al client la confirmació dels paràmetres de configuració de nom.
5. Què és Webmin? Explica la seua utilitat.

## Activitat: Bloc 2

1. Quins són els avantatges d’utilitzar un servidor DHCP en una xarxa? Explica'ls.
2. Quines diferències hi ha entre una adreça IP i una MAC?
3. De quines formes podem assignar una adreça IP amb DHCP? Explica-les.
4. Què indica cada línia del següent arxiu de configuració de DHCP? Excepte 1) i 2).

```
authoritative;
server-identifier 192.168.1.1;
default-lease-time 86400;
max-lease-time 86400;
option subnet-mask 255.255.255.0;
option broadcast-address 192.168.1.255;
option routers 192.168.1.1;
subnet 192.168.1.0 netmask 255.255.255.0
{ 
	range 192.168.1.2 192.168.1.10; 
	option routers 192.168.1.254;
}
host fantasia {
	hardware ethernet AA:BB:CC:DD:EE:FF;
	fixed-address 192.168.1.2; 
}
```

5. Investiga que signifiquen les línies 1) i 2). Comprova-ho almenys en dos recursos.
6. Quina informació es guarda en el fitxer `/etc/network/interfaces`? Explica el següent fitxer.

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 192.168.1.5
netmask 255.255.255.0
gateway 192.168.1.1
```

7. Si un servidor DHCP té configurat el següent interval 192.168.0.44 – 192.168.0.244, quantes adreces IP té excloses?
8. Dels següents missatges quins envia el client i quins el servidor?

	- DHCP Offer
	- DHCP Release
	- DHCP Discover
	- DHCP Request
	- DHCP Inform
	- DHCP ACK
	- DHCP NACK

9. Amb les dades de l'exercici 4 escriu un fitxer `interfaces` que assigne una adreça ip fixa a un nou equip.

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)