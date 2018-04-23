# Router

- IPsec 
  - Kryptering av länk på publikt nät från router till huvudserver. (GRE)
  * Ville
  
- VPN
  - Kryptering av länk på privat nät från router till huvudserver.
  * Ville
  
- NTP
  - Tids synkronisering. Synkar mot huvud server.
  - Varifrån synkar vi tiden och hur sprids information i nätverket.
  * Isak
  
- Admin Access
  - Dedikerat VLAN och IP-addresser för admin åtkomst. Loggas oach autentiseras mot radius server på core site. Consol-port öppen för lokal
  åtkomst om main server är nere där lokalt lösenord används.
  - Utöka det som står ovan lite mer.
  * Ville

- Firewall
  - Brandvägg konfiguerad för endast nödvändga portar öppna. 
  - Kolla mer hur olika brandväggsfunktioner på Fortigate routrarna fungerar.
  
- FortiClient
  - AV, Webfilter, etc för skydd mot virus etc
  - Kolla vilka appar/hemsidor etc som ska blockas
  - Kolla om det ens går att pusha ut FortiClien till alla användare då det är BYOD
  - App-Control
  - Kontrol över vilka program/portar som får använda nätverket. Sker dels av brandväggen och av FortiGuard. Företagets policy för tillåtna program/protokoll.
  - Kolla hos andra företag vad de har för policy gällande app-kontrol. Vad är best-practice.
  
- Port-sec
  - Om port kopplas ur sänds en varning och porten stängs av. Hur går man tillväga för att konfigurera detta.
  - Pluggade portar som inte används. Kablar ska inte kunnas tas ur utan nyckel. Kolla på olika företag som erbjuder en produkt so skyddar      mot detta.
  * Ville
 
- Loggning
  - Loggning av säkerhets händelser till huvud server. Lokal kopia sparas i t.ex 24 timmar innan filen raderas och en ny fil skapas med nya kopior av loggning.
  - Hur ska loggningen fixas, kolla på olika mjukvaru alternativ. Ska loggar sparas längre om koppling till core går ner under en längre tid?
  * Isak
  
- DHCP
  - Utdelning av IP-addresser till uppkopplade enheter från givet IP-spann.
  - Kolla hur DHCP utdelning ska ske. Ska IP adresser ges ut från en DHCP server på core eller ska det ske lokalt.
  * Isak

- VLAN
  - Separat VLAN för admin, printers, users och guests. '
  - Vilka vlan ska vara isolerade, vilka ska kunna kommunicerade med varandra, vilka enheter ska de vara på?
  
- RADIUS/Diameter
  - Synkat mot main servers AD. Vid inloggning ges användaren rätt VLAN. Lokalt lösenord för inlogging av admin ifall länk till main server är nere.
  - Vlan utdelning? Exempel på det. (Hur ska konsol inlogg på nätverksenheterna ske om de inte kan nå radius servern går ner)

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
  - Kolla lite hur det funkar och hur det implementeras
  * Isak

# Main Server

- Loggning
  - Databas för loggning som alla enheter skickar sin log till.
- NTP
  - Master tid server alla routrar synkroniserar mot.
- NAT
  - Konvertering från publik till privat IP-address sker hos huvudservrarna, vilka pekar på rätt site's publika IP/VPN-address.
  - Hur ska NAT ske, varför NAT i Core siten? 
- IPSec
  - GRE-tunnel till alla siter.
- DNS
  - Siternas DNS-server för första check av url. Letar vidade om match inte hittades.
  * Ville
- RADIUS/Diameter
  - Main server för RADIUS.
  - Redundans på RADIUS servrar
