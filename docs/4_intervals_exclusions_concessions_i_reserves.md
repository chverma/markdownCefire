# 4. Intervals, exclusions, concessions i reserves

Els clients DHCP obtenen del servidor una configuració de xarxa. Descrivim ara alguns dels termes que tenen lloc durant aquest procés, i que formen part de la configuració DHCP.

**Interval:** anomenen interval d’adreces IP el conjunt d’adreces dinàmiques que el servidor té disponibles per assignar als clients. Les adreces IP disponibles s’agrupen per oferir-se a les diverses subxarxes que atén el servidor. Una mateixa subxarxa pot disposar de diversos intervals. Segurament s’entendrà més fàcilment amb un exemple:

```
subnet 140.220.191.0 netmask 255.255.255.0 {
	 range 140.220.191.150 140.220.191.249;
}
subnet 239.252.197.0 netmask 255.255.255.0 {
	range 239.252.197.10 239.252.197.107;
	range 239.252.197.113 239.252.197.250;
}
```

En l’exemple anterior s’observa que la primera subxarxa disposa d'un interval de 100 adreces dinàmiques (de la 140.220.191.150 al 250). La segona subxarxa permet assignar dinàmicament dos intervals d'adreces no correlatius.

**Exclusions:** entenem per exclusions aquelles adreces IP que no s'ofereixen dinàmicament per part del servidor. És a dir, que no formen part de cap interval.

**Concessions:** l’assignació d’una adreça IP i la resta de paràmetres de xarxa a un client per part del servidor, és una concessió (o lease). Els clients reben les concessions per períodes de temps finits, que en finalitzar, cal renegociar. Tant el client com el servidor s’anoten les concessions, el client la que rep i el servidor les que concedeix. Quan finalitza una concessió el servidor pot decidir revocar-la o ampliar-ne la concessió.

El client tothora pot decidir renunciar a la concessió. Si el client vol allargar la concessió inicia un diàleg DHCP abreujat amb el servidor que pot acabar amb una renovació o amb la pèrdua de la concessió (sempre pot tornar a començar el procés). Tant el servidor com el client normalment miren les concessions que s’han efectuat entre ells amb anterioritat per tal de, si és possible, repetir la mateixa assignació.

**Reserves:** anomenem reserves aquelles adreces IP que s’assignen via DHCP però de manera fixa. És a dir, són adreces que s’assignen dinàmicament però sempre i únicament a un host determinat. Fixeu-vos que tot i ser una adreça dinàmica només s’utilitza si el host associat en fa ús. Si el host està apagat l’adreça no es pot usar per a altres hosts, està reservada. Un exemple podria ser:

```
subnet 140.220.191.0 netmask 255.255.255.0 {
	host iocserver {
		hardware ethernet 08:00:2b:4c:59:23;
		fixed-address 140.220.191.1;
	}
	range 140.220.191.150 140.220.191.249;
}
```

En aquest exemple es pot veure que l'adreça 140.220.191.1 és una adreça reservada exclusivament per al host iocserver, que s’identifica mitjançant la seva adreça MAC.

## Activitat 2: Conceptes bàsics

Defineix en un document els següents conceptes:
- Interval
- Exclusions
- Concessions
- Reserves

Crea un fitxer de configuració indicant exemples dels conceptes anteriors. La xarxa de treball serà la 192.168.10.0/24.

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)