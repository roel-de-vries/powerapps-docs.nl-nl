---
title: Aanvullende besturingselementen voor Dynamics 365 voor telefoons en tablets | MicrosoftDocs
description: Een lijst met besturingselementen is beschikbaar voor gebruik met Dynamics 365 voor telefoons en tablets
ms.custom: ''
ms.date: 06/18/2018
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
ms.assetid: 7920ef78-2540-48ad-ba25-9ce9cb995ed1
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: d6293f1fc0913a7e2f66e3830702458e3249f0f0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674999"
---
# <a name="additional-controls-for-dynamics-365-for-phones-and-tablets"></a>Aanvullende besturingselementen voor Dynamics 365 voor telefoons en tablets 

 U kunt een uitgebreide set met aanvullende besturingselementen gebruiken om een meer op aanraakbewegingen gerichte ervaring op Dynamics 365 voor telefoons en tablets te maken. Denk aan schuifbalken, schakelaars, een multimediaspeler, invoermaskers, een kalender en andere besturingselementen.  

 
> [!NOTE]
>  U kunt deze aanvullende besturingselementen alleen met de mobiele apps gebruiken. Ze worden niet ondersteund in de web-app.  
  
 Ga als volgt te werk u deze besturingselementen in de formuliereditor wilt gebruiken:  
  
1.  Dubbelklik op het veld of de lijst waaraan u het besturingselement wilt toevoegen.  
  
2.  Klik op het tabblad **Besturingselementen**.  
  
3.  Klik op **Besturingselement toevoegen**.  
  
4.  Selecteer het gewenste besturingselement en klik op vervolgens **Toevoegen**.  
  
    > [!NOTE]
    >  Er zijn verschillende besturingselementen beschikbaar afhankelijk van het veld- of lijsttype. Besturingselementen op schuifbalken zijn bijvoorbeeld mogelijk alleen beschikbaar voor numerieke velden of geldvelden en het kalenderbesturingselement is alleen beschikbaar voor lijsten.  
  
5.  Selecteer de apparaten waarop u het besturingselement wilt laten weergegeven (telefoon, tablet of beide). Besturingselementen zijn niet beschikbaar voor telefoonheadervelden.  
  
6.  Configureer de waarden voor elke eigenschap.  
  
7.  Klik op **OK** wanneer u klaar bent met de configuratie van het besturingselement.  
  
 De volgende items zijn beschrijvingen voor elk besturingselement dat u kunt gebruiken op formulieren voor Dynamics 365 voor telefoons en tablets.  
  
## <a name="calendar-control"></a>Kalenderbesturingselement  
 Gebruik dit besturingselement voor het configureren van formulieren zodat ze als kalenderweergave in Dynamics 365 voor telefoons en tablets worden weergegeven. U kunt dit besturingselement ook gebruiken om dashboards, lijsten of entiteitsrasters voor telefoons en tablets te vervangen.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Begindatum|Definieer de begindatum en -tijd van het item dat u wilt visualiseren in de kalenderweergave. De beschikbare waarden zijn alle kolommen in deze weergave van het type datum.|  
|Einddatum|Definieer de einddatum en -tijd van het item dat u wilt visualiseren in de kalenderweergave. De beschikbare waarden zijn alle kolommen in deze weergave van het type datum.|  
|Duur|De duur in minuten. Als u een waarde opgeeft voor Einddatum wordt Duur genegeerd.|  
|Beschrijving|Dit is het bijschrift dat u wilt zien voor kalenderitems.|  
  
 De minimumduur die in de kalender wordt weergegeven, is 30 minuten. Items met een duur van minder dan 30 minuten worden nog steeds als items van 30 minuten lang weergegeven.  
  
 Het kalenderbesturingselement ondersteunt al het datumgedrag (Lokale gebruiker, Alleen datum en Onafhankelijk van tijdzone).  
  
## <a name="timeline-control"></a>Tijdlijnbesturingselement  
 Geef een tijdlijn op met recente, relevante nieuwsartikelen en Twitter-tweets voor een account.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|CC_Timeline_Title|Eigenschap die moet worden toegewezen voor de titel van elk item op de tijdlijn.|  
|CC_Timeline_Title_Desc|Omschrijving voor Titel.|  
|CC_Timeline_Label1|Veld dat moet worden weergegeven onder de titel van het item op de tijdlijn.|  
|CC_Timeline_Label1_Desc|Omschrijving voor Label 1.|  
|CC_Timeline_Label2|Veld dat moet worden weergegeven na Label 1.|  
|CC_Timeline_Label2_Desc|Omschrijving voor Label 2.|  
|CC_Timeline_Label3|Veld dat moet worden weergegeven na Label 2.|  
|CC_Timeline_Label3_Desc|Omschrijving voor Label 3.|  
|CC_Timeline_Label4|Veld dat moet worden weergegeven na Label 3.|  
|CC_Timeline_Label4_Desc|Omschrijving voor Label 4.|  
|CC_Timeline_Label5|Veld dat moet worden weergegeven na Label 4.|  
|CC_Timeline_Label5_Desc|Omschrijving voor Label 5.|  
|CC_Timeline_Timestamp|Veld dat moet worden gebruikt voor het sorteren van de tijdlijn in omgekeerde chronologische volgorde.|  
|CC_Timeline_Timestamp_Desc|Beschrijving voor Timestamp.|  
|CC_Timeline_Group|Toe te wijzen veld voor het groeperen van de tijdlijn.|  
|CC_Timeline_Group_Desc|Beschrijving voor het veld Groep.|  
|CC_Timeline_GroupOrder|Volgorde van de groep waarvan het item deel uitmaakt ten opzichte van andere groepen (wijs waarden 1, 2, 3, etc. toe voor groepen die moeten worden weergegeven). De groep wordt weergegeven in oplopende waarde van toegewezen groepswaarden.|  
|CC_Timeline_GroupOrder_Desc|Beschrijving voor het veld Groepsvolgorde.|  
|CC_Timeline_URL|Toe te wijzen URL-veld voor weergave van de URL van elk item op de tijdlijn.|  
|CC_Timeline_URL_Desc|Beschrijving voor URL-veld.|  
|CC_Timeline_ThumbnailURL|Toe te wijzen veld voor miniatuur van afbeelding/pictogram dat voor elk item moet worden weergegeven.|  
|CC_Timeline_ThumnailURL_Desc|Beschrijving voor het `ThumbnailURL`-veld.|  
|CC_Timeline_Filter|Toe te wijzen veld voor tijdlijnfilter.|  
|CC_Timeline_Filter_Desc|Beschrijving voor Filter.|  
|CC_Timeline_Footer|Webresource die moet worden weergegeven als de voettekst van de tijdlijn.|  
|CC_Timeline_Footer_Desc|Beschrijving voor het veld Voettekst.|  
  
## <a name="linear-slider"></a>Lineaire schuifbalk  
 Met het besturingselement lineaire schuifbalk kunnen uw gebruikers numerieke waarden invoeren door een schuifbalk te verslepen. Dit element biedt ook een optie voor het typen van de hoeveelheid. Met de schuifregelaar kunt u alleen gehele getallen invoeren en weergeven. Gebruik dit besturingselement voor alle numerieke velden of het geldveld.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max.|Stel de maximumwaarde in die op de schuifbalk moet worden weergegeven.|  
|Min|Stel de minimumwaarde in die op de schuifbalk moet worden weergegeven.|  
|Waarde|De waarde die op de schuifbalk moet worden weergegeven.|  
|Stap|Stel de hoeveelheid in die bij de huidige waarde moet worden opgeteld of die van de huidige waarde moet worden afgetrokken wanneer u gegevens invoert met behulp van dit besturingselement.|  
  
## <a name="option-sets"></a>Optiesets  
 Het besturingselement Optieset biedt uw gebruikers een aantal keuzen wanneer ze gegevens invoeren. Gebruik dit besturingselement voor optiesets met niet meer dan twee of drie keuzen.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Hiermee wordt het veld weergegeven waaraan het besturingselement is toegewezen.|  
  
## <a name="flip-switch"></a>Wisselschakelaar  
 De wisselschakelaar is vergelijkbaar met een aan-uitschakelaar en biedt twee mogelijke waarden.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Hiermee wordt het veld weergegeven waaraan het besturingselement is toegewezen.|  
  
## <a name="star-rating"></a>Sterwaardering  
 Gebruik de sterwaardering om een waardering visueel weer te geven. U kunt maximaal vijf sterren instellen. U kunt dit besturingselement alleen gebruiken voor gehele getallen; decimale waarden kunnen niet worden geaccepteerd.  
  
> [!NOTE]
>  Zorg ervoor dat u de optie **Verbergen op web** selecteert voor dit besturingselement.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max.|Selecteer het maximale aantal sterren voor het besturingselement vanuit de vervolgkeuzelijst.|  
  
## <a name="radial-knob"></a>Draaiknop  
 De draaiknop biedt gebruikers een manier om gegevens in te voeren door aan de knop te draaien. Dit wordt als cirkel op het scherm weergegeven. Met het besturingselement Draaiknop kunnen alleen gehele getallen worden ingevoerd en weergegeven. Gebruik dit besturingselement voor numerieke velden of geldvelden. U kunt aanraakfuncties gebruiken om de waarde te wijzigen of u kunt het toetsenblok gebruiken om het getal in te voeren en te bewerken.  
  
> [!NOTE]
>  Dit besturingselement wordt niet ondersteund op Android 4.2- en 4.3-apparaten. Dit heeft invloed op de bladerervaring op deze versies.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max.|Stel de maximale waarde in die op de meter moet worden weergegeven.|  
|Min|Stel de minimale waarde in die op de meter moet worden weergegeven.|  
|Waarde|Stel de waarde in of haal de waarde op die op de meter moet worden weergegeven.|  
|Stap|Stel de hoeveelheid in die bij de huidige waarde moet worden opgeteld of die van de huidige waarde moet worden afgetrokken wanneer u gegevens invoert met behulp van dit besturingselement.|  
  
## <a name="website-preview"></a>Websitepreview  
 Gebruik het besturingselement Websitepreview om een URL-veld toe te wijzen en een preview van de website weer te geven.  
  
> [!IMPORTANT]
>  Als u dit besturingselement inschakelt, geeft u uw gebruikers toestemming om bepaalde identificeerbare apparaatgegevens met een extern systeem te delen. Gegevens die vanuit externe systemen in een PowerApps-app of Dynamics 365 Customer Engagement worden geïmporteerd, zijn onderworpen aan onze privacyverklaring bij [Privacy en cookies bij Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=521839).  
>   
>  [Privacyverklaringen](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Hiermee wordt het veld weergegeven waaraan het besturingselement is toegewezen.|  
  
## <a name="bullet-graph"></a>Uitgebreide staafgrafiek  
 Het besturingselement Uitgebreide staafgrafiek toont één hoofdmeting met een vergelijkende meting en kwalitatieve bereiken om direct te signaleren of de meting goed of fout is of een andere status heeft. Gebruik dit besturingselement in dashboards voor numerieke velden of geldvelden. U kunt bijvoorbeeld de waarde toewijzen aan daadwerkelijke omzet en het doel aan de geschatte omzet om het verschil tussen daadwerkelijke en geschatte omzet te visualiseren.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max.|Stel de maximale waarde in die op de grafiek moet worden weergegeven.|  
|Min|Stel de minimale waarde in die op de grafiek moet worden weergegeven.|  
|Goed|Stel een waarde in die als goed voor de meting wordt beschouwd (optioneel).|  
|Slecht|Stel een waarde in die als fout voor de meting wordt beschouwd (optioneel).|  
|Waarde|Hiermee wordt het veld weergegeven waaraan het besturingselement is toegewezen.|  
|Doel|Wijs dit toe aan het veld waarmee u de waarde wilt vergelijken. Als **Waarde** bijvoorbeeld is toegewezen aan **Daadwerkelijke omzet**, kunt u **Doel** toewijzen aan **Geschatte omzet** of een statische waarde opgeven.|  
  
## <a name="pen-control"></a>Penbesturingselement  
 Gebruik het penbesturingselement om geschreven invoer zoals handtekeningen vast te leggen.  
  
> [!NOTE]
>  De minimaal aanbevolen **Maximumlengte** die is opgegeven voor het veld waaraan dit besturingselement is toegewezen, is 15000.  
>   
>  Zorg ervoor dat u de optie **Verbergen op web** selecteert voor dit besturingselement.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|PenMode|Geef **PenMode!Draw**, **PenMode!Erase** of **PenMode!Select** op om te bepalen wat er gebeurt wanneer een gebruiker een aanwijsapparaat in een penbesturingselement versleept.|  
  
## <a name="auto-complete"></a>Automatisch aanvullen  
 Met het besturingselement Automatisch aanvullen filtert u een itemlijst terwijl u typt en laat u een waarde uit de vervolgkeuzelijst selecteren. U kunt dit besturingselement bijvoorbeeld gebruiken om gebruikers uit een vervolgkeuzelijst met statussen of landen/regio’s te laten kiezen. Dit besturingselement wordt toegewezen aan een veld van het type **Eén tekstregel**.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Hiermee wordt het veld weergegeven waaraan het besturingselement is toegewezen.|  
|Bron|Stel de bron voor de gegevens in (gegroepeerde opties, Optieset of Weergave).|  
|Optieset|Selecteer de optieset voor dit veld.|  
|Weergeven|Selecteer de entiteit en weergave voor dit veld.|  
|Veld|Selecteer het veld van de primaire entiteit van de weergave om de gegevensbron te gebruiken.|  
  
## <a name="multimedia"></a>Multimedia  
 U kunt video's insluiten voor een rijkere klantervaring voor verkoop- en veldmedewerkers die onderweg zijn. Gebruik dit besturingselement voor toewijzing aan een URL-veld dat de audio- of videolink bevat die in het besturingselement moet worden afgespeeld.  
  
> [!NOTE]
>  Dit besturingselement wordt ondersteund op Android-versies 4.4 en hoger.  
>   
>  YouTube-video's worden momenteel niet ondersteund op Windows 8- en Windows 8.1-tablets en -telefoons. Op Windows 10 worden alleen HTTPS-video's (inclusief YouTube) ondersteund.  
  
 Ondersteunde mediatypen:  
  
-   Gestreamde MP4-bestanden  
  
-   YouTube-video's  
  
-   Azure-media  
  
-   Audiostreams  
  
 [Privacyverklaring](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Media|Voer de URL in van de media die in dit besturingselement moet worden afgespeeld.|  
  
## <a name="number-input"></a>Nummerinvoer  
 Gebruik het besturingselement Nummerinvoer om gebruikers te helpen snel gegevens in te voeren. Gebruikers hoeven alleen maar op de plus- en min-knop te tikken om een numerieke waarde te wijzigen in door u ingestelde stappen. Gebruik dit besturingselement voor alle numerieke velden of het geldveld. Gebruikers kunnen ook een nummer rechtstreeks in het veld typen. Dit veld wordt alleen ondersteund in de bewerkmodus.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Stap|Stel de hoeveelheid in die bij de huidige waarde moet worden opgeteld of die van de huidige waarde moet worden afgetrokken wanneer u gegevens invoert met behulp van dit besturingselement.|  
|Veld|Hiermee wordt het veld weergegeven waaraan het besturingselement is toegewezen.|  
  
## <a name="input-mask"></a>Invoermasker  
 Met het besturingselement Invoermasker stelt u de opmaak in voor een veld zoals een telefoonnummer of creditcard om te voorkomen dat ongeldige gegevens worden ingevoerd. Als u bijvoorbeeld wilt dat gebruikers een telefoonnummer in de Verenigde Staten invoeren in de indeling +1-222-555-1011, gebruikt u het invoermasker +1-000-000-0000.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Masker|Voer het masker in om te gebruiken voor het valideren van gegevens terwijl deze door gebruikers worden ingevoerd. Voor het masker kunt u een combinatie van de volgende tekens gebruiken:<br /><br /> 0: Cijfer<br /><br /> 9:- Cijfer of spatie<br /><br /> #: cijfer, teken of spatie<br /><br /> L: Letter<br /><br /> I: letter of spatie<br /><br /> A: Alfanumeriek<br /><br /> A: alfanumeriek of spatie<br /><br /> <: hiermee worden tekens geconverteerd die op een kleine letter volgen<br /><br /> >: hiermee worden tekens geconverteerd die op een hoofdletter volgen<br /><br /> &#124;: hiermee wordt de conversie van hoofdletters en kleine letters uitgeschakeld<br /><br /> \: hiermee wordt elk willekeurig teken gemaskeerd, waardoor dit een letterlijke waarde wordt<br /><br /> Alle andere: letterlijke waarde|  
|Veld|Hiermee wordt het veld weergegeven waaraan het besturingselement is toegewezen.|  
  
## <a name="linear-gauge"></a>Lineaire meter  
 Met de lineaire meter kunnen uw gebruikers numerieke waarden invoeren door een schuifregelaar te verslepen in plaats van de exacte hoeveelheid te typen. Met de schuifregelaar kunt u alleen gehele getallen invoeren en weergeven. Gebruik dit besturingselement voor alle numerieke velden en geldvelden.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max.|Stel de maximale waarde in die op de meter moet worden weergegeven.|  
|Min|Stel de minimale waarde in die op de meter moet worden weergegeven.|  
|Waarde|Stel de waarde in of haal de waarde op die op de meter moet worden weergegeven.|  
|Stap|Stel de hoeveelheid in die bij de huidige waarde moet worden opgeteld of die van de huidige waarde moet worden afgetrokken wanneer u gegevens invoert met behulp van dit besturingselement.|  
  
## <a name="arc-knob"></a>Boogknop  
 De boogknop biedt gebruikers een manier om gegevens in te voeren door aan de knop te draaien. Dit wordt als een boog op het scherm weergegeven. Met het besturingselement Boogknop kunnen alleen gehele getallen worden ingevoerd en weergegeven. Gebruik dit besturingselement voor alle numerieke velden en geldvelden. U kunt aanraakfuncties gebruiken om de waarde te wijzigen of u kunt het toetsenblok gebruiken om het getal in te voeren en te bewerken.  
  
> [!NOTE]
> Dit besturingselement wordt niet ondersteund op Android 4.2- en 4.3-apparaten. Dit heeft invloed op de bladerervaring op deze versies.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max.|Stel de maximale waarde in die op de meter moet worden weergegeven.|  
|Min|Stel de minimale waarde in die op de meter moet worden weergegeven.|  
|Waarde|Stel de waarde in of haal de waarde op die op de meter moet worden weergegeven.|  
|Stap|Stel de hoeveelheid in die bij de huidige waarde moet worden opgeteld of die van de huidige waarde moet worden afgetrokken wanneer u gegevens invoert met behulp van dit besturingselement.|  
  
## <a name="next-steps"></a>Volgende stappen
[Zelfstudie: aangepaste besturingselementen voor gegevensvisualisaties gebruiken](use-custom-controls-data-visualizations.md)