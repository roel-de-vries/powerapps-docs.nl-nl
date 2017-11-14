In deze sectie van de cursus maken we een app op basis van *entiteiten* in de Common Data Service. Entiteiten zijn blokken gedeelde gegevens die kunnen worden gewijzigd, opgeslagen, opgehaald en waarmee kan worden gecommuniceerd. We genereren de app op basis van een entiteit, laten zien hoe de app kan worden aangepast, voegen een andere gegevensbron toe en roepen een stroom aan vanuit de app. Als u de sectie over het maken van een app op basis van een SharePoint-lijst al hebt doorgenomen, worden hier enkele van dezelfde onderwerpen behandeld, maar gaan we daar dieper op in, met name wat betreft het aanpassen van de app.

We maken een app voor casebeheer die door een IT-afdeling kan worden gebruikt om problemen met hardware en software in een organisatie te volgen, te prioriteren en daar actie op te ondernemen. Bij het doorlopen van de onderwerpen kunt u ook nadenken over andere gebruiksmogelijkheden voor een app als deze. We maken gebruik van gegevens uit de Common Data Service omdat deze geschikt zijn voor het opslaan van app-gegevens, maar u kunt voor dezelfde app ook een andere gegevensbron gebruiken.

PowerApps bevat een complexere sjabloon voor casebeheer die gebruikmaakt van dezelfde entiteiten als de app die wij gaan maken. Nadat u deze sectie hebt doorgenomen, raden we u aan deze sjabloon te verkennen om een idee te krijgen van wat u in PowerApps allemaal kunt bouwen.

## <a name="create-a-common-data-service-database"></a>Een Common Data Service-database maken
De eerste stap in het bouwen van deze app is het maken van een Common Data Service-database als u die nog niet hebt. Een Common Data Service-database maakt u in een *omgeving*. Een omgeving is een container voor apps en andere bronnen (we bespreken omgevingen verderop in de cursus ). Een *omgevingsbeheerder* kan deze stappen volgen om een database te maken (bent u geen beheerder, neem dan contact op met een beheerder in uw organisatie).

Klik of tik vanaf het tabblad **Startpagina** op **Database maken**.

![Common Data Service-database maken](./media/learning-case-app-generate/create-database.png)

Geef aan of u de toegang tot de database wilt beperken (we houden de database geopend) en klik of tik op **Mijn database maken**.

![Toegang tot Common Data Service opgeven](./media/learning-case-app-generate/specify-access.png)

Nadat het proces is voltooid, ziet u alle standaardentiteiten die zijn opgenomen in het algemene gegevensmodel. Enkele daarvan worden hieronder weergegeven.

![Standaardentiteiten van Common Data Service](./media/learning-case-app-generate/standard-entities.png)

## <a name="generate-an-app-from-the-case-entity"></a>Een app genereren op basis van de Case-entiteit
Nu de database is gemaakt, maken we een verbinding met de Case-entiteit en genereren we een app. Klik of tik op **Nieuwe app** en vervolgens op **PowerApps Studio voor internet**.

![Nieuwe app in PowerApps Studio voor internet](./media/learning-case-app-generate/choose-studio.png)

Omdat we een telefoon-app voor een Common Data Service-entiteit gaan maken, klikt of tikt u onder **Common Data Service** op **Telefoonindeling**.

![Telefoon-app op basis van Common Data Service](./media/learning-case-app-generate/common-phone.png)

In het volgende scherm kiest u een verbinding en een entiteit om verbinding mee te maken en klikt of tikt u op **Verbinden**.

![Verbinding maken met Case-entiteit](./media/learning-case-app-generate/connect-entity.png)

Nadat u **Verbinden** hebt gekozen, begint PowerApps met het genereren van de app. PowerApps trekt allerlei conclusies op basis van uw gegevens om een nuttige app als uitgangspunt te genereren.

## <a name="view-the-app-in-powerapps-studio"></a>De app in PowerApps Studio weergeven
Uw nieuwe app met drie schermen wordt geopend in PowerApps Studio. Alle apps die worden gegenereerd op basis van gegevens hebben dezelfde reeks schermen:

* Het **blader**scherm: voor het zoeken, sorteren, filteren en vernieuwen van de gegevens die zijn opgehaald uit de lijst en voor het toevoegen van items door op het pluspictogram (+) te klikken of te tikken.
* Het **detail**scherm: voor het weergeven van meer informatie over een item en waar u het item kunt verwijderen of bewerken.
* Het scherm voor **bewerken/maken**: waar u een bestaand item bewerkt of een nieuw item maakt.

Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.

![Schakelen tussen weergaven](./media/learning-case-app-generate/toggle-view.png)

Klik of tik op een miniatuur om de besturingselementen in het betreffende scherm weer te geven.

![De gegenereerde app](./media/learning-case-app-generate/finished-app.png)

Vervolgens gaan we de app nader verkennen en deze later aanpassen zodat hij beter aansluit op onze behoeften.

