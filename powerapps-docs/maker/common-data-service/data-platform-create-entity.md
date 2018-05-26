---
title: Snelstartgids voor het maken van een aangepaste entiteit | Microsoft Docs
description: In deze snelstartgids leert u hoe u een aangepaste entiteit in PowerApps kunt maken.
author: Mattp123
ms.service: powerapps
ms.component: cds
ms.topic: quickstart
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: 66c96f7496266e03491e404de2bb329f82b6a2bf
ms.sourcegitcommit: 3f5adf07cac1c798f3d4843ed5928505becde30e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/26/2018
---
# <a name="quickstart-create-a-custom-entity"></a>Snelstartgids: Een aangepaste entiteit maken
In PowerApps definieert een *entiteit* de gegevens die u wilt bijhouden in de vorm van records, waaronder doorgaans eigenschappen zoals de bedrijfsnaam, locatie, producten, e-mailadres en telefoonnummer. Vervolgens kunt u die gegevens weergeven door een app te ontwikkelen die naar de entiteit verwijst. PowerApps biedt kant-en-klare standaardentiteiten die geschikt zijn voor gebruikelijke scenario's binnen een organisatie (zoals het volgen van afspraken), maar er zijn situaties waarin u wellicht aangepaste entiteiten wilt maken om specifieke gegevens van uw organisatie op te slaan.

In deze snelstartgids leert u hoe u de aangepaste entiteit Productbeoordeling maakt, die u kunt gebruiken om een app te maken waarin beoordelingen en opmerkingen worden weergegeven voor producten die door uw bedrijf worden verkocht.

## <a name="prerequisites"></a>Vereisten
Als u de stappen in deze snelstartgids wilt volgen, zijn de volgende items vereist:
* Een licentie voor PowerApps Plan 2 óf voor Microsoft Flow Plan 2. U kunt zich ook aanmelden voor een [gratis proefversie van een PowerApps-abonnement 2](https://web.powerapps.com/signup?redirect=marketing&email=).
* Ofwel de beveiligingsrol van systeembeheerder of systeemaanpasser binnen Common Data Service voor apps.

## <a name="sign-in-to-powerapps"></a>Meld u aan bij PowerApps
Meld u aan bij PowerApps in [https://web.powerapps.com]([https://web.powerapps.com).

## <a name="create-an-entity"></a>Een entiteit maken
1. Klik of tik in het navigatiedeelvenster op **Gegevens** om de sectie uit te vouwen en klik of tik vervolgens op **Entiteiten**.

    ![Lijst met entiteiten en de bijbehorende details](./media/data-platform-cds-create-entity/entitylist.png "Entiteitenlijst")

2. Klik of tik in de opdrachtbalk op **Nieuwe entiteit**.

    Voordat u een entiteit maakt, moet u de [entiteitsreferentie](../../developer/common-data-service/reference/about-entity-reference.md) bekijken voor een beschrijving van beschikbare standaardentiteiten. Deze entiteiten zijn bedoeld voor gebruikelijke scenario's. Als een van deze entiteiten in de huidige vorm of na enkele kleine aanpassingen aan uw vereisten voldoet, bespaart u zichzelf tijd door met die entiteit te beginnen. 

3. Voer in het deelvenster **Nieuwe entiteit** in het vak **Weergavenaam** de naam **Productbeoordeling** in en voer vervolgens een beschrijving in (optioneel; een beschrijving is nuttig als anderen deze entiteit gaan gebruiken). Andere velden in het deelvenster worden automatisch ingevuld, zoals hieronder wordt beschreven. Klik op **Volgende** zodra u klaar bent.

    * **Weergavenaam in meervoud**: dit veld wordt automatisch ingevuld wanneer u een weergavenaam invult, maar u kunt dit desgewenst wijzigen. De weergavenaam in meervoud is de naam van de entiteit in de Common Data Service WebAPI. Deze naam wordt gebruikt wanneer u vanuit PowerApps of Flow met deze entiteit werkt.
    * **Naam**: dit veld wordt ook automatisch ingevuld wanneer u een weergavenaam invoert. Het voorvoegsel is ingesteld op het moment dat de omgeving is gemaakt en zorgt ervoor dat de entiteiten die u maakt, kunnen worden geëxporteerd en geïmporteerd naar andere omgevingen zonder conflicten met andere entiteitsnamen. U kunt dit voorvoegsel wijzigen door het voorvoegsel van de uitgever van de Common Data Service-standaardoplossing bij te werken. Als u fouten met bestaande apps wilt voorkomen, moet u de naam niet wijzigen nadat u de entiteit hebt opgeslagen.
     
    ![Nieuwe entiteit](./media/data-platform-cds-create-entity/newentitypanel.png "deelvenster Nieuwe entiteit")

4. Klik of tik op de pagina met entiteitsdetails op het veld **Primaire naam** om het deelvenster **Primaire naam** te openen. Vervang daarna in het vak **Weergavenaam** de optie **Primaire naam** door **Productbeoordeling**. In het vak **Naam** vervangt u **Primaire naam** door **Productbeoordeling**. Klik of tik daarna op **Gereed**.
 
    Elke entiteit bevat standaard het veld Primaire naam, die voor opzoekvelden wordt gebruikt wanneer er relaties met andere entiteiten tot stand worden gebracht. In het veld Primaire naam wordt doorgaans de naam of primaire beschrijving opgeslagen van de gegevens die in de entiteit zijn opgeslagen. U kunt de naam en de weergavenaam van het veld Primaire naam bijwerken voordat u de entiteit voor de eerste keer opslaat.

    ![Details entiteit](./media/data-platform-cds-create-entity/newentitydetails.png "Details nieuwe entiteit")

5. U kunt als volgt een veld aan de entiteit toevoegen:
 
    a. Klik of tik in de opdrachtbalk op **Veld toevoegen** om het deelvenster **Veldeigenschappen** te openen.

    b. Voer in het vak **Weergavenaam** de **beoordelingsdatum** in.

    c. Kies in de vervolgkeuzelijst **Gegevenstype** de optie **Alleen datum**.

    d. Klik of tik op het selectievakje **Vereist**.
    
    e. Klik of tik op **Gereed**.
     
    Zie [Manage fields in an entity](data-platform-manage-fields.md) (Velden in een entiteit beheren) voor meer informatie.

    ![Nieuw veld](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Deelvenster Nieuw veld")

6. Herhaal de vorige stappen om nog drie velden toe te voegen met de volgende configuratie:
    * **Weergavenaam** = Productbeoordeling; **Gegevenstype** = geheel getal; klik of tik op het selectievakje **Vereist**
    * **Weergavenaam** = Naam beoordelaar; **Gegevenstype** = tekst
    * **Weergavenaam** = Opmerking van beoordelaar; **Gegevenstype** = tekst

    Als u klaar bent, moet de pagina met entiteitsdetails vijf velden bevatten.

    ![Veldenlijst](./media/data-platform-cds-create-entity/addedfields.png "Lijst met velden")

    Alle entiteiten hebben systeemvelden die alleen-lezen zijn. Standaard worden systeemvelden niet weergegeven in de lijst met velden, hoewel ze zich wel in de entiteit bevinden. Voor een overzicht van alle velden kunt u het filter in de opdrachtbalk wijzigen van **Standaard** in **Alles**. Zie [Metagegevens van entiteiten](../../developer/common-data-service/entity-metadata.md) voor meer informatie over de metagegevens die zijn gerelateerd aan een entiteit.

7. Klik op **Entiteit opslaan**om uw entiteit op te slaan en om deze beschikbaar te maken voor gebruik in apps.

    De entiteit Productbeoordeling moet in de lijst met entiteiten in uw database worden weergegeven. Als u deze entiteit niet ziet staan, kunt u het filter in de opdrachtbalk wijzigen van **Standaard** naar **Aangepast**.

    ![Filter](./media/data-platform-cds-create-entity/filter.png "Selectie filteren")

## <a name="next-steps"></a>Volgende stappen
In deze snelstartgids hebt u geleerd hoe u de aangepaste entiteit Productbeoordeling maakt, die u kunt gebruiken om een app te maken waarin beoordelingen en opmerkingen worden weergegeven voor elk product dat door een specifiek bedrijf wordt verkocht. Hierna kunt u leren hoe u relaties tussen entiteiten definieert (in dit geval tussen de standaardentiteit Product en uw aangepaste entiteit Productbeoordeling), zodat u elk product kunt koppelen aan de beoordelingen en opmerkingen die u ervoor ontvangt.

> [!div class="nextstepaction"]
> [Een relatie maken](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard. We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die door app-makers worden gemaakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
