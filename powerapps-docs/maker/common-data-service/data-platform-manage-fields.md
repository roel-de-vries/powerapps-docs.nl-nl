---
title: Aangepaste velden in een entiteit beheren | Microsoft Docs
description: 'Leer hoe u aangepaste velden maakt, leest, bijwerkt en verwijdert in een entiteit in Common Data Service (CDS) voor Apps.'
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="manage-custom-fields-in-an-entity"></a>Aangepaste velden in een entiteit beheren
U kunt een of meer aangepaste velden in een entiteit maken en bijwerken. Als u een aangepast veld maakt, geeft u een aantal eigenschappen op, bijvoorbeeld de naam en de weergavenaam van het veld, en het type gegevens dat het kan bevatten. Zie voor meer informatie [Metagegevens entiteitkenmerk](../../developer/common-data-service/entity-attribute-metadata.md).

> [!NOTE]
> Elke entiteit bevat systeemvelden, zoals velden die aangeven wanneer een record voor het laatst is bijgewerkt en door wie dit is gedaan. Daarnaast bevatten standaardentiteiten standaardvelden. U kunt systeemvelden en standaardvelden niet wijzigen of verwijderen. Als u een aangepast veld maakt, moet dit naast deze ingebouwde velden extra functionaliteit bieden.

## <a name="create-a-field"></a>Een veld maken
1. Vouw in [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsdetails](./media/data-platform-cds-create-entity/entitylist.png "Entiteitenlijst")

2. Klik of tik op een bestaande entiteit of kies ervoor [Een nieuwe entiteit te maken](data-platform-create-entity.md)

3. Voeg een nieuw veld aan uw entiteit toe door op **Veld toevoegen** te klikken.

4. Voer in het deelvenster Nieuw veld de **weergavenaam** voor het veld in. De **naam** wordt automatisch ingevuld en wordt gebruikt als de unieke naam voor het veld. De **weergavenaam** wordt gebruikt wanneer dit veld aan uw gebruikers wordt gepresenteerd. De **naam** wordt gebruikt bij het bouwen van uw app, in expressies en formules.

    > [!NOTE]
    > De velden **Weergavenaam** kunnen op elk gewenst moment worden bijgewerkt zodat deze anders worden weergegeven in uw apps. Het veld **Naam** kan niet worden gewijzigd nadat de entiteit is opgeslagen, aangezien dit kan leiden tot het verbreken van een bestaande app.

    ![Nieuw veld](./media/data-platform-cds-create-entity/newfieldpanel.png "Paneel Nieuw veld")

5. Selecteer het **gegevenstype** van het veld. Hiermee bepaalt u de manier waarop de informatie wordt opgeslagen en in apps wordt aangeboden. Tekst wordt bijvoorbeeld anders opgeslagen dan een decimaal getal of een URL. Zie [Metagegevens entiteitkenmerk](../../developer/common-data-service/entity-attribute-metadata.md) voor meer gedetailleerde informatie over de beschikbare gegevenstypen.

    Wanneer u daarom wordt gevraagd, geeft u aanvullende informatie op over het opgegeven gegevenstype. Afhankelijk van het gegevenstype worden verschillende velden weergegeven. Als u een veld maakt van het type Optieset of Optieset voor meervoudige selectie, kunt u **Nieuwe optieset** selecteren en een nieuwe optieset maken tijdens het maken van het veld. Zie [Een optieset maken](custom-picklists.md) voor meer informatie

    ![Nieuw veld](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Paneel Nieuw veld")


7. Onder **Vereist** schakelt u het selectievakje in als u dit veld als vereist wilt aanbevelen in uw apps. Dit biedt geen strikte afdwinging via alle verbindingen met Common Data Service. Als u wilt controleren of het veld wordt ingevuld, maakt u een [bedrijfsregel](data-platform-create-business-rule.md).

8. Schakel onder **Doorzoekbaar** het selectievakje in als u wilt dat dit veld beschikbaar is in Weergaven, Diagrammen, Dashboards en Geavanceerd zoeken. In de meeste gevallen moet dit selectievakje zijn ingeschakeld.

9. Klik of tik op **Gereed** om het deelvenster Veld te sluiten en terug te keren naar de entiteit. U kunt stap 3 tot 9 herhalen voor elk extra veld.
   
    > [!IMPORTANT]
    > Het veld wordt pas opgeslagen en gemaakt als u de wijzigingen in de entiteit hebt opgeslagen.

10. Klik of tik op **Entiteit opslaan** om uw wijzigingen te voltooien en deze op te slaan in Common Data Service.

    Er wordt een bericht weergegeven wanneer de bewerking is voltooid. Als de bewerking is mislukt, wordt een foutbericht weergegeven met de problemen die zijn opgetreden, zodat u die kunt corrigeren.

## <a name="create-a-calculated-or-roll-up-field"></a>Een berekend of samengeteld veld maken
Met berekende velden kunt u handmatige berekeningen automatiseren die in uw bedrijfsprocessen worden gebruikt. Een verkoper wil bijvoorbeeld weten wat de gewogen opbrengst van een verkoopkans is, die wordt gebaseerd op de geschatte opbrengst van een verkoopkans, vermenigvuldigd met de waarschijnlijkheid. Of, zij willen automatisch een korting toepassen als een order groter is dan $500. Een berekend veld kan waarden bevatten die het resultaat zijn van simpele berekeningen of voorwaardelijke bewerkingen, zoals groter dan, Als-Anders, enzovoort. Berekende velden kunnen worden gemaakt met behulp van de volgende gegevenstypen:

* Enkele regel tekst
* Optieset
* Twee opties
* Geheel getal
* Decimaal getal
* Valuta
* Datum en tijd

Zie [Berekende velden definiëren](/dynamics365/customer-engagement/customize/define-calculated-fields) voor meer informatie over de verschillende typen expressies die worden ondersteund en voor voorbeelden

## <a name="update-or-delete-a-field"></a>Een veld bijwerken of verwijderen
1. Vouw op [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit, klik of tik op **Entiteiten** in het linkernavigatiedeelvenster en klik of tik op een entiteit.
2. Klik of tik in de lijst met velden voor de geselecteerde entiteit op een veld en volg een van de volgende twee stappen:
   
   * Wijzig een of meer eigenschappen van het veld.
   * Verwijder het veld door op het bijbehorende beletselteken (…) aan de rechterkant van het veld te klikken of tikken en vervolgens op **Verwijderen** te klikken of tikken.

3. Klik of tik op **Entiteit opslaan** om de wijzigingen te verzenden.
   
    > [!IMPORTANT]
    > De wijzigingen gaan verloren als u ze niet opslaat voordat u een andere pagina in de browser opent of de browser sluit.

    Er wordt een bericht weergegeven wanneer de bewerking is voltooid. Als de bewerking is mislukt, wordt een foutbericht weergegeven met de problemen die zijn opgetreden, zodat u die kunt corrigeren.

## <a name="best-practices-and-restrictions"></a>Aanbevolen procedures en beperkingen
Houd bij het maken en wijzigen van velden rekening met het volgende:

* U kunt systeemvelden of hun waarden niet wijzigen of verwijderen.
* In een standaardentiteit kunt u geen standaardveld wijzigen of verwijderen, een veld toevoegen waarvoor gegevens vereist zijn of een andere wijziging aanbrengen waardoor een app die van die entiteit afhankelijk is, defect kan raken.
* Bij een aangepaste entiteit moet u ervoor zorgen dat een app die van die entiteit afhankelijk is, niet defect kan raken door eventuele wijzigingen.
* Geef elk aangepast veld een naam die uniek is binnen die entiteit. U kunt de naam van een eenmaal gemaakt veld niet wijzigen.

## <a name="next-steps"></a>Volgende stappen
* [Relaties tussen entiteiten definiëren](data-platform-entity-lookup.md)
* [Een bedrijfsregel maken](data-platform-create-business-rule.md)
* [Een app maken met behulp van entiteiten](../canvas-apps/data-platform-create-app.md)
* [Een compleet nieuwe app maken met behulp van een Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken deze informatie om het algemene gegevensmodel voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, worden door Microsoft niet geopend of gebruikt en worden niet buiten de regio gerepliceerd waarin de database wordt geleverd. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht aan de bescherming van uw privacy, zoals nader wordt beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

