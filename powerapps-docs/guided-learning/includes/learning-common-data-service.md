Gegevens vormen de kern van zakelijke toepassingen en processen: gegevens uit Excel, uit on-premises bronnen zoals SQL Server en uit cloudbronnen zoals Salesforce en SharePoint Online. Gegevens kunnen betrekking hebben op klanten, verkopen, werknemers en tal van andere zaken, maar het gemeenschappelijke thema is dat gegevens van cruciaal belang zijn voor uw bedrijf en een belangrijke rol spelen in de apps die u in PowerApps ontwikkelt. U hebt tot nu toe in de cursus met verschillende soorten gegevensbronnen gewerkt, en eerder hadden we de Microsoft Common Data Service geïntroduceerd. In deze sectie besteden we enige tijd aan de details, met uitleg over de voordelen en laten we zien hoe u de service kunt gebruiken.

## <a name="understanding-the-service"></a>Over de service
Laten we beginnen met enkele diagrammen. U hebt het eerste diagram wellicht al eerder gezien. Het bevat de onderdelen van het Microsoft-platform voor zakelijke toepassingen. U bent nu uiteraard bekend met PowerApps, maar wellicht hebt u ook al gewerkt met Microsoft Flow, Power BI of andere onderdelen. Wat u ziet is dat de Common Data Service en connectors en gateways voor al deze onderdelen relevant zijn. Op dit moment wordt de Common Data Service voornamelijk gebruikt in combinatie met PowerApps en Microsoft Flow, maar na verloop van tijd komt deze oplossing ook beschikbaar voor andere onderdelen.

![Diagram van platform voor zakelijke toepassingen](./media/learning-common-data-service/business-platform.png)

Nu u weet waar de Common Data Service in het grotere plaatje past, gaan we de onderdelen ervan bekijken. U kunt de Common Data Service zien als een hiërarchie. Op het laagste niveau slaat de service gegevens op een schaalbare en betrouwbare manier op en stelt de gegevens beschikbaar zodat meerdere toepassingen er gebruik van kunnen maken. Het volgende niveau is het algemene gegevensmodel met veel entiteiten die worden gebruikt in toepassingen en bedrijfsprocessen: entiteiten zoals Account, Contact, Product en Sales Order. U kunt de standaardentiteiten uitbreiden en uw eigen entiteiten maken op basis van de behoeften van uw bedrijf.

![Architectuurdiagram van Common Data Service](./media/learning-common-data-service/architecture.png)

Een entiteit is gewoon een combinatie van de metagegevens die als beschrijving dienen (veldnamen, gegevenstypen, enzovoort) en de gegevens die u erin opslaat. Als u bekend bent met Access of een andere database, lijkt een entiteit erg veel op een tabel. In het volgende onderwerp gaan we dieper in op entiteiten, maar kijk voorlopig eens naar de voordelen van het werken met entiteitgegevens in de Common Data Service:

* **Eenvoudig te beheren**: zowel de metagegevens als de gegevens worden opgeslagen in de cloud. U hoeft u geen zorgen te maken over de details of hoe de gegevens worden opgeslagen.
* **Eenvoudig te delen**: de gegevens kunnen makkelijk met collega's worden gedeeld, omdat PowerApps de machtigingen beheert.
* **Eenvoudig te beveiligen**: gegevens worden veilig opgeslagen, zodat gebruikers ze alleen kunnen bekijken als hun toegang wordt verleend. Met op rollen gebaseerde beveiliging kunt u de toegang tot entiteiten voor verschillende gebruikers binnen uw organisatie beheren.
* **Rich metagegevens**: gegevenstypen en relaties worden rechtstreeks in PowerApps gebruikt. Door bijvoorbeeld een veldtype-URL te definiëren worden uw gegevens als een hyperlink in uw app gepresenteerd.
* **Hulpprogramma's voor productiviteit**: entiteiten zijn beschikbaar binnen de invoegtoepassingen voor Microsoft Excel en Outlook om de productiviteit te vergroten en ervoor te zorgen dat uw gegevens toegankelijk zijn.
* **Selectielijsten**: maak een selectie uit een groot aantal standaardselectielijsten om handige vervolgkeuzelijsten op te nemen in uw entiteiten en apps.

## <a name="create-a-common-data-service-database"></a>Een Common Data Service-database maken
Een Common Data Service-database maakt u in een *omgeving*. We hebben het eerder in de cursus over omgevingen gehad, dus laten we de informatie even samenvatten: een omgeving is een container voor apps en andere bronnen, zoals de Common Data Service. Aan elke omgeving kan één exemplaar van de service gekoppeld zijn. Als u een omgevingsbeheerder bent en de service aan een omgeving wilt toevoegen, volg dan deze stappen.

Klik of tik vanaf het tabblad **Startpagina** op **Database maken**.

![Common Data Service-database maken](./media/learning-common-data-service/create-database.png)

Geef aan of u de toegang tot de database wilt beperken en klik of tik op **Mijn database maken**.

![Toegang tot Common Data Service opgeven](./media/learning-common-data-service/specify-access.png)

Nadat het proces is voltooid, ziet u alle standaardentiteiten die zijn opgenomen in het algemene gegevensmodel. Enkele daarvan worden hieronder weergegeven.

![Standaardentiteiten van Common Data Service](./media/learning-common-data-service/standard-entities.png)

Sommige aspecten van dit onderwerp zijn wellicht onbekend gebied voor u als u nog niet eerder met databases hebt gewerkt. Maar het algemene concept is tamelijk eenvoudig: de Common Data Service biedt een beveiligde en betrouwbare manier om gegevens op te slaan en om die gegevens te behandelen als algemene entiteiten zoals Account, Contact, Product en Sales Order. In het volgende onderwerp gaan we dieper in op entiteiten.

