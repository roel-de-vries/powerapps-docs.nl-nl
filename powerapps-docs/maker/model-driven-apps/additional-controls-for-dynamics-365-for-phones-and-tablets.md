---
title: Extra besturingselementen voor Dynamics 365 voor telefoons en tablets | MicrosoftDocs
description: Een lijst met besturingselementen die beschikbaar zijn voor gebruik met Dynamics 365 voor telefoons en tablets
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="additional-controls-for-dynamics-365-for-phones-and-tablets"></a>Extra entiteiten die zijn ingeschakeld voor Dynamics 365 voor telefoons en tablets 

 U kunt een uitgebreide reeks extra besturingselementen gebruiken om een meer touch-vriendelijke ervaring voor Dynamics 365 voor telefoons en tablets te maken. Deze omvatten schuifregelaars, schakelopties, multimediaspelers, invoermaskers, agenda´s en andere besturingselementen.  

 
> [!NOTE]
>  U kunt deze extra besturingselementen uitsluitend met de mobiele toepassingen gebruiken. Deze worden niet ondersteund in de web-app.  
  
 Als u deze besturingselementen in de formuliereneditor wilt gebruiken:  
  
1.  Dubbelklik op het veld of de lijst waaraan u het besturingselement wilt toevoegen.  
  
2.  Klik op het tabblad **Besturingselementen**.  
  
3.  Klik op **Besturingselement toevoegen**.  
  
4.  Selecteer het besturingselement dat u wenst en klik vervolgens op **Toevoegen**.  
  
    > [!NOTE]
    >  Afhankelijk van het veld- of lijsttype dat u selecteert, zijn er verschillende besturingselementen beschikbaar: Zo zijn schuifregelaars bijvoorbeeld waarschijnlijk alleen beschikbaar voor numerieke of valutavelden, en het besturingselement agenda is alleen beschikbaar voor lijsten.  
  
5.  Selecteer de apparaten waarop het besturingselement moet worden weergegeven (telefoon, tablet of beide). Besturingselementen zijn niet beschikbaar voor velden met telefoonkoptekst.  
  
6.  Configureer de waarden voor elke eigenschap.  
  
7.  Klik op **OK** wanneer u klaar bent met het configureren van het besturingselement.  
  
 Hieronder vindt u beschrijvingen van elk besturingselement dat u kunt gebruiken op formulieren voor Dynamics 365 voor telefoons en tablets.  
  
## <a name="calendar-control"></a>Besturingselement agenda  
 Gebruik dit besturingselement om formulieren zo te configureren dat deze worden weergegeven als een agendaweergave in Dynamics 365 voor telefoons en tablets. U kunt dit besturingselement ook gebruiken ter vervanging van dashboards, lijsten of entiteitrasters voor telefoons en tablets.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Begindatum|Bepaal de begindatum en de -tijd waarop het item in de agendaweergave zichtbaar moet zijn. De beschikbare waarden zijn in de kolommen in deze weergave van het type datum.|  
|Einddatum|Bepaal de einddatum en -tijd waarop het item in de agendaweergave zichtbaar moet zijn. De beschikbare waarden zijn in de kolommen in deze weergave van het type datum.|  
|Duur|De duur in minuten. Als u een waarde voor de einddatum opgeeft, wordt de duur genegeerd.|  
|Beschrijving|Dit is het bijschrift dat u voor agenda-items wilt zien.|  
  
 De minimumduur die in de agenda wordt weergegeven is 30 minuten. Items korter dan 30 minuten worden toch als 30 minuten weergegeven.  
  
 Het besturingselement agenda ondersteunt elk lokaal datumgedrag (Gebruikersinstelling, Alleen datum en Tijdzone-onafhankelijk).  
  
## <a name="timeline-control"></a>Tijdlijnbesturingselement  
 Geef een tijdlijn van recente, belangrijke nieuwsartikelen en tweets weer voor een account.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|CC_Timeline_Title|Eigenschap die u moet toewijzen voor de titel van elk tijdlijnitem.|  
|CC_Timeline_Title_Desc|Beschrijving van Titel.|  
|CC_Timeline_Label1|Veld dat onder de titel van het tijdlijnitem wordt weergegeven.|  
|CC_Timeline_Label1_Desc|Beschrijving voor label 1.|  
|CC_Timeline_Label2|Veld dat na Label 1 moet worden weergegeven.|  
|CC_Timeline_Label2_Desc|Beschrijving voor label 2.|  
|CC_Timeline_Label3|Veld dat na Label 2 moet worden weergegeven.|  
|CC_Timeline_Label3_Desc|Beschrijving voor label 3.|  
|CC_Timeline_Label4|Veld dat na Label 3 moet worden weergegeven.|  
|CC_Timeline_Label4_Desc|Beschrijving voor label 4.|  
|CC_Timeline_Label5|Veld dat na Label 4 moet worden weergegeven.|  
|CC_Timeline_Label5_Desc|Beschrijving voor label 5.|  
|CC_Timeline_Timestamp|Veld voor het sorteren van de tijdlijn in omgekeerde chronologische volgorde.|  
|CC_Timeline_Timestamp_Desc|Beschrijving voor Tijdstempel.|  
|CC_Timeline_Group|Veld voor toewijzing ten behoeve van het groeperen van de tijdlijn.|  
|CC_Timeline_Group_Desc|Beschrijving voor het veld Groep.|  
|CC_Timeline_GroupOrder|De volgorde van de groep waarvan het item deel uitmaakt, ten opzichte van andere groepen (wijs de waarden 1, 2, 3 enzovoort toe voor groepen die u wilt laten weergeven). De groepen worden weergegeven in oplopende volgorde op basis van de toegewezen groepswaarden.|  
|CC_Timeline_GroupOrder_Desc|Beschrijving voor het veld Groepsvolgorde.|  
|CC_Timeline_URL|URL-veld dat u moet toewijzen voor weergave van de URL van elk tijdlijnitem.|  
|CC_Timeline_URL_Desc|Beschrijving voor het veld URL.|  
|CC_Timeline_ThumbnailURL|Veld dat moet worden toegewezen voor de miniatuur van afbeelding/pictogram die voor de items worden getoond.|  
|CC_Timeline_ThumnailURL_Desc|Beschrijving voor het veld `ThumbnailURL`.|  
|CC_Timeline_Filter|Veld voor toewijzing voor het tijdlijnfilter.|  
|CC_Timeline_Filter_Desc|Beschrijving voor het veld Filter.|  
|CC_Timeline_Footer|Webresource die moet worden weergegeven als de voettekst van de tijdlijn.|  
|CC_Timeline_Footer_Desc|Beschrijving voor het veld Voettekst.|  
  
## <a name="linear-slider"></a>Lineaire schuifregelaar  
 Op het besturingselement lineaire schuifregelaar kunnen uw gebruikers numerieke waarden opgeven door een schuifregelaar te verslepen, en beschikt u ook over een optie om de hoeveelheid te typen. De schuifregelaar kan alleen voor de invoer van hele getallen worden gebruikt en is alleen-weergeven. Gebruik dit besturingselement voor numerieke velden of valutavelden.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max|Stelt de maximumwaarde voor weergave op de schuifregelaar in.|  
|Min|Stel de minimumwaarde voor weergave op de schuifregelaar in.|  
|waarde|De waarde voor weergave op de schuifregelaar.|  
|Stap|Stel het bedrag in waarmee de huidige waarde moet worden vermeerderd of verminderd als gegevens worden ingevoerd met dit besturingselement.|  
  
## <a name="option-sets"></a>Optiesets  
 Het besturingselement optieset presenteert een verzameling opties voor uw gebruikers waar ze uit kunnen kiezen bij het invoeren van gegevens. Gebruik dit besturingselement uitsluitend voor een optieset met twee of drie opties.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Geeft het veld weer waaraan het besturingselement is toegewezen.|  
  
## <a name="flip-switch"></a>Aan/uit-schakelaar  
 De tikschakelaar is als een aan-/uitschakelaar die een keuze uit twee waarden biedt.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Geeft het veld weer waaraan het besturingselement is toegewezen.|  
  
## <a name="star-rating"></a>Sterrenwaardering  
 Gebruik de sterwaardering om een visuele weergave van een beoordeling te geven. Het maximale aantal sterren dat u kunt instellen is vijf. U kunt dit besturingselement slechts voor hele getallen gebruiken; decimale waarden worden niet geaccepteerd.  
  
> [!NOTE]
>  Zie erop toe dat u de optie **Verbergen op web** voor dit besturingselement selecteert.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max|Selecteer het maximale aantal sterren in de vervolgkeuzelijst dat moet worden gebruikt voor het besturingselement.|  
  
## <a name="radial-knob"></a>Radiale knop  
 De radiale knop biedt een manier voor gebruikers om gegevens in te voeren door de knop te verschuiven, en wordt als cirkel weergegeven op het scherm. Het besturingselement radiale knop kan alleen voor de invoer van hele getallen worden gebruikt en is alleen-weergeven. Gebruik dit besturingselement voor numerieke velden of valutavelden. U kunt met een aanraking de waarde wijzigen, of u kunt het toetsenblok gebruiken om u op het cijfer te concentreren en het te bewerken.  
  
> [!NOTE]
>  Dit besturingselement wordt niet ondersteund op Android 4.2- en 4.3-apparaten. Het is van invloed op de schuifervaring in deze versies.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max|Stel de maximumwaarde voor weergave op de meter in.|  
|Min|Stel de minimumwaarde voor weergave op de meter in.|  
|waarde|Stel de waarde in die moet worden weergegeven op de meter, op haal deze waarde op.|  
|Stap|Stel het bedrag in waarmee de huidige waarde moet worden vermeerderd of verminderd als gegevens worden ingevoerd met dit besturingselement.|  
  
## <a name="website-preview"></a>Voorbeeld van website  
 Gebruik het besturingselement Voorbeeld van website om een veld met een URL te koppelen en om een voorbeeld van een website te zien.  
  
> [!IMPORTANT]
>  Door het besturingselement in te schakelen, gaat u ermee akkoord dat uw gebruikers wordt toegestaan om bepaalde identificeerbare apparaatinformatie met een extern systeem te delen. Op gegevens die uit externe systemen in een PowerApps-app of Dynamics 365 Customer Engagement worden geïmporteerd, is onze privacyverklaring van toepassing die u op de pagina [Microsoft-privacyverklaring](http://go.microsoft.com/fwlink/p/?LinkId=521839) vindt.  
>   
>  [Privacyverklaringen](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Geeft het veld weer waaraan het besturingselement is toegewezen.|  
  
## <a name="bullet-graph"></a>Puntengrafiek  
 Het besturingselement puntengrafiek toont één enkele belangrijke maateenheid die wordt vergeleken met een soortgelijke maateenheid en kwalitatieve bereiken om direct aan te geven of de maateenheid goed, slecht of in een andere status is. Gebruik dit besturingselement in dashboards voor numerieke velden of valutavelden. Zo kunt u bijvoorbeeld de waarde toewijzen aan werkelijke omzet en het doel aan geschatte omzet om de werkelijke omzet vergeleken met de geschatte omzet te visualiseren.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max|Stel de maximumwaarde voor weergave op het diagram in.|  
|Min|Stel de minimumwaarde voor weergave op het diagram in.|  
|Good|Stel een waarde in die wordt beschouwd als goed (optioneel).|  
|Slecht|Stel een waarde in die wordt beschouwd als slecht (optioneel).|  
|waarde|Geeft het veld weer waaraan het besturingselement is toegewezen.|  
|Doel|Wijs dit toe aan het veld dat waarmee u de waarde wilt vergelijken. Als bijvoorbeeld **Waarde** is toegewezen aan **Werkelijke omzet** kunt u **Doel** toewijzen aan **Geschatte omzet** of u kunt een statische waarde verstrekken.|  
  
## <a name="pen-control"></a>Penbesturingselement  
 Gebruik het besturingselement pen om geschreven invoer zoals handtekeningen vast te leggen.  
  
> [!NOTE]
>  De minimum aanbevolen **Maximale lengte** die is opgegeven voor het veld waar dit besturingselement aan is toegewezen is 15000 is.  
>   
>  Zie erop toe dat u de optie **Verbergen op web** voor dit besturingselement selecteert.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|PenMode|Specificeer **PenMode!Draw**, **PenMode!Erase** of **PenMode!Select** om te bepalen wat er gebeurt als een gebruiker een aanwijsapparaat in een penbesturingselement versleept.|  
  
## <a name="auto-complete"></a>Automatisch aanvullen  
 Het besturingselement automatisch aanvullen filtert een itemlijst tijdens het typen en laat u een waarde in de vervolgkeuzelijst selecteren. U kunt bijvoorbeeld dit besturingselement gebruiken om gebruikers de mogelijkheid te bieden om in een vervolgkeuzelijst een land/regio kiezen. Dit besturingselement is toegewezen aan een veldtype **Eén tekstregel**.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Veld|Geeft het veld weer waaraan het besturingselement is toegewezen.|  
|Bron|Stel de bron van de gegevens in (Gegroepeerde opties, Optieset of Weergeven).|  
|Optieset|Selecteer de optieset voor dit veld.|  
|Weergeven|Selecteer de entiteit en weergave voor dit veld.|  
|Veld|Selecteer het veld van de primaire entiteit van de weergave die moet worden gebruikt als gegevensbron.|  
  
## <a name="multimedia"></a>Multimedia  
 U kunt video's insluiten om een betere klantervaring te bieden voor verkoopmedewerkers en vertegenwoordigers onderweg. Gebruik dit besturingselement om iets aan een URL-veld toe te wijzen dat over een koppeling naar audio- of videomateriaal bevat die in het besturingselement moet worden afgespeeld.  
  
> [!NOTE]
>  Dit besturingselement wordt alleen ondersteund op Android 4.4 en hogere versies.  
>   
>  YouTube-video's worden momenteel niet ondersteund op Windows 8- en Windows 8.1-tablets en -telefoons. Op Windows 10 worden momenteel alleen HTTPS-video's ondersteund (met inbegrip van YouTube).  
  
 Ondersteunde mediatypen zijn onder andere:  
  
-   Streaming MP4-bestanden  
  
-   Youtube-video's  
  
-   Azure-media  
  
-   Audiostreams  
  
 [Privacyverklaring](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Media|Typ de URL van het medium dat in dit besturingselement moet worden afgespeeld.|  
  
## <a name="number-input"></a>Getalinvoer  
 Gebruik het besturingselement numerieke invoer om gebruikers te helpen om snel gegevens in te voeren. Gebruikers hoeven alleen maar op de knoppen met het plus- en minteken te tikken om een numerieke waarde te wijzigen in vooraf ingesteld stappen. Gebruik dit besturingselement voor numerieke velden of valutavelden. Gebruikers kunnen ook rechtstreeks een waarde in het veld typen. Dit veld wordt alleen ondersteund in de bewerkingsmodus.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Stap|Stel het bedrag in waarmee de huidige waarde moet worden vermeerderd of verminderd als gegevens worden ingevoerd met dit besturingselement.|  
|Veld|Geeft het veld weer waaraan het besturingselement is toegewezen.|  
  
## <a name="input-mask"></a>Invoermasker  
 Met het besturingselement invoermasker, stelt u de indeling voor een veld in, zoals voor een of telefoonnummer of creditcard, om invoeren van ongeldige gegevens te verhinderen. Bijvoorbeeld, als u gebruikers een telefoonnummer in de Verenigde Staten in de indeling +1-222-555-1011 wilt laten kunnen invoeren, gebruikt u het invoermasker +1-000-000-0000.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Masker|Geef het masker op dat wordt gebruikt voor validatie van data als gebruikers deze typen. U kunt een combinatie van de volgende tekens als masker gebruiken:<br /><br /> 0 – cijfer<br /><br /> 9 – cijfer of spatie<br /><br /> # – cijfer, teken of spatie<br /><br /> L – letter<br /><br /> I - letter of spatie<br /><br /> A – alfanumeriek teken<br /><br /> A – alfanumeriek teken of spatie<br /><br /> < – zet tekens die volgen om in kleine letters<br /><br /> < – zet tekens die volgen om in hoofdletters<br /><br /> &#124;| – omzetten hoofdletters kleine letters uitschakelen<br /><br /> \ – teken wordt verlaten, wordt omgezet in letterlijke waarde<br /><br /> Alle andere - letterlijke waarden|  
|Veld|Geeft het veld weer waaraan het besturingselement is toegewezen.|  
  
## <a name="linear-gauge"></a>Lineaire meter  
 Met de lineaire meter stelt u uw gebruikers in staat numerieke waarden in te voeren door een schuifregelaar te verslepen in plaats van dat ze de exacte hoeveelheid moeten typen. De schuifregelaar kan alleen voor de invoer van hele getallen worden gebruikt en is alleen-weergeven. Gebruik dit besturingselement voor numerieke velden en valutavelden.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max|Stel de maximumwaarde voor weergave op de meter in.|  
|Min|Stel de minimumwaarde voor weergave op de meter in.|  
|waarde|Stel de waarde in die moet worden weergegeven op de meter, op haal deze waarde op.|  
|Stap|Stel het bedrag in waarmee de huidige waarde moet worden vermeerderd of verminderd als gegevens worden ingevoerd met dit besturingselement.|  
  
## <a name="arc-knob"></a>Boogknop  
 De boogknop biedt een manier voor gebruikers om gegevens in te voeren door de knop te verschuiven, en wordt als een boog weergegeven op het scherm. Het besturingselement boog kan alleen voor de invoer van hele getallen worden gebruikt en is alleen-weergeven. Gebruik dit besturingselement voor numerieke velden en valutavelden. U kunt met een aanraking de waarde wijzigen, maar u kunt u ook op het cijfer richten en het bewerken via het toetsenblok.  
  
> [!NOTE]
> Dit besturingselement wordt niet ondersteund op Android 4.2- en 4.3-apparaten. Het is van invloed op de schuifervaring in deze versies.  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Max|Stel de maximumwaarde voor weergave op de meter in.|  
|Min|Stel de minimumwaarde voor weergave op de meter in.|  
|waarde|Stel de waarde in die moet worden weergegeven op de meter, op haal deze waarde op.|  
|Stap|Stel het bedrag in waarmee de huidige waarde moet worden vermeerderd of verminderd als gegevens worden ingevoerd met dit besturingselement.|  
  
## <a name="next-steps"></a>Volgende stappen
[Zelfstudie: Aangepaste besturingselementen gebruiken voor gegevensvisualisaties](use-custom-controls-data-visualizations.md)
