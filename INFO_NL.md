De Somtoday bron- en doelconnectoren vereenvoudigen het beheer van gebruikersaccounts en autorisaties binnen je onderwijsorganisatie aanzienlijk. De connectoren koppelen Somtoday aan je doelsystemen via de identity & access management (IAM)-oplossing HelloID van Tools4ever. De koppeling automatiseert diverse Instroom-, Doorstroom- en Uitstroom (IDU)-processen binnen je organisatie, zodat jij hiernaar geen omkijken hebt. In dit artikel lees je meer over deze koppeling, de specifieke mogelijkheden die dit biedt en de voordelen. 

## Wat is Somtoday

Somtoday is een elektronische leeromgeving (ELO), een portaal dat leerlingen en verzorgers onder andere inzicht geeft in huiswerk, cijfers en berichten, evenals het rooster en de studieplanning. Ook kunnen leerlingen onder meer werkstukken uploaden en delen met docenten. Somtoday kan als bronsysteem worden ingezet voor IDU-processen. Het vormt een belangrijke uitbreiding op een HRM-systeem. Zo geeft het systeem extra inzicht voor medewerkers en bevat alle gegevens van deelnemers. Deze data spelen een belangrijke rol in het IDU-proces van educatieve instellingen. Medewerkers en leerlingen gebruiken Somtoday daarnaast als werkomgeving. 

## Waarom is een Somtoday koppeling handig?

De Somtoday connector wordt in veel gevallen als bronkoppeling ingezet ter aanvulling van een HR-systeem. De koppeling is daarbij specifiek gericht op deelnemers en het beschikbaar maken van extra data over medewerkers. Daarnaast ondersteunt de Somtoday connector het beheer van accounts van leerlingen en medewerkers in het ELO ter ondersteuning van de IDU-processen. De Somtoday connector maakt een koppeling met veelvoorkomende doelsystemen mogelijk, zoals:

*	Active Directory 
* Entra ID 
* Google Workspace

Verdere details over de koppeling met deze doelsystemen zijn te vinden verderop in het artikel.

## HelloID voor Somtoday helpt je met

**Verbeterde compliance:** De integratie verbetert ook je compliance. Zo borg je dankzij automatisering het proces, zorg je voor consistentie en voorkom je fouten. Prettig met het oog daarop is ook Role Based Access Control (RBAC), waarbij je mutaties niet op individuele basis maar juist op basis van RBAC-rollen toekent. Dit maakt het onder meer mogelijk de rechten die bepaalde groepen gebruikers krijgen in één keer te definiëren. Alle mutaties die HelloID uitvoert legt de IAM-oplossing vast in een uitgebreid auditlog, waardoor je compliance kunt aantonen. 

**Uniform accountbeheer:** De instroom van een nieuwe leerling of medewerker vraagt om het aanmaken van de juiste accounts. Met behulp van de integratie van Somtoday en je doelsystemen met behulp van HelloID heb je hiernaar geen omkijken. Door het proces in belangrijke mate te automatiseren zorg je voor consistent en uniform accountbeheer. Zo voorkom je fouten en zorg je dat gebruikers op het juiste moment over het juiste account beschikken. 

**Aansluiting op het IDU-proces in de organisatie:** Je onderwijsorganisatie is continu in beweging, zowel als het gaat om leerlingen als medewerkers. Zo stromen nieuwe personen in, gaan leerlingen door naar een volgend schooljaar, krijgen medewerkers een andere functie toegewezen en stromen personen uit. Al deze ontwikkelingen vragen om mutaties in je systemen, waardoor de hoeveelheid handelingen die je moet uitvoeren snel oploopt. De koppeling van Somtoday met je doelsystemen neemt je veel werk uit handen en zorgt dat accountbeheer perfect aansluit op het IDU-proces binnen je organisatie. 

**Verbeterde efficiëntie:** Het automatiseren van accountbeheer biedt grote voordelen. Zo til je je efficiëntie naar een hoger niveau, waardoor je gebruikers nog sneller kunt bedienen. Prettig, want zo beschikken leerlingen en medewerkers eerder over de accounts en autorisaties waarop zij in de praktijk vertrouwen. 

## Hoe HelloID integreert met Somtoday
Indien je Somtoday met je doelsystemen integreert, fungeert Somtoday doorgaans als een aanvulling op je HR-systeem. Dit maakt het mogelijk de volledige levenscyclus van gebruikersaccounts in je doelsystemen via HelloID geautomatiseerd te beheren. Zo voorkom je fouten, bespaar je tijd en ben je gebruikers nog sneller van dienst.

| Wijziging in Somtoday |	Procedure in doelsystemen |
| ------------------------- | --------------------- | 
| **Nieuwe leerling of medewerker** |	HelloID maakt op basis van informatie uit Somtoday in je doelsystemen de benodigde accounts aan voor nieuwe leerlingen en medewerkers, en kent de vereiste autorisaties toe. Je hebt geen omkijken naar dit proces; HelloID detecteert automatisch de wijziging in Somtoday en voert op basis hiervan de gewenste mutaties uit.|
| **Ander schooljaar, gewijzigde functie, wijziging in plaatsing, vakkeuzes en lesgroepen** |	Onderwijsorganisaties zijn continu in beweging. Zo gaan bestaande leerlingen door naar een volgend schooljaar of doen het schooljaar juist nogmaals over. Ook kan het zo zijn dat leerlingen andere vakken mogen kiezen en dat kan leiden tot andere lesgroepen. Tegelijkertijd is ook je personeelsbestand dynamisch en krijgen medewerkers bijvoorbeeld nieuwe functies toegewezen. Deze wijzigingen kunnen vragen om andere accounts en autorisaties in je gekoppelde doelsystemen. HelloID automatiseert dit proces in belangrijke mate, waarbij het autorisatiemodel van HelloID altijd leidend is. Toegewezen autorisaties die gekoppeld zijn aan de oude functie trekt HelloID automatisch in.|
| **Naam wijzigt** | Door allerlei redenen kan de naam van een leerling of medewerker veranderen. HelloID detecteert deze wijziging en past de gebruikersnaam van gebruikers hierop automatisch aan. |
| **Leerling of medewerker vertrekt** |	Gebruikersaccounts in doelsystemen worden gedeactiveerd, waarbij HelloID betrokken medewerkers in de organisatie informeert. Na verloop van tijd verwijdert HelloID automatisch de accounts en trekt verstrekte permissies in. |

HelloID maakt gebruik van standaard REST calls voor de ConnectAPI en SOAP calls voor de HRMService. De IAM-oplossing haalt via de ConnectAPI per instelling en vestiging gegevens op over een specifiek peiljaar. Op basis hiervan verwerkt HelloID de plaatsingen, vakkeuzes en lesgroepen, zodat deze gebruikt kunnen worden bij het toekennen van autorisaties met behulp van business rules. De HRMService maakt het beheer van gegevens op de persoonskaart in het HR-gedeelte van Somtoday mogelijk.

## Somtoday via HelloID koppelen met doelsystemen
Je kunt Somtoday via HelloID aan allerlei doelsystemen koppelen. Handig, want zo kan HelloID op basis van informatie uit Somtoday mutaties doorvoeren in je doelsystemen. De koppelingen nemen je zo niet alleen werk uit handen, maar tillen ook het beheer van zowel gebruikers als autorisaties naar een hoger niveau. Enkele voorbeelden van veelvoorkomende integraties zijn:

* **Somtoday - AFAS koppeling:** Dankzij de koppeling tussen Somtoday en AFAS kan je het beheer van gebruikersaccounts en autorisaties in belangrijke mate automatiseren. Maak je een nieuw account aan of wijzig je een bestaand account in Somtoday? Dan detecteert HelloID deze aanpassing en verwerkt dit automatisch in AFAS. De koppeling neemt je zo werk uit handen en stroomlijnt accountbeheer. 

* **Somtoday – Active Directory koppeling:** Dankzij de koppeling tussen Somtoday en Active Directory is het onder meer mogelijk deze systemen geautomatiseerd te synchroniseren. Zo stel je zeker dat accounts en autorisaties altijd volledig up-to-date zijn. Daarnaast voorkom je menselijke fouten doordat je gegevens niet langer handmatig hoeft over te nemen.

* **Somtoday – Entra ID koppeling:** De integratie tussen het cloudgebaseerde Entra ID maakt het onder meer mogelijk alles van account provisioning tot het toekennen van de juiste autorisaties volledig te automatiseren. Vind het provisioning-proces plaats op de on-premises tegenhanger Active Directory? Dan kan je onder meer cloud-only permissies toekennen. 

Voor HelloID zijn 200 connectoren beschikbaar, waarmee je de IAM-oplossing aan een breed scala aan bron- en doelsystemen kunt koppelen. Dankzij deze brede integratiemogelijkheden kan je Somtoday dan ook koppelen aan alle populaire doelsystemen. 
