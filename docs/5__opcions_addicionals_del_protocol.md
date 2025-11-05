# 5. Opcions addicionals del protocol

Recorda que el protocol DHCP proporciona la configuració IP no sols una adreça IP i la màscara. Per a afegir nous paràmetres s'utilitza la paraula reservada options.

## option subnet-mask

L'opció `subnet-mask` s'utilitza per especificar la màscara de subxarxa que s'enviarà al client, si s'omet s'enviaria la màscara que va associada amb la declaració subnet a la qual pertanyi la IP assignada. El normal és ometre-per facilitar el manteniment del fitxer de configuració. La seva sintaxi és la següent:

`option subnet-mask ip-address;`

Exemple:
```
subnet 10.0.0.0 netmask 255.255.255.0 {
   range 10.0.0.10 10.0.0.254;
   option domain-name-servers 8.8.8.8, 8.8.4.4;
   option routers 10.0.0.1;
   option broadcast-address 10.0.0.255;
   option subnet-mask 255.255.255.0;
}
```

## option routers

L'opció `routers` s'usa per enviar-li al client la seva porta d'enllaç. Pot especificar una IP numèrica o un nom. La seva sintaxi és la següent:

`option routers ip-address;`

Exemple:
```
subnet 10.0.0.0 netmask 255.255.255.0 {
	range 10.0.0.10 10.0.0.254;
	option domain-name-servers 8.8.8.8, 8.8.4.4;
	option routers 10.0.0.1;
}
```

## option domain-name-servers

L'opció `domain-name-servers` s'empra per enviar al client els servidors DNS que utilitzarà. La seva sintaxi és la següent:

`option domain-name-servers ip-address [, ip-address ...];`

Els servidors s'han d'especificar per ordre de preferència, sent el primer de la llista el que s'utilitzarà com a servidor DNS primari.

Exemple:
```
subnet 10.0.0.0 netmask 255.255.255.0 {
	range 10.0.0.10 10.0.0.254;
	option domain-name-servers 8.8.8.8, 8.8.4.4;
}
```

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)