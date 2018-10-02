---
title: Lokaliseerbare tekst vertalen voor modelgestuurde apps | MicrosoftDocs
description: Hier wordt beschreven hoe u lokaliseerbare tekst laat vertalen om meerdere talen te ondersteunen
ms.custom: ''
ms.date: 06/03/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="translate-localizable-text-for-model-driven-apps"></a>Lokaliseerbare tekst vertalen voor modelgestuurde apps

Als u aangepaste entiteit- of veldtekst hebt, zoals veldlabels of vervolgkeuzelijstwaarden, kunt u de gebruikers in uw omgeving die niet met de standaardtaalversie van uw omgeving werken, deze aangepaste tekst in hun voorkeurstaal bieden. 

Dit proces omvat de volgende stappen:
1. Andere talen voor uw omgeving inschakelen
2. De lokaliseerbare tekst exporteren
3. De lokaliseerbare tekst laten vertalen
4. De gelokaliseerde tekst importeren

## <a name="enable-other-languages-for-your-environment"></a>Andere talen voor uw omgeving inschakelen

Als u de talen voor uw omgeving nog niet hebt ingeschakeld, gebruikt u de stappen in [De taal inschakelen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) om deze in te schakelen.

> [!IMPORTANT]
> Het inschakelen van een taal kan enkele minuten duren. Tijdens dit proces kunnen andere gebruikers van de omgeving uw app mogelijk niet gebruiken. Schakel talen in op een tijdstip waarop gebruikers hier het minst last van hebben.

> [!TIP]
> Houd tijdens het inschakelen van de talen de LCID-waarden voor elke taal in de gaten. Deze waarde staat voor de taal in de geëxporteerde gegevens voor de lokaliseerbare tekst. Taalcodes bestaan uit vier- of vijfcijferige landinstellingen-id's. U vindt de geldige LCID-waarden in het [Diagram van landinstellingen-id's (LCID's)](http://go.microsoft.com/fwlink/?LinkId=122128).

## <a name="export-the-localizable-text"></a>De lokaliseerbare tekst exporteren

Het bereik van de lokaliseerbare tekst die wordt geëxporteerd, is de onbeheerde oplossing die de lokaliseerbare tekst bevat. Dit kan alleen worden gedaan met de oplossingenverkenner

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Open de onbeheerde oplossing met de lokaliseerbare tekst door op de menubalk **Vertalingen** > **Vertalingen exporteren** te selecteren. 

![Vertalingen exporteren](media/export-localizable-text.png)

De volgende waarschuwing wordt weergegeven:
> Het kan enkele minuten duren voordat aangepaste labels voor vertaling zijn geëxporteerd. Klik pas weer op de exportkoppeling nadat de eerste export is voltooid. Weet u zeker dat u nu de labels wilt exporteren? 

Klik op **OK** als u wilt doorgaan.

Als het exporteren is voltooid, kunt u zoeken naar een bestand met een naam als `CrmTranslations_{0}_{1}.zip` in uw map met downloads. Hierbij is `{0}` de unieke naam van de oplossing en `{1}` het versienummer van de oplossing.

## <a name="get-the-localizable-text-translated"></a>De lokaliseerbare tekst laten vertalen

U kunt dit bestand verzenden naar een taalkundig expert, vertaalbureau of lokalisatiebedrijf.

Als u over de nodige kennis beschikt om de tekst te vertalen, of als u alleen de indeling wilt bekijken, kunt u het geëxporteerde zipbestand uitpakken. Vervolgens ziet u dat het bestand twee XML-bestanden bevat. 
 - `[Content_Types].xml`
 - `CrmTranslations.xml`

U kunt het bestand CrmTranslations.xml openen in Microsoft Office Excel.

> [!TIP]
> Tenzij u vaker XML-bestanden opent met Excel, is het misschien gemakkelijker om Excel eerst te openen en vervolgens het bestand te openen door het pad naar het uitgepakte bestand CrmTranslations.xml-bestand te plakken.

> [!IMPORTANT]
> Zorg ervoor dat u niet de bestandsindeling wijzigt. Als u het bestand in een andere indeling opslaat, kunt u het vervolgens niet weer importeren.

Bekijk het tabblad **Gelokaliseerde labels** wanneer u de gegevens in Excel weergeeft.

![Geëxporteerde tekst voor lokalisatie](media/localized-labels-tab-exported-languages.png)

Aangepaste entiteiten of velden hebben lege cellen voor de lokaliseerbare tekst. Voeg de gelokaliseerde waarden voor deze items toe.

> [!NOTE]
> Als u de weergavenaam of beschrijving voor een standaardentiteit of entiteitsveld hebt gewijzigd, bevatten de gelokaliseerde tekenreeksen nog steeds de vertalingen voor de oorspronkelijke waarde. Deze moeten worden gelokaliseerd op basis van de nieuwe waarde.

Het tabblad **Weergavetekenreeksen** bevat tekst die voor andere elementen wordt weergegeven, zoals lintopdrachten, foutberichten en formulierlabels.

### <a name="updating-localizable-text-in-the-base-language"></a>Lokaliseerbare tekst in de standaardtaal bijwerken

Als u de weergavenaam voor een standaardentiteit of entiteitsveld in een speciaal bericht wijzigt, kunt u gegevens op het tabblad **Weergavetekenreeksen** bijwerken zodat de aangepaste naam wordt gebruikt.

> [!TIP]
> Hoewel de gebruikersinterface voor het bewerken van systeementiteitsberichten veel verwijzingen naar entiteitsnamen bevat, zijn niet alle entiteitsnamen hierin opgenomen. Met deze techniek vindt u er mogelijk meer. Meer informatie: [Systeementiteitberichten bewerken](../common-data-service/edit-system-entity-messages.md)

Als u de weergavenaam voor de entiteit Account in *Bedrijf* wijzigt, moet u bijvoorbeeld de standaardtaalkolom in **Weergavetekenreeksen** doorzoeken op `account`, `accounts`, `Account` en `Accounts`, en vervangen door `company`, `companies`, `Company` en `Companies`.

> [!IMPORTANT]
> Voer geen algemene zoek- en vervangbewerking in het bestand uit. U dient ervoor te zorgen dat de overeenkomende tekst daadwerkelijk verwijst naar de namen die u hebt gewijzigd.


## <a name="import-the-localized-text"></a>De gelokaliseerde tekst importeren
Als u de tekst wilt importeren, moet u de bestanden comprimeren en importeren in het systeem.

### <a name="compress-the-files"></a>De bestanden comprimeren

Als u wijzigingen hebt aangebracht in het bestand `CrmTranslations.xml`, moet u het bestand samen met het bestand `[Content_Types].xml` comprimeren in de zipindeling. Selecteer *beide bestanden* en klik met de rechtermuisknop om het contextmenu te openen. Kies in het contextmenu de optie **Verzenden naar** > **Gecomprimeerde (gezipte) map**.

### <a name="import-the-files"></a>De bestanden importeren

In dezelfde onbeheerde oplossing waaruit u de vertalingen hebt geëxporteerd, kiest u **Vertalingen** > **Vertalingen importeren** in het menu. 

![Vertalingen importeren](media/import-translations.png)

Selecteer het bestand met de gecomprimeerde vertaalde tekst en selecteer **Importeren**.

![Geselecteerd bestand importeren](media/import-translated-text-dialog.png)

Wanneer de vertaalde tekst is geïmporteerd, moet u alle aanpassingen publiceren om de wijzigingen in uw app(s) weer te geven.

## <a name="community-tools"></a>Community-hulpprogramma's

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) is een hulpprogramma dat de XrmToolBox-community heeft ontwikkeld. Gebruik Easy Translator om vertalingen met contextuele gegevens te exporteren en te importeren. 

> [!NOTE]
> De community-hulpprogramma's worden niet ondersteund door Microsoft.
> Als u vragen hebt over het hulpprogramma, raadpleegt u de uitgever hiervan. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).


## <a name="next-steps"></a>Volgende stappen
[Land- en taalinstellingen voor uw organisatie wijzigen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)<br />
[Systeementiteitsberichten bewerken](../common-data-service/edit-system-entity-messages.md)

