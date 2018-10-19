---
title: Het kleurenschema wijzigen of een logo toevoegen met het merk van uw organisatie | MicrosoftDocs
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
author: Mattp123
ms.assetid: 21a166a0-d25e-4260-a1e4-2ddc528787c2
caps.latest.revision: 17
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-theme"></a>Een thema maken

U kunt een aangepast uiterlijk (een thema) voor uw app maken door wijzigingen aan te brengen in de standaardkleuren en visuele elementen van het niet-aangepaste systeem. U kunt bijvoorbeeld uw persoonlijke producthuisstijl maken door een bedrijfslogo toe te voegen en entiteitspecifieke kleuren te bieden. Een thema wordt gemaakt met de aanpassingshulpmiddelen in de gebruikersinterface, zonder dat een ontwikkelaar code hoeft te schrijven. U kunt thema's maken, wijzigen of verwijderen die in uw organisatie worden gebruikt. De thema-aanpassing wordt ondersteund in de webformulieren in Dynamics 365 for Outlook. U kunt meerdere thema's definiëren, maar er kan er slechts één zijn ingesteld en worden gepubliceerd als het standaardthema.  
  
<a name="UseThemes"></a>   
## <a name="use-themes-to-enhance-the-user-interface-and-create-your-product-branding"></a>Thema's gebruiken om de gebruikersinterface te verbeteren en uw eigen merkaanduidingen toe te voegen  
 Thema's worden gebruikt om de gebruikersinterface van de app te verbeteren, niet om deze ingrijpend te wijzigen. De themakleuren worden algemeen, door de hele toepassing heen, toegepast. Zo kunt u bijvoorbeeld de volgende visuele elementen in de UI verbeteren:  
  
-   Productlogo's en navigatiekleuren wijzigen om een eigen productidentiteit te creëren  
  
-   Accentkleuren aanpassen, zoals de kleur bij het aanwijzen of selecteren van items  
  
-   Entiteitsspecifieke kleuren bieden  
    
-   Logo  
  
-   Knopinfo voor logo  
  
-   Kleur van navigatiebalk  
  
-   Kleur van navigatiebalkplank

-   Hoofdopdrachtbalkkleur in de Unified Interface
  
-   Koptekstkleur  
  
-   Algemene koppelingskleur  
  
-   Effect bij geselecteerde koppeling  
  
-   Effect bij aanwijzen van koppeling  
  
-   Kleur van procesbesturingselementen  
  
-   Standaardkleur van entiteiten  
  
-   Standaardkleur van aangepaste entiteiten  
  
-   Schaduw van besturingselementen  
  
-   Rand van besturingselementen  
  
<a name="Solution"></a>   
## <a name="solution-awareness"></a>Oplossingsbewustzijn  
 Het thema is niet oplossingsbewust. De wijzigingen in het thema van een organisatie worden niet opgenomen in oplossingen die uit de organisatie worden geëxporteerd. De gegevens worden opgeslagen in de thema-entiteit die kan worden geëxporteerd en opnieuw geïmporteerd in een andere omgeving. Het geïmporteerde thema moet eerst worden gepubliceerd voordat het van kracht wordt.  
  
<a name="CloneAlter"></a>   
## <a name="copy-and-alter-the-existing-theme"></a>Het bestaande thema kopiëren en wijzigen  
 De gemakkelijkste en snelste manier om een nieuw thema te maken is een bestaand thema klonen en wijzigen, het vervolgens op te slaan, te bekijken en te publiceren. 
 
1.  Meld u aan bij [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

2.  Selecteer **Modelgestuurd** (onderste links). 

3.  Selecteer ![pictogram Instellingen](../model-driven-apps/media/powerapps-gear.png) (rechtsboven) > **Geavanceerde aanpassingen**. 

4. Selecteer onder **Thema's** de optie **Alle thema's**. 

5. Selecteer **CRM-standaardthema**. 

In de volgende schermafbeelding ziet u een gedeelte van de standaardthema-instelling.  

> [!div class="mx-imgBorder"] 
> ![Standaardthema](media/default-theme.png) 
  
 WIj hebben het standaardthema gekloond en de kleuren gewijzigd. De volgende screenshots tonen de nieuwe kleuren voor navigatie en markering. U kunt ook een nieuw logo voor uw product kiezen.  
  
 De volgende screenshot toont de nieuwe navigatiekleur.  
 
 > [!div class="mx-imgBorder"] 
 > ![Zachte groene themakleuren](media/theme-gentle-green.png "Zachte groene themakleuren")  
  
 De volgende screenshot toont het raster voor de entiteit account met de nieuwe markeringskleur.  
 
 > [!div class="mx-imgBorder"] 
 > ![Accountraster zacht groen thema](media/themes-gentle-green-account-grid.png "Accountraster zacht groen thema")  
  
<a name="Publish"></a>   
## <a name="preview-and-publish-a-theme"></a>Een voorbeeld van een thema bekijken en dit publiceren  
 Voer de volgende stappen uit om een voorbeeld van een thema te bekijken en dit te publiceren:  
  
-   Maak een geheel nieuw thema of kloon een bestaand thema.  
  
-   Bekijk het nieuwe thema door **Voorbeeld** te kiezen op de opdrachtbalk. U kunt de voorbeeldmodus verlaten door **Voorbeeld afsluiten** te kiezen op de opdrachtbalk, naast de knop **Voorbeeld**.  
  
-   Publiceer een thema. Kies **Thema publiceren** op de opdrachtbalk.  
  
 De volgende screenshot toont de knoppen op de opdrachtbalk voor voorbeeldweergave en publicatie.  
  
 ![Voorbeeldknoppen gebruiken om de voorbeeldmodus te openen/sluiten](media/themes-preview-buttons.PNG "Voorbeeldknoppen gebruiken om de voorbeeldmodus te openen/sluiten")  
  
<a name="BestPracticies"></a>   
## <a name="best-practices"></a>Aanbevolen procedures  
 Hieronder volgen de aanbevelingen voor het ontwerpen van themacontrasten en het kiezen van kleuren.  
  
### <a name="theme-contrast"></a>Themacontrast  
 Wij adviseren de volgende aanpak bij het gebruiken van contrastkleuren:  
  
-   Kies de contrasterende kleuren zorgvuldig. Het gebruiksklare standaardthema van Common Data Service voor Apps heeft de juiste contrastverhoudingen om een optimale bruikbaarheid te waarborgen. Gebruik vergelijkbare verhoudingen voor uw nieuwe thema's.  
  
-   Gebruik de standaard kleurinstellingen voor de modus met hoog contrast.  
  
### <a name="theme-colors"></a>Themakleuren  
 Wij adviseren u niet een groot aantal verschillende kleuren te gebruiken. Hoewel u een andere kleur kunt instellen voor elke entiteit, adviseren wij één van twee patronen:  
  
-   Geef alle entiteiten weer in neutrale kleuren en markeer de belangrijkste entiteiten.  
  
-   Gebruik dezelfde kleur voor vergelijkbare of gerelateerde entiteiten, zoals wachtrij en wachtrij-item, of entiteiten in de productcatalogus. Houd het totale aantal groepen laag.  
  
<a name="Considerations"></a>   
## <a name="custom-theme-considerations"></a>Overwegingen bij aangepaste thema's  
 U zou het volgende moeten overwegen bij het plannen van het gebruik van aangepaste thema's:  
  
-   De meeste bijgewerkte gebieden in de gebruikersinterface (UI) worden weergegeven in de aangepaste themakleuren.  
  
-   Hoewel de themakleuren globaal worden toegepast in de toepassing, behouden sommige oudere UI-gebieden, zoals kleurovergangknoppen, de standaardkleuren.  
  
-   Bepaalde gebieden moeten donkere of lichte kleuren gebruiken om te contrasteren met de standaard pictogramkleuren. De pictogramkleur is niet aanpasbaar.  
  
-   Een entiteit kan in verschillende kleuren worden weergegeven onder verschillende Sitemap-knooppunten.  
  
-   De kleuren van de Sitemap-knooppunten zijn niet aanpasbaar.  
  
## <a name="see-also"></a>Zie ook  
         
 [Video: Thema's in Dynamics 365 Customer Engagement](http://go.microsoft.com/fwlink/p/?LinkId=529568) [Query uitvoeren op het thema van een organisatie en dit bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/query-and-edit-an-organization-theme)

