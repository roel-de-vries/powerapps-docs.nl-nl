---
title: Een aangepaste entiteit maken | Microsoft Docs
description: Meer informatie over het maken van een aangepaste entiteit in PowerApps.
author: Mattp123
ms.service: powerapps
ms.component: cds
ms.topic: quickstart
ms.date: 05/01/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-custom-entity"></a>Een aangepaste entiteit maken
In PowerApps wordt met een *entiteit* gegevens gedefinieeerd die u in de vorm van records wilt bijhouden. Dit omvat meestal eigenschappen zoals bedrijfsnaam, locatie, producten, e-mail en telefoon. U kunt vervolgens die gegevens gebruiken door een app te ontwikkelen die naar de entiteit verwijst. PowerApps biedt standaard gebruiksklare entiteiten om veelgebruikte scenario's in een organisatie (zoals het bijhouden van afspraken) te behandelen, maar soms moet u aangepaste entiteiten maken om gegevens op te slaan die specifiek voor uw organisatie zijn.

In dit onderwerp leert u hoe u een aangepaste entiteit maakt met de naam Productcontrole die u kunt gebruiken om een app te maken waarmee beoordelingen en opmerkingen worden weergegeven voor producten bevat die uw bedrijf verkoopt.

## <a name="prerequisites"></a>Vereisten
Als u deze procedure wilt volgen, zijn de volgende items nodig:
* Een PowerApps Plan 2- of Microsoft Flow Plan 2-licentie. U kunt u ook registreren voor een [gratis PowerApps Plan 2-proefversie](https://web.powerapps.com/signup?redirect=marketing&email=)
* Een beveiligingsrol van systeembeheerder of systeemaanpasser in Common Data Service voor Apps.

## <a name="sign-in-to-powerapps"></a>Aanmelden bij PowerApps
Aanmelden bij PowerApps via [https://web.powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-an-entity"></a>Een entiteit maken
1. Klik of tik in het navigatiedeelvenster op **Gegevens** om deze uit te vouwen en klik of tik vervolgens op **Entiteiten**.

    ![Lijst met entiteiten en de bijbehorende details](./media/data-platform-cds-create-entity/entitylist.png "Entiteitenlijst")

2. Klik of tik op de opdrachtbalk op **Nieuwe entiteit**.

    Voordat u een entiteit maakt, raadpleegt u [entiteitsverwijzing](../../developer/common-data-service/reference/about-entity-reference.md) voor een beschrijving van beschikbare standaardentiteiten. Deze entiteiten behandelen typische scenario's. Als een van deze entiteiten ongewijzigd of na kleine wijzigingen aan uw behoeften voldoet, kunt u tijd besparen door met deze entiteit te beginnen. 

3. Voer in het paneel **Nieuwe entiteit**, in het vak **Weergavenaam** **Productcontrole** in en voer vervolgens desgewenst een beschrijving in (beschrijvingen zijn handig als andere mensen deze entiteit gebruiken). Andere velden in het paneel worden automatisch ingevuld, zoals hieronder wordt beschreven. Klik op **Volgende** als u gereed bent.

    * **Meervoudsweergavenaam** - dit veld wordt automatisch ingevuld als u een weergavenaam invoert, maar u kunt deze naam desgewenst wijzigen. De meervoudsweergavenaam is de naam van de entiteit in de Common Data Service-WebAPI en wordt gebruikt wanneer met deze entiteit wordt gewerkt vanuit PowerApps of Flow.
    * **Naam** - dit veld wordt ook automatisch ingevuld als u een weergavenaam invoert. Het voorvoegsel is ingesteld toen de omgeving werd gemaakt en zorgt ervoor dat de entiteiten die u maakt, in andere omgevingen kunnen worden geëxporteerd en geïmporteerd zonder te conflicteren met andere entiteitsnamen. U kunt dit voorvoegsel wijzigen door het voorvoegsel in uw uitgever voor de Common Data Service-standaardoplossing bij te werken. Als u wilt voorkomen dat bestaande apps worden onderbroken, kunt u de naam wijzigen nadat de entiteit is opgeslagen.
     
    ![Nieuwe entiteit](./media/data-platform-cds-create-entity/newentitypanel.png "Paneel Nieuwe entiteit")

4. Klik of tik op de pagina met entiteitsdetails op het veld **Primaire naam** om het paneel **Primaire naam** te openen en vervang vervolgens in het vak **Weergavenaam** **Primaire naam** door **Productcontrole**. Vervang in het vak **Naam** **PrimaryName** door **ProductReview** en klik of tik vervolgens op **Gereed**.
 
    Elke entiteit bevat standaard een veld voor primaire naam. Dit veld wordt gebruikt door opzoekvelden bij het instellen van relaties met andere entiteiten. Meestal wordt in het veld Primaire naam de naam of de primaire beschrijving opgeslagen van de gegevens die de entiteit bevat. U kunt de naam en de weergavenaam van het veld Primaire naam bijwerken voordat u de entiteit voor de eerste keer opslaat.

    ![Entiteitsdetails](./media/data-platform-cds-create-entity/newentitydetails.png "Nieuwe entiteitsdetails")

5. Als u een veld wilt toevoegen aan de entiteit, doet u het volgende:
 
    a. Klik of tik in de opdrachtbalk op **Veld toevoegen** om het paneel **Veldeigenschappen** te openen.

    b. Voer in het vak **Weergavenaam** **Controledatum** in.

    c. Selecteer in de vervolgkeuzelijst **Gegevenstype** **Alleen datum**.

    d. Klik of tik op het selectievakje **Vereist**.
    
    e. Klik of tik op **Gereed**.
     
    Zie voor meer informatie [Velden beheren in een entiteit](data-platform-manage-fields.md).

    > [!div class="mx-imgBorder"] 
    > ![Nieuw veld](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Paneel Nieuw veld")

6. Herhaal de voorgaande stap om nog drie velden met de volgende configuraties toe te voegen:
    * **Weergavenaam** = Productbeoordeling; **Gegevenstype** = Geheel getal. Klik of tik op het selectievakje **Vereist**
    * **Weergavenaam** = Naam controleur; **Gegevenstype** = Tekst
    * **Weergavenaam** = Opmerking controleur; **Gegevenstype** = Tekst

    Wanneer u gereed bent, dienen er vijf velden op uw pagina met entiteitsdetails te worden weergegeven.

    ![Lijst met velden](./media/data-platform-cds-create-entity/addedfields.png "Lijst met velden")

    Alle entiteiten hebben alleen-lezensysteemvelden. Standaard worden de systeemvelden niet weergegeven in de lijst met velden, ook niet als ze in de entiteit aanwezig zijn. Als u alle velden wilt zien, wijzigt u het filter op de opdrachtbalk van **Standaard** in **Alle**. Zie voor meer informatie over de metagegevens die aan een entiteit zijn gerelateerd [Entiteitsmetagegevens](../../developer/common-data-service/entity-metadata.md).

7. Klik op **Entiteit opslaan** om uw entiteit op te slaan en beschikbaar te maken voor gebruik in apps.

    De entiteit Productcontrole moet in de lijst met entiteiten in uw database worden weergegeven. Als u de entiteit niet ziet, wijzigt u het filter op de opdrachtbalk van **Standaard** in **Aangepast**.

    > [!div class="mx-imgBorder"] 
    > ![Filter](./media/data-platform-cds-create-entity/filter.png "Filterselectie")

## <a name="next-steps"></a>Volgende stappen
In dit onderwerp hebt u geleerd hoe u een aangepaste entiteit maakt met de naam Productcontrole die u kunt gebruiken om een app te maken waarmee beoordelingen en opmerkingen worden weergegeven voor elk product dat door een bepaald bedrijf is verkocht. Vervolgens hebt u geleerd om de relaties tussen entiteiten te definiëren (in dit geval de standaardentiteit Product en uw aangepaste entiteit Productcontrole) zodat u elk product kunt koppelen aan de controles en opmerkingen die worden ontvangen.

> [!div class="nextstepaction"]
> [Een relatie maken](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard. We gebruiken deze informatie om het algemene gegevensmodel voor onze klanten te verbeteren. De entiteits- en veldnamen die de app Creators maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, worden door Microsoft niet geopend of gebruikt en worden niet buiten de regio gerepliceerd waarin de database wordt geleverd. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht aan de bescherming van uw privacy, zoals nader wordt beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
