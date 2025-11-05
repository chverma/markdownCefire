# 3. El model funcional DHCP

El protocol DHCP utilitza UDP en la capa de transport. Utilitza dos ports:

- Port 67, on escolta el servidor.
- Port 68, on escolta el client.

El protocol DHCP descriu el diàleg que es produeix entre client i servidor per a la concessió de configuracions IP. En una xarxa amb configuració d’equips dinàmica, un o més servidors DHCP escoltaran les peticions dels clients en el port 67. Els clients DHCP sol·licitaran al servidor DHCP una configuració IP, i començarà un procés de negociació que ha d’acabar (si tot va bé) amb la concessió d’una adreça IP al client. Els servidors parlen al port 68 dels clients.

La negociació que s’estableix es pot definir a grans trets de la manera següent:
1. El client sol·licita una adreça IP (de fet, una configuració de xarxa).
2. El servidor mira les adreces IP disponibles dins de l’interval d’adreces dinàmiques de què disposa per concedir i n’ofereix una al client.
3. Si el client l’accepta, envia una sol·licitud al servidor per fer-la seva.
4. Si al servidor li sembla bé, accepta la petició del client i li confirma que pot utilitzar aquesta IP, que la hi concedeix per un període de temps limitat.

### UDP en les transmissions DHCP

L’intercanvi d’informació entre client i servidor no és gaire gran (poc volum de dades) i no requereix un flux permanent (una conversa continuada). És per això que el protocol que s’utilitza en les transmissions DHCP és l’UDP.

La concessió de l’adreça IP és per un període de temps establert pel servidor. Això significa que, transcorregut aquest període, el client haurà de renegociar la concessió en un procés similar al descrit anteriorment.

El procés real, però, és més detallat. El podem repassar: consta principalment de quatre parts: la petició del client o discovery, l’oferta del servidor o offer, l’acceptació de l’adreça IP pel client o request, i la confirmació del servidor o acknowledgement. A part d’aquest tipus de missatges, el protocol DHCP en defineix d’altres com el de petició d’informació o information i el d’alliberament de l’adreça IP o releasing.

#### Tipus de paquets DHCP:
- DHCP discover
- DHCP offer
- DHCP request
- DHCP ack / DHCP nack
- DHCP decline
- DHCP release
- DHCP information

#### Diagrama del model funcional del protocol DHCP
![Model funcional del protocol DHCP](img/smxm7uf1ud1_im1.png)

Font: [IOC](http://ioc.xtec.cat/materials/FP/Materials/2201_SMX/SMX_2201_M07/web/html/WebContent/u1/a1/continguts.html). [Model funcional del protocol DHCP](https://corriol.github.io/sxe/UD03/Model%20funcional%20del%20protocol%20DHCP) ([CC BY-NC-SA](http://creativecommons.org/licenses/?lang=ca-ES))

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)