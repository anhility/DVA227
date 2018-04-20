# Router

- IPsec 
 - Kryptering av länk på publikt nät från router till huvudserver. (GRE)
- VPN
 - Kryptering av länk på privat nät från router till huvudserver.
- NTP
 - Tids synkronisering.
- Admin Access
 - Dedikerat VLAN och IP-addresser för admin åtkomst.

- Firewall
 - Brandvägg konfigueradd för endast nödvändga portar öppna.
- FortiGuard
 - AV, Webfilter, etc för skydd mot virus etc
- Port-sec
 - Om port kopplas ur sänds en varning och porten stängs av.
- Loggning
 - Loggning av säkerhets händelser till huvud server.
- DHCP
 - Utdelning av IP-addresser till uppkopplade enheter-

- VLAN
 - Separat VLAN för admin, printers, users och guests. 
- RADIUS/Diameter
 - Synkat mot main servers AD. Vid inloggning ges användaren rätt VLAN. Lokalt lösenord för inlogging av admin ifall länk till main server är nere.
- CAP
 - Gäster på trådlösa måste logga in för att kunna använda nätverket.
- App-Control
 - Kontrol över vilka program/portar som får använda nätverket.

# Switch

- Admin access
 - Del av det dedikerade VLAN:et för admin åtkomst.
- NTP
 - Synkronisering mot närmast router.
- Port-sec
 - Om port kopplas i och ur med olika MAC-addrasser för ofta stängs porten ner under en tid och logg skickas.

- VLAN
 - Separat VLAN för varje enskilt företag som hyr bandbredd.
- StormControl
 - Skydd ifall flera enheter ansluta samtidigt.

# Main Server

- Loggning
 - Databas för loggning som alla enheter skickar sin log till.
- NTP
 - Master tid server alla enheter synkroniserar mot.
- NAT
 - Konvertering från publik till privat IP-address sker hos huvudservrarna, vilka pekar på rätt site's publika IP.
- IPSec
 - GRE-tunnel till alla siter.
- DNS
 - Siternas DNS-server för första check av url. Letar vidade om match inte hittades.
- RADIUS/Diameter
 - Main server för RADIUS.
