# 1. Introducció

### Exemples d'ús del servei DHCP

Els següents són alguns exemples d’ús del servei DHCP:

- En una biblioteca que admet connexions Wi-Fi, els clients obtindran concessions per a un temps reduït, per exemple, minuts.
- Un usuari d’Internet que rep al seu equip de casa una adreça IP dinàmica del seu proveïdor d’accés a Internet (ISP) tindrà una concessió que segurament serà per hores.
- En la xarxa corporativa d’una empresa que s’ha configurat dinàmicament usant DHCP, els equips rebran concessions dinàmiques per períodes de temps molt llargs, per exemple, dies.

DHCP és l’acrònim de dynamic host configuration protocol, en català, protocol de configuració dinàmica d’equips. El servei DHCP permet la configuració d’adreces IP, màscares, passarel·les per defecte i moltes altres opcions de configuració de manera totalment dinàmica.

**Què fa el DHCP?**

Una forma planera d’entendre el DHCP és imaginar que els equips de client en arrencar fan un crit per la xarxa i pregunten “que hi ha algú?”, “qui sóc jo?”. El servidor de DHCP els contesta proporcionant-los tota la informació necessària perquè sàpiguen qui són i com han de configurar els seus paràmetres de xarxa.

El servei DHCP proporciona un mecanisme de configuració centralitzat dels equips de la xarxa. En lloc de configurar un per un els equips de xarxa amb adreces i valors estàtics, un servidor DHCP anirà assignant als equips clients els valors que els corresponguin. Aquesta assignació es fa per un període de temps finit, passat el qual caldrà renovar-se.

**Avantatges DHCP**

El servei DHCP té diversos avantatges:

- Evita errors i conflictes IP.
- Centralitza l’administració.
- Estalvia temps.
- Simplifica l’administració.

Els principals avantatges d’utilitzar DHCP són: d’una banda, evitar conflictes d’adreces IP (adreces repetides i adreces errònies), ja que passar equip per equip a canviar la configuració és molt més pesat i propens a l’error que fer-ho editant un sol fitxer de configuració en el servidor DHCP; i, d’altra banda, poder fer l’administració centralitzada representa un estalvi de temps i de feina.

El servei DHCP simplifica l’administració de la configuració dels equips de xarxa fent-la centralitzada, dinàmica i amb concessions per períodes de temps finits.

La concessió dinàmica d’adreces IP i altres paràmetres de configuració de xarxa es realitza per a un període de temps determinat, que varia en funció de les necessitats del client i del servidor.

Llicenciat sota la [Llicència Creative Commons Reconeixement CompartirIgual 4.0](http://creativecommons.org/licenses/by-sa/4.0/)