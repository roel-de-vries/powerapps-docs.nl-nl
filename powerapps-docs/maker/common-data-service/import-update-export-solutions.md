---
title: 'Oplossingen importeren, bijwerken en exporteren | MicrosoftDocs'
description: 'Lees hoe u een oplossing kunt importeren, bijwerken en exporteren'
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
ms.assetid: 56363ea3-ea76-4311-9b7a-b71675e446fb
caps.latest.revision: 57
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-update-and-export-solutions"></a>Oplossingen importeren, bijwerken en exporteren 

 U kunt oplossingen handmatig importeren met behulp van de onderstaande stappen. Importeer alleen oplossingen die zijn verkregen van een vertrouwde bron. Aanpassingen kunnen code bevatten waardoor gegevens naar externe bronnen kunnen worden verzonden. U kunt de standaardoplossing alleen in de organisatie importeren waarvan u deze hebt geëxporteerd, maar niet in een andere organisatie.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.  
  
2.  Kies in het menu van de oplossingenlijst **Importeren**.  
  
3.  Blader in het dialoogvenster **Oplossing importeren** en de stap **Oplossingspakket selecteren** naar het gecomprimeerde (ZIP- of CAB-)bestand met de oplossing die u wilt importeren. 
  
4.  Kies **Volgende**.  
  
5.  U kunt informatie over de oplossing weergeven voordat u op **Importeren** klikt.  
  
6.  U moet misschien een ogenblik wachten totdat de importoplossing is voltooid. Als dit succesvol is, kunt u de resultaten weergeven en klikken op **Sluiten**.  
  
 Als u wijzigingen hebt geïmporteerd die gepubliceerd moeten worden, moet u aanpassingen publiceren voordat ze beschikbaar worden. 
  
 Als de import niet is geslaagd, ziet u een rapport dat fouten of waarschuwingen weergeeft die zijn vastgelegd. U kunt op **Logboekbestand downloaden** klikken om gegevens vast te leggen over waardoor het importeren is mislukt. De meest voorkomende oorzaak van het mislukken van een oplossingsimport is dat de oplossing niet de vereiste oplossingsonderdelen bevatte.  
  
 Als u het logboekbestand downloadt, vindt u een XML-bestand dat u kunt openen in Office Excel.  
  
> [!NOTE]
>  U kunt geen actieve regelverzameling voor doorsturen bewerken. Dus als u een oplossing importeert met een actieve routeringregel in een organisatie waarin de regel al met dezelfde id bestaat, mislukt de importbewerking. Meer informatie: [Regels maken om aanvragen automatisch te routeren](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/create-rules-automatically-route-cases)  
  
<a name="BKMK_UpdateSolutions"></a>   

## <a name="update-solutions"></a>Oplossingen bijwerken  
 Het kan voorkomen dat u misschien een update van een bestaande beheerde oplossing wilt installeren. De procedure is hetzelfde als voor de installatie van een nieuwe beheerde oplossing, maar u krijgt een paar andere opties. Als u een oplossing bijwerkt die u van iemand anders hebt gekregen, moet u richtlijnen van de oplossingsuitgever krijgen over de opties die u moet kiezen.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Kies in het menu van de oplossingenlijst **Importeren**.  
  
3.  Blader in het dialoogvenster **Oplossing importeren** en de stap **Oplossingspakket selecteren** naar het gecomprimeerde (ZIP- of CAB-)bestand met de oplossing die u wilt bijwerken.  
4.  Kies **Volgende**.  
  
5.  U kunt informatie over de oplossing weergeven voordat u op **Volgende** klikt. Op deze pagina wordt een gele balk weergegeven waarin staat **Dit oplossingspakket bevat een update voor een oplossing die al is geïnstalleerd**.  
  
6.  U hebt de volgende opties:  
  
    - **Aanpassingen behouden (aanbevolen)**  
  
         Wanneer u deze optie inschakelt, blijven onbeheerde aanpassingen aan onderdelen behouden, maar worden sommige updates in deze oplossing mogelijk niet van kracht.  
  
    - **Aanpassingen overschrijven**  
  
         Als u deze optie selecteert, worden onbeheerde aanpassingen overschreven die eerder zijn aangebracht in onderdelen die deel uitmaken van deze oplossing. Alle updates die zijn opgenomen in deze oplossing worden van kracht.  
  
     Kies de gewenste optie en klik vervolgens op **Volgende**.  
  
7.  U moet misschien een ogenblik wachten totdat de importoplossing is voltooid. Als dit succesvol is, kunt u de resultaten weergeven en klikken op **Sluiten**.  
  
 Als u wijzigingen hebt geïmporteerd die gepubliceerd moeten worden, moet u aanpassingen publiceren voordat ze beschikbaar worden. 
  
 Oplossingsuitgevers kunnen u vragen uw bestaande onbeheerde aanpassingen te exporteren, hun beheerde oplossing bij te werken met behulp van de optie om aanpassingen te overschrijven en vervolgens uw onbeheerde aanpassingen opnieuw te importeren. Dit kan ervoor zorgen dat de wijzigingen die zij verwachten, worden toegepast terwijl uw aanpassingen worden gehandhaafd.  
  
<a name="BKMK_ExportSolutions"></a>   

## <a name="export-solutions"></a>Oplossingen exporteren  
 We raden u aan uw onbeheerde aanpassingen regelmatig te exporteren zodat u een back-up hebt voor het geval er iets gebeurt. U kunt beheerde oplossingen niet exporteren.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Selecteer in de lijst de oplossing die u wilt exporteren en klik op **Exporteren**.  
  
3.  In de stap **Aanpassingen publiceren** wordt u eraan herinnerd dat alleen gepubliceerde aanpassingen worden geëxporteerd en u de optie **Alle aanpassingen publiceren** hebt voordat u op **Volgende** klikt.  
  
4.  Als uw oplossing eventuele ontbrekende vereiste onderdelen bevat, ziet u de stap **Er ontbreken vereiste onderdelen**. U kunt deze waarschuwing alleen negeren als u van plan bent deze oplossing weer als onbeheerde oplossing te importeren in de oorspronkelijke organisatie. Als dit niet het geval is, volgt u de instructies in het dialoogvenster om de export te annuleren en de vereiste onderdelen toe te voegen.  
  
5.  In de stap **Systeeminstellingen exporteren (geavanceerd)** kunt u bepaalde systeeminstellingen kiezen om in uw oplossing op te nemen. Als uw oplossing afhankelijk is van de groepen systeeminstellingen, selecteert u ze en klikt u op **Volgende**.  
  
     Raadpleeg **Instellingenopties voor oplossing exporteren** hieronder voor meer informatie over de instellingen die bij elke optie zijn opgenomen.  
  
6.  In de stap **Pakkettype** moet u kiezen of de oplossing als **Onbeheerd** of **Beheerd** moet worden geëxporteerd.  
  
7.  In de volgende stap kunt u een doeloplossing voor een specifieke Dynamics 365-versie kiezen. Deze mogelijkheid wordt meestal gebruikt door ISV's die mogelijk een oplossing willen exporteren die compatibel met een eerdere versie is. Als u van plan bent de oplossing in een organisatie weer te importeren die niet is geüpgrade naar dezelfde versie als de organisatieversie die u gebruikt, accepteert u de standaardwaarde.   
  
8.  Kies **Exporteren** om het oplossingbestand te downloaden.  
  
 Het exacte gedrag voor het downloaden van bestanden varieert tussen browsers.  

<a name="BKMK_SettingsOptionsOnSolutionExport"></a>  
 
## <a name="settings-options-for-solution-export"></a>Opties voor instellingen voor oplossingsexport  
 De volgende tabel geeft de opties weer die beschikbaar zijn wanneer u een oplossing exporteert:  
  
|Groep|Instelling|Beschrijving|  
|-----------|-------------|-----------------|  
|Automatische nummering|Campagnevoorvoegsel|Het voorvoegsel dat wordt gebruikt voor de nummering van campagnes.|  
|Aanvraagvoorvoegsel|Het voorvoegsel dat moet worden gebruikt voor alle aanvragen in de app.|  
|Contractvoorvoegsel|Het voorvoegsel dat moet worden gebruikt voor alle contracten in de app.|  
|Factuurvoorvoegsel|Het voorvoegsel dat moet worden gebruikt voor alle factuurnummers in de app.|  
|Artikelvoorvoegsel|Het voorvoegsel dat moet worden gebruikt voor alle artikelen in de app.|  
|Ordervoorvoegsel|Het voorvoegsel dat moet worden gebruikt voor alle orders in de app.|  
|Lengte van unieke tekenreeks|Het aantal tekens dat moet worden toegevoegd aan factuur-, prijsopgave- en ordernummers.|  
|Kalender|Agendatype|Agendatype voor het systeem. Standaard ingesteld op Gregoriaans (VS)|  
|Datumnotatiecode|Gegevens over hoe de datum wordt weergegeven in Dynamics 365.|  
|Datumscheidingsteken|Het teken dat in de app wordt gebruikt in datums voor het scheiden van de maand, de dag en het jaar.|  
|Max. afspraakduur|Het maximumaantal dagen dat een afspraak kan duren.|  
|Weeknummer weergeven|Gegevens over de vraag of het weeknummer moet worden weergegeven in agendaweergaven in de app.|  
|Tijdnotatiecode|Gegevens over hoe tijden worden weergegeven in de app.|  
|Code voor eerste dag van week|De aangewezen eerste dag van de week in de app.|  
|Aanpassing|Toepassingsmodus is ingeschakeld|Geeft aan of het laden van de app is ingeschakeld in een browservenster dat geen adres-, werk- en menubalk heeft.|  
|E-mail bijhouden|Verzenden van e-mail met niet-omgezette adressen toestaan|Geeft aan of het gebruikers is toegestaan om e-mail naar niet-omgezette betrokkenen te verzenden (betrokkenen moeten nog steeds een e-mailadres hebben).|  
|Interne e-mail negeren|Geeft aan of binnenkomende e-mail die is verzonden door app-gebruikers of -wachtrijen moet worden bijgehouden.|  
|Max. volgnummer|Het volgnummer waarbij recycling plaatsvindt.|  
|Beveiligd frame genereren voor e-mail|De markering om de hoofdtekst van e-mail in het webformulier in een IFrame te renderen met het kenmerk security='restricted'. Dit is extra beveiliging maar kan wel een referentiesprompt veroorzaken.|  
|Voorvoegsel voor volgen|Geschiedenisoverzicht van het volgen van voorvoegsels voor tokens.|  
|Basis volgtoken|De basiswaarde waarmee afzonderlijke token-id's voor het volgen worden geboden aan gebruikers van verschillende installaties.|  
|Cijfers volgtoken|Het aantal cijfers waarmee een token-id voor volgen wordt weergegeven.|  
|Algemeen|Bijlagen blokkeren|Uploaden of downloaden voorkomen van bepaalde typen bijlage die gevaarlijk worden geacht.|  
|Valutanotatiecode|Informatie over hoe valutasymbolen worden gebruikt in de app.|  
|Valutasymbool|Valutasymbool|  
|Weergavevolgorde van volledige naam|De volgorde waarin de namen worden weergegeven in de app.|  
|Aanwezigheid is ingeschakeld|Informatie over de inschakeling van de IM-aanwezigheid.|  
|Negatieve notatie|Geeft aan hoe negatieve bedragen worden weergegeven in de app.|  
|Getalnotatie|Hiermee wordt opgegeven hoe getallen worden weergegeven in de app.|  
|Decimale precisie van prijs|Aantal cijfers achter de komma dat kan worden gebruikt voor prijzen.|  
|Delen met vorige eigenaar bij toewijzen|Gegevens over de vraag of bij toewijzing moet worden gedeeld met de vorige eigenaar.|  
|Marketing|Automatisch maken van antwoorden toestaan|Geeft aan of automatisch een antwoord mag worden gemaakt|  
|Automatisch afmelden toestaan|Geeft aan of abonnementen automatisch mogen worden beëindigd.|  
|Bevestiging van automatisch afmelden toestaan|Geeft aan of er automatisch een e-mailbericht mag worden verzonden om te bevestigen dat een abonnement is beëindigd.|  
|Uitvoering van marketing-e-mail toestaan|Geeft aan of e-mailberichten voor marketing mogen worden uitgevoerd.|  
| Outlook-synchronisatie|Adresboeksynchronisatie toestaan|Geeft aan of de synchronisatie van het adresboek in Microsoft Office Outlook op de achtergrond is toegestaan.|  
|Geplande offlinesynchronisatie toestaan|Geeft aan of offlinesynchronisatie op de achtergrond in Outlook is toegestaan.|  
|Geplande synchronisatie toestaan|Geeft aan of geplande synchronisaties met Outlook zijn toegestaan.|  
|Pollingfrequentie voor e-mailverzending|Normale pollingfrequentie voor het verzenden van e-mail in Outlook.|  
|Min. frequentie voor adressynchronisatie|Normale pollingfrequentie die wordt gebruikt voor adresboeksynchronisatie in Outlook.|  
|Min. frequentie voor offlinesynchronisatie|Normale pollingfrequentie die wordt gebruikt voor offlinesynchronisatie op de achtergrond in Outlook.|  
|Min. synchronisatiefrequentie|De minimaal toegestane periode tussen geplande Outlook-synchronisaties.|  
|Max. cycli voor automatisch labelen|Het maximumaantal agressieve polling-cycli dat voor automatische tags voor e-mail wordt gebruikt als een nieuwe e-mail wordt ontvangen.|  
|Interval voor automatisch labelen|Normale pollingfrequentie die wordt gebruikt voor automatische tagging van e-mail in Outlook.|  
|ISV-configuratie|De configuratie van het uiterlijk van de servicekalender|U kunt visuele stijlen voor servicekalenders definiëren.

Meer informatie: [De configuratie van het uiterlijk van de servicekalender](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/service-calendar-appearance-configuration)|

  
## <a name="next-steps"></a>Volgende stappen

[Oplossingen en patches distribueren](use-segmented-solutions-patches-simplify-updates.md)
