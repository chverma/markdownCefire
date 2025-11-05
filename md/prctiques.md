# Pràctiques

## Cas pràctic

Donat el següent esquema i suposant que l'enrutador d'internet disposa d'un servei DHCP funcional, crea el fitxer de configuració de DHCP perquè hi haja:

![Esquema de xarxa](img/esquema-dhcp.png)

Llicència: [CC BY-NC-SA](http://creativecommons.org/licenses/?lang=ca-ES)

a. 20 adreces IP excloses.
b. Una reserva per al commutador.
c. La resta formaran part de l'interval d'assignació dinàmica.
d. Una vegada creat el fitxer de configuració les adreces IP de l'esquema serà un dels escenaris possibles.
e. El temps per defecte de connexió serà de 20 minuts i el màxim 50.
f. Escriu el fitxer de configuració `interfaces` de l’enrutador d’Internet. Suposem que és un equip amb Ubuntu.

```
# Exemple bàsic de configuració dhcpd.conf 
subnet 192.168.1.0 netmask 255.255.255.0 
{ 
	range 192.168.1.11 192.168.1.29; 
	option domain-name-servers 192.168.1.1, 193.146.96.2, 193.146.96.3; 
	option domain-name "uimagen.iaf"; 
	option routers 192.168.1.1; 
	option subnet-mask 255.255.255.0; 
	option broadcast-address 192.168.1.255;
	default-lease-time 86400; 
	max-lease-time 172800; 
	host apache 
	{ 
		hardware ethernet 00:10:5a:f1:35:87; 
		fixed-address 192.168.1.3; 
	} 
} 
```

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)