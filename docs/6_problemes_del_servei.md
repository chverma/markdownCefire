# 6. Problemes del servei

## 6.1. Atacs al funcionament de DHCP i conflictes d'adreces IP

Com tot servei de xarxa, el servidor DHCP és susceptible de patir atacs mal intencionats. L’atac més fàcil i clàssic és el DoS o de denegació de servei. Consisteix a inundar de peticions un servidor per tal de saturar-lo i bloquejar-ne el funcionament. Un client pot realitzar innumerables peticions DHCP discovery fingint que són clients diferents (emmascarant la seva MAC) amb la intenció d’esgotar les adreces IP disponibles del servidor o simplement amb la intenció de sobrecarregar-lo amb tantes peticions que no done a l’abast a atendre-les o que ho faci lentament.

Un altre tipus d’atac consisteix a falsejar la informació que s’envia al client (DHCP Spoofing). Recordem que el client fa una sol·licitud d’IP en forma de difusió (broadcast) i la seva petició pot ser atesa per un o més servidors DHCP. Un dels servidors DHCP pot ser un atacant que intentarà proporcionar informació de configuració falsa al client. Per exemple indicant un servidor DNS també maliciós. Aquest pot falsejar les identitats de les màquines de la xarxa i, quan el client s’adreça a la seva entitat bancària, el servidor DNS en realitat li ha proporcionat una IP d’una màquina que falseja la de l’entitat bancària. Perillós, veritat?

Per posar remei a la inseguretat en la comunicació client-servidor DHCP, el protocol permet utilitzar mecanismes d’autenticació i xifratge. Aquests mecanismes queden fora de l’abast d’aquesta explicació.

Esquema de funcionament del DHCP Spoofing:
![DHCP Spoffing](img/dhcp-spoofing.jpg)

Font: [IES Haría](https://smr.iesharia.org/wiki/doku.php/sgf:ut1:ataques_dhcp). Esquema de funcionament del DHCP Spoofing ([CC BY-NC-SA](http://creativecommons.org/licenses/?lang=ca-ES))

## 6.2. Conflictes amb les adreces IP

Un dels principals motius per utilitzar DHCP és simplificar el procés de configuració de xarxa i minimitzar els conflictes per encavalcament d’adreces IP. Per desgràcia, això no garanteix que no es puguin produir conflictes. Per exemple, ens podem trobar en situacions en què dues màquines diferents tinguin la mateixa IP per una simple mala configuració del servidor DHCP. Un altre cas típic és el d’un client que s’ha configurat ell mateix una IP estàtica quan en la xarxa ja hi havia un equip que utilitzava la mateixa adreça IP assignada pel servidor DHCP.

Un problema habitual per als administradors poc experimentats és definir una configuració de xarxa local al client (hostname, servidor DNS, porta d’enllaç a utilitzar, etc.), però demanar l’adreça IP dinàmicament. La configuració dinàmica no és solament la IP i la màscara, sinó que el servidor DHCP pot proporcionar altres paràmetres de xarxa que sobreescriuran els que el client tenia definits localment (aquest és l’objectiu de DHCP!).

La configuració rebuda per DHCP sobreescriu la configuració local del client.

## 6.3. Diversos servidors DHCP en la mateixa xarxa

Un altre dels problemes habituals és que per error o maldat es connecte a la xarxa un altre servidor DHCP que responga primer a les peticions de DHCP Discover. En els entorns corporatius cal tindre control de què es connecta a la xarxa per a evitar problemes. Aquests tipus d'escenaris es poden minimitzar indicant que el servidor és autoritari en el segment de xarxa afectat.

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)