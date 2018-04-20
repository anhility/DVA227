# Router

- IPsec 
  - Kryptering av länk på publikt nät från router till huvudserver. (GRE)
- VPN
  - Kryptering av länk på privat nät från router till huvudserver.
- NTP
  - Tids synkronisering. Synkar mot huvud server.
- Admin Access
  - Dedikerat VLAN och IP-addresser för admin åtkomst. Loggas oach autentiseras mot radius server på core site. Consol-port öppen för lokal åtkomst om main server är nere där lokalt lösenord används.

- Firewall
  - Brandvägg konfiguerad för endast nödvändga portar öppna. 
- FortiGuard
  - AV, Webfilter, etc för skydd mot virus etc
- Port-sec
  - Om port kopplas ur sänds en varning och porten stängs av.
  - Pluggade portar som inte används. Kablar ska inte kunnas tas ur utan nyckel.
- Loggning
  - Loggning av säkerhets händelser till huvud server. Lokal kopia sparas i t.ex 24 timmar innan filen raderas och en ny fil skapas med nya kopior av loggning.
- DHCP
  - Utdelning av IP-addresser till uppkopplade enheter från givet IP-spann.

- VLAN
  - Separat VLAN för admin, printers, users och guests. 
- RADIUS/Diameter
  - Synkat mot main servers AD. Vid inloggning ges användaren rätt VLAN. Lokalt lösenord för inlogging av admin ifall länk till main server är nere.
- CAP
  - Gäster på trådlösa måste logga in för att kunna använda nätverket.
- App-Control
  - Kontrol över vilka program/portar som får använda nätverket. Sker dels av brandväggen och av FortiGuard. Företagets policy för tillåtna program/protokoll.

# Switch

- Admin access
  - Dedikerat VLAN och IP-addresser för admin åtkomst. Loggas oach autentiseras mot radius server på core site. Consol-port öppen för lokal åtkomst om main server är nere där lokalt lösenord används.
- NTP
  - Synkronisering mot närmast router.
- Port-sec
  - Om port till router kopplas ur skall switchen stänga porten. 
- VLAN
  - Separat VLAN för varje enskilt företag som hyr bandbredd.
- StormControl
  - Skydd ifall flera enheter ansluta samtidigt.

# Main Server

- Loggning
  - Databas för loggning som alla enheter skickar sin log till.
- NTP
  - Master tid server alla routrar synkroniserar mot.
- NAT
  - Konvertering från publik till privat IP-address sker hos huvudservrarna, vilka pekar på rätt site's publika IP/VPN-address.
- IPSec
  - GRE-tunnel till alla siter.
- DNS
  - Siternas DNS-server för första check av url. Letar vidade om match inte hittades.
- RADIUS/Diameter
  - Main server för RADIUS.
