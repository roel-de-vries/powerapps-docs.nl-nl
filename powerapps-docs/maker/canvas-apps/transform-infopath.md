---
title: Uw InfoPath-formulier transformeren in een canvas-app | Microsoft Docs
description: Begin met het transformeren van uw InfoPath-formulier in PowerApps met informatie over veelvoorkomende scenario's en het maken van deze items in een canvas-app.
author: richardriley99
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/05/2018
ms.author: rriley
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3e17015c05d23f4bd9f8a0906e7b1d9d00e2c38f
ms.sourcegitcommit: 6e2fa2665ded6ac6fd271e1a12f4e3227ebc8865
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2018
ms.locfileid: "48246046"
---
# <a name="transform-your-infopath-form-to-powerapps"></a>Uw InfoPath-formulier transformeren in PowerApps

Maakt u geweldige dingen in InfoPath en wilt u weten hoe u deze op een robuuster platform kunt leveren?

## <a name="key-advantages-of-powerapps-over-infopath"></a>Belangrijke voordelen van PowerApps ten opzichte van InfoPath

Net als de meeste InfoPath-hoofdgebruikers maakt u al een tijdje mooie formulieren. U bent zeer tevreden met de formulieren, maar u kent ook hun beperkingen: de &quot;klassieke&quot; weergave die niet optimaal overkomt op mobiele apparaten, de onzekerheid of u uw formulieren ook in de toekomst kunt blijven gebruiken en het feit dat u altijd code moet schrijven om verbinding te maken met andere services.

Het PowerApps-team heeft kennisgenomen van deze en vele andere uitdagingen. Ze hebben hard gewerkt om een betere ervaring te realiseren en u in staat te stellen om canvas-apps te maken door gebruik te maken van uw zakelijke en technologische vaardigheden. Met PowerApps kunt u snel de juiste bedrijfsoplossingen ontwikkelen en implementeren zonder code te schrijven.

**PowerApps voor een krachtige toekomst**  
PowerApps is een SaaS-platform (Software-as-a-Service) waarmee u snel werkende apps kunt bouwen die u online kunt implementeren of die u kunt implementeren naar SharePoint, Dynamics 365, Teams, Power BI of mobiele apparaten, zonder extra stappen. En doordat de apps zo eenvoudig te implementeren zijn (u geeft alleen de URL naar de gepubliceerde app door), zijn ze ook heel eenvoudig bij te werken.

**Uw apps delen**  
Hebt u ooit geprobeerd een app te bouwen en deze vervolgens te publiceren voor iOS- of Android-apparaten? Dat is ingewikkeld. Als u een tweede app wilt implementeren of de bestaande app wilt bijwerken, moeten uw gebruikers veel meer stappen doorlopen. Niet met PowerApps. Uw gebruikers installeren PowerApps Mobile op hun apparaat en melden zich aan. Nu beschikken ze over alle functionele apps die u met hen hebt gedeeld. Als u deze apps bijwerkt of nieuwe apps pusht, verschijnen deze direct op de apparaten van gebruikers. Als u mobiele apps kunt gebruiken zonder apparaten te hoeven beheren, hebben zowel u als uw bedrijf daar baat bij.

**Mobiliteit**  
Met PowerApps kunt u gebruikmaken van de kracht van het mobiele apparaat van de gebruiker. U hebt toegang tot versnelling, de camera, het kompas, de verbindingsgegevens en locatiesignalen, direct vanuit uw app. Hiermee opent u een hele wereld aan mogelijkheden voor het bouwen van apps om mee te werken. Uiteraard is de aanraakfunctionaliteit geheel automatisch in PowerApps, zodat u hiervoor niets extra's hoeft te programmeren.

**Direct aan de slag**  
Met InfoPath werkt u normaal gesproken met gegevens uit één bron. Het werd echter ingewikkeld als u graag een andere bron wilde bijwerken (zoals een SharePoint-lijst in een andere siteverzameling) of als u verbinding wilde maken met externe services. U kon wakker liggen van zaken zoals de benodigde code. Met PowerApps kunt u met meerdere gegevensbronnen en serviceverbindingen in één app werken. Op dit moment bieden [meer dan 200 connectors](connections-list.md#all-standard-connectors) ondersteuning voor een combinatie van on-premises en cloudgegevens middels Microsoft Office 365 en Azure-services zoals Microsoft Flow en Dynamics 365. U kunt ook verbinding maken met verschillende services van derden, zoals Dropbox, Google, Salesforce, Slack en andere populaire bestemmingen.

U kunt oplossingen bouwen om deze te schalen waar de gebruikers ze nodig hebben, niet waar de oorspronkelijke gegevens staan.

## <a name="powerapps-and-sharepoint-even-better-together"></a>PowerApps en SharePoint: samen nog beter

PowerApps is een uitstekende tool om uw SharePoint-ervaring op twee manieren nog beter te maken. U kunt de formulieren voor een SharePoint-lijst aanpassen of een zelfstandige app maken om met SharePoint-gegevens te werken.

**Een SharePoint-formulier aanpassen** is handig als u wilt aanpassen hoe gebruikers items toevoegen, bekijken of bewerken in een lijst die ze voor hun dagelijkse werkzaamheden gebruiken. Als u op **Formulieren aanpassen** klikt, maakt u een &quot;formulieren-app&quot; met één scherm waarin de modi (nieuw, bewerken, weergeven) worden gewijzigd op basis van de context. SharePoint beheert deze apps. De machtigingen voor deze apps zijn hetzelfde als de lijst met machtigingen voor bewerken of weergeven.

**Als u een PowerApps-canvas-app maakt in SharePoint**, kunt u de app zelfstandig uitvoeren op een mobiel apparaat. U kunt de app ook insluiten in een SharePoint-pagina. Als u hierop klikt, wordt er een app met drie schermen gemaakt (bladerlijst, details weergeven en een item maken/bijwerken). Het machtigingsmodel/model voor het delen van deze apps is niet gekoppeld aan SharePoint, maar wordt in plaats daarvan beheerd door PowerApps.

Dit is het verschil tussen de twee opties. In het volgende gedeelte vindt u een overzicht van het gebruik van beide opties.

## <a name="sharepoint-forms"></a>SharePoint-formulieren

Het PowerApps-team en het SharePoint-team hebben samen gewerkt aan een nieuwe manier om formulieren aan te passen voor gebruik met SharePoint. Als u hetzelfde bent als de meeste InfoPath-ontwikkelaars, weet u dat InfoPath samenwerkt met SharePoint. SharePoint is geweldig, maar de standaardformulieren zijn enigszins gewoontjes. Zonder InfoPath kunt u de formulieren niet aanpassen of er bedrijfslogica mee uitvoeren. Dat is verleden tijd.

Met PowerApps kunt u nu uw lijstformulieren aanpassen met systeemeigen functionaliteit. Op deze manier kunt u optimaal gebruikmaken van de kracht van PowerApps. In de onderstaande schermafbeelding ziet u een voorbeeld van een PowerApps-formulier met een ingesloten Power BI-rapport. Deze oplossing is in zijn geheel in minder dan 15 minuten opgezet.

![SharePoint-integratie](./media/transform-infopath/sharepoint-integration.png)

Een andere belangrijke functie van PowerApps is de mogelijkheid om eenvoudig verbinding te maken met een andere SharePoint-siteverzameling of een andere omgeving uit hetzelfde formulier. Wilt u bijvoorbeeld een formulier maken dat de gegevens van uw SharePoint Online en SharePoint on-premises omgeving tegelijkertijd weergeeft en bijwerkt? Geen probleem. Als u de [on-premises gegevensgateway](gateway-management.md) installeert, kunt u binnen enkele minuten aan de slag en PowerApps, Power BI, Microsoft Flow en Azure Logic Apps verbinden met uw on-premises gegevens. Er hoeven geen wijzigingen te worden aangebracht aan de firewallregels. U kunt nog een stap verder gaan en deze app koppelen aan Microsoft Flow.

## <a name="a-standalone-sharepoint-app"></a>Een zelfstandige SharePoint-app

Als u in plaats van alleen de lijstformulieren bijwerken een volledig zelfstandige app wilt bouwen op basis van uw SharePoint-gegevens, kunt u deze techniek gebruiken. Dit is ook de beste manier om aan de slag te gaan. U kunt uzelf vertrouwd maken met het PowerApps-canvas en apps bouwen met verschillende gegevensbronnen.

Volg deze stappen om aan de slag te gaan:

1. Open de SharePoint-lijst die u wilt gebruiken om een app te bouwen.
1. Selecteer in de menubalk **PowerApps** en selecteer vervolgens **Een app maken**.
1. Geef een naam op en selecteer dan **Maken**.

PowerApps bouwt dan een app die u kunt aanpassen.

Begin voor uw eerste app met een eenvoudige aangepaste lijst met een paar verschillende veldtypen. Op deze manier maakt u een solide basis. En geen zorgen, u bent al snel een professional die ook complexe apps zonder moeite aankan. Bekijk de volgende [documentatie](generate-app-from-sharepoint-list-interface.md) of deze [community-video](https://youtu.be/BnYe_7fpZRM) om aan de slag te gaan met uw eerste app. In de voorbeelden hieronder ziet u algemene InfoPath-taken en leert u hoe u deze uitvoert in PowerApps. Er wordt steeds gewerkt met een eenvoudige SharePoint-app met lijsten.

## <a name="how-do-you-do-that-with-powerapps"></a>Hoe u dit doet met PowerApps?

Nu u de basisbeginselen onder de knie hebt, gaan we een stapje verder. In het volgende gedeelte ziet u hoe u enkele algemene InfoPath-concepten toepast in PowerApps.

**Een veld dat is gebaseerd op een waarde verbergen, weergeven of vergrendelen**  
Bij formulieren die uitstekend werken, wordt er in de meeste gevallen gebruikgemaakt van sterke bedrijfslogica, door bijvoorbeeld de status van een veld te wijzigen op basis van een waarde of actie. U kunt met PowerApps de eigenschap **DisplayMode** van een besturingselement instellen op **Bewerken** of **Weergeven** om op te geven of een gebruiker het veld mag wijzigen. U kunt ook een eenvoudige **If**-formule gebruiken om dit voorwaardelijk af te handelen. Selecteer om te beginnen de kaart die u wilt bewerken en selecteer dan het slotpictogram. Met deze stap wordt de kaart ontgrendeld zodat u de waarde kunt wijzigen.

![Gegevenskaarten verbergen, weergeven of vergrendelen](./media/transform-infopath/hide-show-lock.png)

Schuif in het rechterdeelvenster naar de eigenschap **DefaultMode** om deze te bewerken.

![If Else-instructie-expressies](./media/transform-infopath/if-else-statement.png)

In dit voorbeeld is gebruikgemaakt van een **If**-formule:

```If(ThisItem.Color = "Blue", DisplayMode.View, DisplayMode.Edit)```

Met deze formule wordt aangegeven dat als de waarde van het veld **Kleur** van het huidige item **Blauw** is, het veld **Dieren** alleen-lezen wordt. In alle andere gevallen kan het veld gewoon worden bewerkt.

Als u de kaart wilt verbergen in plaats van deze alleen-lezen te maken, voegt u een vergelijkbare functie toe in de eigenschap **Zichtbaar** rechts boven **DisplayMode**.

U kunt bijvoorbeeld ook spelen met het weergeven van een goedkeuringsknop (maar dan alleen als het e-mailadres van de gebruiker overeenkomt met het e-mailadres van de fiatteur). (Hint: met **User().Email** hebt u toegang tot het e-mailadres van de huidige gebruiker.) U kunt het e-mailadres van de fiatteur bijvoorbeeld opslaan in **YourDataCard** en dan de eigenschap **Zichtbaar** van de knop instellen op deze formule:

```If(YourDataCard.Text = User().Email, true, false)```

**Voorwaardelijke opmaak**  
Op een vergelijkbare manier als hierboven, waarin u het veld verborgen hebt, kunt u ook visuele feedback aan gebruikers geven. Mogelijk wilt u tekst rood markeren als de opgegeven waarde buiten het aanvaardbare bereik valt of de tekst en kleur van de uploadknop wijzigen nadat een gebruiker een bestand heeft geüpload. U kunt dit allebei doen door een functie te gebruiken, zoals **If**, in eigenschappen zoals **Kleur** en **Zichtbaar**.

U kunt bijvoorbeeld de **If**-functie koppelen aan de [IsMatch](functions/function-ismatch.md)-functie om de tekstkleur van het e-mailveld te wijzigen in rood als de gebruiker geen juist opgemaakt e-mailadres in het invoervak heeft ingevoerd. U doet dit door de waarde **Kleur** van **TextInput1** (hier voert de gebruiker een e-mailadres in) in te stellen op de volgende formule:

```If(IsMatch(TextInput1.Text, Email), Black, Red)```

**IsMatch** ondersteunt tal van vooraf gedefinieerde patronen, zoals Email, maar u kunt ook uw eigen patronen maken. Bekijk deze [community-video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Conditional-Formatting-and-Popups/m-p/84962) voor meer informatie over voorwaardelijke opmaak.

**Beveiliging op basis van rollen implementeren**  
De eerste functie waarover u moet nadenken is [DataSourceInfo](functions/function-datasourceinfo.md). De informatie die wordt geretourneerd uit de gegevensbron kan verschillen, maar vaak kunt u deze formule gebruiken om te controleren of de gebruiker toegang heeft tot de gegevens om deze te bewerken (vervang *YourDataSource* door de naam van uw gegevensbron):

```DataSourceInfo(YourDataSource, DataSourceInfo.EditPermission)```

Op deze manier kunt u een formulier of knop alleen weergeven als de gebruiker de gegevens kan bewerken. Bekijk de [DataSourceInfo](functions/function-datasourceinfo.md)-documentatie voor de volledige lijst met informatie die u kunt gebruiken voor een query in de functie.

Als u in plaats daarvan Active Directory-groepen wilt gebruiken voor het beheren van toegang tot de knoppen of formulieren in uw app, moet u een stapje verder gaan. Hiervoor maakt u gebruik van de flexibiliteit van PowerApps en maakt u uw eigen connector met de Microsoft Graph API. Als dat ingewikkeld klinkt, leest u dit [blogbericht](https://powerapps.microsoft.com/blog/implementing-role-based-permission/) voor stapsgewijze instructies.

**Een e-mailbericht verzenden vanuit uw app**  
U kunt op vele manieren e-mailberichten verzenden vanuit PowerApps. De eenvoudigste is om de Office 365 Outlook-connector te gebruiken. Met deze connector kunt u als uzelf berichten verzenden vanuit uw app. U kunt ook e-mailberichten en andere taken ophalen die communiceren met uw postvak. Bekijk deze [documentatie](connections/connection-office365-outlook.md) of deze community-[video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Send-an-email-from-PowerApps/m-p/74349) over het verzenden van e-mailberichten.

U kunt complexere berichten verzenden (bijvoorbeeld als onderdeel van een SharePoint-goedkeuringsstroom) door gebruik te maken van Microsoft Flow en de app te verbinden met de stroom die u maakt. Nadat u uw app met Microsoft Flow hebt verbonden, kunt u gebruikmaken van alle mogelijkheden van een werkstroomengine die net als PowerApps uitstekend is verbonden met externe gegevens en services. Raadpleeg deze [documentatie](using-logic-flows.md) om te zien hoe u met PowerApps verbinding maakt met Microsoft Flow.

Als u de gewenste e-mailoptie nog niet hebt gevonden, kunt u gebruikmaken van de PowerApps-connectors voor Benchmark Email, Gmail, MailChimp, Outlook.com, SendGrid of SMTP. Connectiviteit is hét voordeel van PowerApps.

**Werkstromen**  
Voor zakelijke apps en bedrijfslogica is onvermijdelijk een werkstroomengine nodig. Het goede nieuws is dat het PowerApps-team het wiel niet opnieuw heeft uitgevonden door een andere werkstroomengine te ontwikkelen. In plaats daarvan bieden ze een robuuste connector met de Microsoft Flow-service. Met de gebruiksvriendelijke werkstroomengine kunt u processen en taken automatiseren voor meer dan [200 verschillende services](https://flow.microsoft.com/connectors/). Raadpleeg deze [documentatie](using-logic-flows.md) om te zien hoe u met PowerApps verbinding maakt met Microsoft Flow.

**Variabelen met PowerApps**  
Wanneer u oplossingen bouwt, is het vanzelfsprekend dat u denkt dat u gebruik moet maken van variabelen. PowerApps biedt meerdere typen variabelen, maar gebruik deze alleen als dat echt nodig is. In plaats van gegevens ophalen, deze in een variabele opslaan en vervolgens te verwijzen naar de variabele, kunt u ook rechtstreeks naar deze gegevens verwijzen. U kunt dit model beter begrijpen als u dit vergelijkt met Excel. In Excel is Totaal geen variabele, het is de som van andere velden. Als u die waarde ergens anders in het werkblad wilt gebruiken, geeft u de cel op waarin u het totaal hebt berekend. In deze [documentatie](working-with-variables.md) staat een uitstekende, uitgebreide uitleg. Probeer anders te denken.

Als u toch gebruik wilt maken van een variabele (en dit kan vaak het geval zijn), kunt u hier zien hoe de verschillende opties werken. Met PowerApps hoeft u geen variabelen op te geven. U gebruikt een functie om de naam en waarde op te geven die u wilt opslaan en dan wordt uw variabele automatisch gemaakt. U vindt de variabelen die u hebt gemaakt via **Variabelen** op het tabblad **Weergave**. Variabelen worden in het geheugen opgeslagen en de waarden gaan verloren zodra u de app sluit. U kunt deze typen variabelen maken:

- U denkt waarschijnlijk het eerst aan algemene variabelen. U kunt de functie [Set](functions/function-set.md) gebruiken om een waarde op te geven voor een algemene variabele en deze beschikbaar maken in uw app:

    ```Set(YourVariable, YourValue)```

    Vervolgens kunt u in de app verwijzen naar *YourVariable*.

- Contextvariabelen zijn alleen zichtbaar in het scherm waarin ze zijn gedefinieerd. Zodra u het scherm verlaat, worden ze opnieuw ingesteld. Deze variabelen worden bijvoorbeeld vaak gebruikt om gegevens op te slaan uit een vorig scherm of om bijvoorbeeld bij te houden of het formulier is verzonden. Als een contextvariabele wilt maken, gebruikt u de functie [UpdateContext](functions/function-updatecontext.md), zoals in dit voorbeeld:

    ```UpdateContext( { Submitted: "true" } )```

    In dit voorbeeld wordt de waarde van de variabele **Submitted** ingesteld op **true**. U kunt deze formule toevoegen aan de eigenschap **OnSelect** van een verzendknop om bij te houden of de informatie is verzonden en alle velden in te stellen op alleen-lezen.

- Verzamelingen worden gebruikt om tabellen met gegevens op te slaan die afzonderlijk kunnen worden bijgewerkt. U kunt [Verzamelen](functions/function-clear-collect-clearcollect.md) gebruiken om bijvoorbeeld een winkelwagentje te maken wanneer de gebruiker verschillende SharePoint-items tagt die hij wilt verzenden. Bekijk deze community-[video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Learn-about-PowerApps-Collections/m-p/89180) om dit concept in actie te zien.

**Trapsgewijze vervolgkeuzelijsten**  
Trapsgewijze vervolgkeuzelijsten zijn enorm handig omdat u bijvoorbeeld de keuzes in de ene lijst kunt filteren op basis van de waarde die in de voorgaande lijst is geselecteerd. In PowerApps worden deze vaak gemaakt met twee gegevensbronnen in uw app. De eerste gegevensbron bevat de gegevens die u bekijkt of bijwerkt en de tweede gegevensbron bevat de waarden om het gewenste trapsgewijze effect te maken. In deze afbeelding ziet u een voorbeeld van de tweede gegevensbron met de verschillende keuzeopties.

![Trapsgewijze vervolgkeuzelijsten](./media/transform-infopath/cascading-dropdowns.png)

In dit voorbeeld zou u een vervolgkeuzelijst met de naam **ddSelectType** kunnen toevoegen en de eigenschap **Items** instellen op deze formule:

```Distinct(Impacts, Title)```

In de vervolgkeuzelijst worden alleen Cost, Program Impact en Schedule weergegeven. U zou dan een tweede vervolgkeuzelijst kunnen toevoegen en de eigenschap **Items** instellen op deze formule:

```Filter(Impacts,ddSelectType.Selected.Value in SCategory)```

Dit is een voorbeeld van hoe u een trapsgewijze vervolgkeuzelijst maakt. Bekijk voor meer informatie het volgende bericht van het PowerApps-team: [SharePoint: Cascading Dropdowns in 4 Easy Steps!](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/SharePoint-Cascading-Dropdowns-in-4-Easy-Steps/ba-p/16248) of deze [community-video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Cascading-Dropdown/m-p/92813). Geen zorgen, u kunt dit net zo gemakkelijk doen zonder SharePoint.

**Maak niet één super-app**  
Met PowerApps, kunt u via de ene app een andere app aanroepen. Dus in plaats van een uitgebreid InfoPath-formulier te maken dat met kauwgom aan elkaar hangt, kunt u een groep apps maken die elkaar aanroepen. U kunt zelfs gegevens van de ene app aan de andere doorgeven, wat het ontwikkelen nog eenvoudiger maakt.

## <a name="next-steps"></a>Volgende stappen

Met PowerApps en de informatie in dit onderwerp bent u klaar om krachtige apps te maken. Als u hier verder mee aan de slag gaat, vindt u hieronder enkele handige koppelingen voor hulp, bijvoorbeeld een koppeling naar de PowerApps-community-site. Sluit u aan bij de community - zo kunt u uw vaardigheden veel sneller ontwikkelen dan in uw eentje.

[**Referentie formule** ](formula-reference.md) Een uitstekende manier om inspiratie op te doen door enkele standaardfuncties te bekijken.

[**PowerApps-community**](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1): voorbeelden bekijken, samenwerken met anderen, vragen stellen en de PowerApps-community verder laten groeien.
