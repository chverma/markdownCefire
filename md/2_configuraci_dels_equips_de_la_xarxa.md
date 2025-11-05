# 2. Configuració dels equips de la xarxa

## Configuració d'un equip de xarxa

Qualsevol equip que pertany a una xarxa requereix que es configuri amb uns paràmetres mínims, que són l’adreça IP, la màscara i la porta d’enllaç per defecte. L’adreça IP identifica l’equip de manera única, i la màscara permet determinar la xarxa o subxarxa en què es troba l’equip. Amb aquests dos paràmetres n’hi ha prou per tenir connectivitat en la xarxa. Si es vol disposar d’accés fora de la xarxa pròpia (per exemple, a Internet o a la resta de la xarxa corporativa) cal definir també la porta d’enllaç predeterminada. A part de la configuració bàsica, els equips poden necessitar més paràmetres de configuració com, per exemple: el nom del host, el servidor DNS, el fitxer d’iniciació a baixar, etc.

Exemple de configuració de xarxa d'un equip de casa:

```
Direcció IP. . . . . . . . . . . : 192.168.1.33
Màscara de subred . . . . . . . . : 255.255.255.0
Puerta de enlace predeterminada.. : 192.168.1.1
Servidor DHCP . . . . . . . . . . : 192.168.1.1
Servidors DNS . . . . . . . . .  : 80.58.61.250 80.58.61.254
```

La configuració estàtica implica configurar els equips un a un. Fins i tot encara que es tingui accés remot als equips (per Telnet o SSH), com que cal modificar la configuració de xarxa no es pot fer assegut des de l’equip de l’administrador, sinó que cal anar equip per equip a modificar la configuració. Aquest procés de configuració cal que es faci per a cada equip de la xarxa. Fer-lo manualment implica configurar equip per equip sense cometre errades en teclejar les adreces i les màscares. Qualsevol canvi en l’estructura de la xarxa, com per exemple redefinir les subxarxes o modificar algunes adreces IP, significa tornar a configurar manualment els equips implicats. Tant si la xarxa corporativa consta de pocs equips com de molts, cal una solució que permeti automatitzar la configuració de xarxa de cada equip de manera centralitzada.

Les opcions de configuració de xarxa es poden assignar a cada equip estàticament o es poden configurar de manera dinàmica utilitzant DHCP. Com a administradors de xarxa, la gestió centralitzada que ens proporciona DHCP ens permet modificar la xarxa afegint, eliminant i redefinint, equips amb un cost mínim.

### Tipus d'assignacions d'adreces IP

Cada equip de xarxa té assignada una adreça IP que l’identifica de manera única dins la xarxa. La composició de l’adreça IP i la màscara determina la xarxa o subxarxa a la qual pertany. A més a més, es configuren altres paràmetres de xarxa com la porta d’enllaç predeterminada, servidors DNS, etc. Això es pot configurar manualment anant equip per equip i introduint aquesta informació.

Quan l’adreça IP i els altres paràmetres necessaris de configuració de la xarxa es configuren equip per equip, manualment, es diu que tenen una configuració IP estàtica.

Quan la configuració de xarxa d'un equip no es fa manualment i localment en l’equip sinó que es rep per mitjà d’un servidor DHCP, es diu que l’equip utilitza una configuració IP dinàmica. Per realitzar configuracions de xarxa dinàmicament caldran un o més servidors de DHCP (a manera de redundància) que proporcionaran la configuració als equips clients (els que cal configurar). Per tant, serà una estructura client-servidor.

Les adreces IP dinàmiques que rep el client les podem classificar en dues categories: assignació dinàmica d'interval i assignació fixa.

El servidor DHCP disposa d’un interval d’adreces que pot assignar als clients que demanen una adreça IP. Quan el servidor assigna una adreça qualsevol de l’interval al client (a l’atzar) es tracta d’una assignació dinàmica d’interval. El client no sap quina adreça IP tindrà i no hi ha manera de predir quina adreça se li concedirà en una futura configuració. A cada nova assignació l’adreça IP pot ser diferent.

Una assignació fixa es produeix quan el servidor DHCP sempre assigna la mateixa adreça al client. Per assignar sempre la mateixa adreça IP al client cal que el servidor pugui identificar inequívocament el client (per l’adreça MAC). El servidor disposa d’una taula amb les correspondències entre les adreces MAC i les adreces IP fixes.

Quan la configuració de xarxa d’un equip es rep per mitjà d’un servidor DHCP es diu que utilitza una adreça IP dinàmica. Aquesta adreça pot variar dins d’un interval d’adreces disponibles per al servidor DHCP o pot ser fixa. Si l'assignació de la configuració es fa per a sempre es diu que es fa una assignació de configuració IP automàtica.

Els avantatges de disposar d’una IP fixa són que la vostra identificació a Internet (la vostra adreça IP) no varia i tothom us pot identificar sempre per la mateixa IP. Podeu proporcionar serveis a altres equips, els clients us identifiquen sempre amb la mateixa adreça sense haver de recordar en cada moment quina adreça IP teniu avui (com passa en el cas d’una IP dinàmica).

## Cal que conegues

MAC: Cada interfície de xarxa s’identifica de manera única físicament per l’adreça MAC (media acces control, adreça d’accés al medi).

## Per saber més

Macchange: L’ordre GNU permet (mascarade) emmascarar l’adreça MAC pròpia. Compte! No feu maldats.

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)