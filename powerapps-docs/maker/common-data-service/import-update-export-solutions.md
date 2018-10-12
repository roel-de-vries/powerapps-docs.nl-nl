---
title: Oplossingen importeren, bijwerken en exporteren | MicrosoftDocs
description: Meer informatie over het importeren, bijwerken en exporteren van een oplossing
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
ms.openlocfilehash: 89907e80085fe2bfcf3c38972724a0f9b55836c7
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675524"
---
# <a name="import-update-and-export-solutions"></a>Oplossingen importeren, bijwerken en exporteren 

 U kunt oplossingen handmatig importeren met de onderstaande stappen. Importeer alleen oplossingen die u hebt verkregen van een vertrouwde bron. Aanpassingen kunnen code bevatten die gegevens naar externe bronnen kunnen verzenden. U kunt de standaardoplossing alleen importeren in het bedrijf waaruit u die hebt geëxporteerd, maar niet in een ander bedrijf.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.  
  
2.  Kies **Importeren** in het lijstmenu met oplossingen.  
  
3.  Navigeer in de stap **Oplossingspakket selecteren** in het dialoogvenster **Oplossing importeren** naar het gecomprimeerde (.zip of .cab) bestand dat de oplossing bevat die u wilt importeren. 
  
4.  Kies **Volgende**.  
  
5.  U kunt de informatie over de oplossing bekijken voordat u **Importeren** kiest.  
  
6.  U moet mogelijk even geduld hebben totdat het importeren van de oplossing is voltooid. Als dat is geslaagd, kunt u de resultaten bekijken en **Sluiten** kiezen.  
  
 Als u wijzigingen hebt geïmporteerd die moeten worden gepubliceerd, moet u de aanpassingen publiceren voordat ze beschikbaar zijn. 
  
 Als het importeren niet is gelukt, ziet u een rapport met mogelijke fouten of waarschuwingen die zijn vastgelegd. U kunt **Logboekbestand downloaden** kiezen voor meer informatie over de oorzaak van het mislukken van het importeren. De meest voorkomende oorzaak dat het importeren van een oplossing mislukt, is dat de oplossing bepaalde vereiste oplossingsonderdelen niet bevat.  
  
 Wanneer u het logboekbestand downloadt, ziet u een XML-bestand dat u kunt openen met Office Excel.  
  
> [!NOTE]
>  U kunt een actieve regelset voor doorsturen niet bewerken. Als u een oplossing importeert die een actieve regelset voor routering bevat naar een bedrijf waar die regel al bestaat met hetzelfde ID, zal het importeren van de oplossing mislukken. Meer informatie: [Regels maken voor het automatisch verzenden van aanvragen](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/create-rules-automatically-route-cases)  
  
<a name="BKMK_UpdateSolutions"></a>   

## <a name="update-solutions"></a>Oplossingen bijwerken  
 Er zijn momenten dat u mogelijk een update wilt installeren voor een bestaande beheerde oplossing. De procedure is vergelijkbaar met het installeren van een nieuwe beheerde oplossing, behalve dat u andere opties krijgt. Als u een oplossing bijwerkt die u van een ander hebt gekregen, zou u hulp moeten krijgen van de uitgever van de oplossing over welke opties u moet kiezen.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Kies **Importeren** in het lijstmenu met oplossingen.  
  
3.  Navigeer in de stap **Oplossingspakket selecteren** in het dialoogvenster **Oplossing importeren** naar het gecomprimeerde (.zip of .cab) bestand dat de oplossing bevat die u wilt bijwerken.  
4.  Kies **Volgende**.  
  
5.  Voordat u **Volgende** kiest, kunt u informatie bekijken over de oplossing. Deze pagina toont een gele balk met de mededeling **Dit oplossingspakket bevat een update voor een oplossing die al is geïnstalleerd**.  
  
6.  U hebt de volgende opties:  
  
    - **Aanpassingen behouden (Aanbevolen)**  
  
         Door deze optie te selecteren, behoudt u alle onbeheerde aanpassingen die zijn uitgevoerd aan onderdelen, maar het impliceert ook dat bepaalde updates in deze oplossing mogelijk niet van kracht worden.  
  
    - **Aanpassingen overschrijven**  
  
         Door deze optie te selecteren, overschrijft u alle onbeheerde aanpassingen die eerder zijn uitgevoerd aan onderdelen in deze oplossing. Alle updates in deze oplossing zullen van kracht worden.  
  
     Kies de juiste optie en kies vervolgens **Volgende**.  
  
7.  U moet mogelijk even geduld hebben totdat het importeren van de oplossing is voltooid. Als dat is geslaagd, kunt u de resultaten bekijken en **Sluiten** kiezen.  
  
 Als u wijzigingen hebt geïmporteerd die moeten worden gepubliceerd, moet u de aanpassingen publiceren voordat ze beschikbaar zijn. 
  
 Oplossingsuitgevers kunnen u vragen uw bestaande onbeheerde aanpassingen te exporteren, hun beheerde oplossing bij te werken met de optie aanpassingen te overschrijven en dan uw onbeheerde aanpassingen opnieuw te importeren. Hiermee kunnen zij ervoor zorgen dat de wijzigingen die zij verwachten, worden aangebracht, terwijl uw aanpassingen behouden blijven.  
  
<a name="BKMK_ExportSolutions"></a>   

## <a name="export-solutions"></a>Oplossingen exporteren  
 Het is raadzaam dat u uw onbeheerde aanpassingen regelmatig exporteert, zodat u een back-up hebt als er iets gebeurt. U kunt beheerde oplossingen niet exporteren.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Selecteer de oplossing die u wilt exporteren in de lijst en kies **Exporteren**.  
  
3.  In de stap **Aanpassingen publiceren** wordt u eraan herinnerd dat alleen gepubliceerde aanpassingen worden geëxporteerd en heeft u de optie **Alle aanpassingen publiceren** voordat u **Volgende** kiest.  
  
4.  Als uw oplossing ontbrekende vereiste onderdelen bevat, ziet u de stap **Ontbrekende vereiste onderdelen**. U kunt deze waarschuwing alleen negeren als u van plan bent dit als onbeheerde oplossing in het originele bedrijf te importeren. Volg anders de instructies in het dialoogvenster om de export te annuleren en de vereiste onderdelen toe te voegen.  
  
5.  In de stap **Systeeminstellingen exporteren (Geavanceerd)** kunt u kiezen bepaalde systeeminstellingen in uw oplossing op te nemen. Als uw oplossing afhankelijk is van een van de groepen met systeeminstellingen, selecteer die dan en kies **Volgende**.  
  
     Zie **Instellingsopties voor het exporteren van oplossingen** hieronder voor meer informatie over de instellingen die in elke optie zijn opgenomen.  
  
6.  In de stap **Pakkettype** moet u kiezen of u de oplossing als **Onbeheerde** of **Beheerde** oplossing wilt exporteren.  
  
7.  In de volgende stap kunt u een doeloplossing kiezen voor een specifieke Dynamics 365-versie. Deze optie wordt doorgaans gebruikt door ISV’s die een oplossing willen exporteren die compatibel is met een eerdere versie. Accepteer de standaardwaarde, tenzij u van plan bent deze oplossing te importeren in een bedrijf dat niet is bijgewerkt naar dezelfde versie als de bedrijfsversie die u gebruikt.   
  
8.  Kies **Exporteren** om het oplossingsbestand te downloaden.  
  
 Het precieze gedrag voor het downloaden van bestanden verschilt per browser.  

<a name="BKMK_SettingsOptionsOnSolutionExport"></a>  
 
## <a name="settings-options-for-solution-export"></a>Instellingsopties voor oplossingsexpert  
 De volgende tabel toont de beschikbare opties wanneer u een oplossing exporteert:  
  
|Groep|Instelling|Beschrijving|  
|-----------|-------------|-----------------|  
|Automatische nummering|Campagnevoorvoegsel|Voorvoegsel gebruikt voor nummering van campagne.|  
|Case-voorvoegsel|Voorvoegsel voor alle cases in de app.|  
|Contractvoorvoegsel|Voorvoegsel voor alle contracten in de app.|  
|Factuurvoorvoegsel|Voorvoegsel voor alle factuurnummers in de app.|  
|Artikelvoorvoegsel|Voorvoegsel voor alle artikelen in de app.|  
|Bestellingsvoorvoegsel|Voorvoegsel voor alle bestellingen in de app.|  
|Unieke tekenreekslengte|Aantal tekens toegevoegd aan factuur-, offerte- en bestelnummers.|  
|Agenda|Agendatype|Agendatype voor het systeem. Standaard ingesteld op Gregoriaans V.S.|  
|Datumnotatiecode|Informatie over hoe de datum wordt weergegeven in Dynamics 365.|  
|Datumscheidingsteken|Teken dat wordt gebruikt om de dag, maand en het jaar in datums te scheiden in de app.|  
|Maximale duur afspraak|Maximaal aantal dagen dat een afspraak kan duren.|  
|Weeknummer tonen|Informatie die aangeeft of het weeknummer in agendaweergaven wordt weergegeven in de app.|  
|Tijdnotatiecode|Informatie die aangeeft hoe de tijd wordt weergegeven in de app.|  
|Code voor begindag week|Aangewezen eerste dag van de week in de app.|  
|Aanpassing|Is toepassingsmodus ingeschakeld|Geeft aan of het laden van een app in een browservenster dat geen adres, hulpprogramma en menubalken heeft, is ingeschakeld.|  
|E-mail bijhouden|E-mail met niet-omgezet adres verzenden|Geeft aan of gebruikers een e-mail mogen sturen naar niet-omgezette partijen (partijen moeten nog steeds een e-mailadres hebben).|  
|Interne e-mail negeren|Geeft aan of inkomende e-mail verzonden door app-gebruikers of -wachtrijen moeten worden gevolgd.|  
|Maximale traceringsnummer|Maximale traceringsnummer voordat ze worden gerecycled.|  
|Beveiligd kader voor e-mail genereren|Vlag om de hoofdtekst van een e-mail in het webformulier in een IFRAME weer te geven met het kenmerk beveiliging=’beperkt’ ingeschakeld. Dit is aanvullende beveiliging, maar kan leiden tot een referentieprompt.|  
|Traceervoorvoegsel|Historische lijst met traceertokenvoorvoegsels.|  
|Traceertokenbasis|Basisnummer dat wordt gebruikt om verschillende traceertoken-ID’s te bieden aan gebruikers behorend bij verschillende implementaties.|  
|Traceertokencijfers|Aantal cijfers dat wordt gebruikt voor een traceertoken-id.|  
|Algemeen|Bijlagen blokkeren|Uploaden of downloaden van bepaalde bijlagetypen die als gevaarlijk worden beschouwd, voorkomen.|  
|Valutanotatiecode|Informatie over hoe valuta worden geplaatst in de app.|  
|Valutasymbool|Valutasymbool|  
|Weergavevolgorde volledige naam|De volgorde waarin namen worden weergegeven in de app.|  
|Aanwezigheid ingeschakeld|Informatie of de IM-aanwezigheid is ingeschakeld.|  
|Negatieve indeling|Informatie die aangeeft hoe negatieve getallen worden weergegeven in de app.|  
|Nummerindeling|Specificatie hoe nummers worden weergegeven in de app.|  
|Decimale precisie bij prijzen|Aantal decimaalposities dat kan worden gebruikt voor prijzen.|  
|Delen met vorige eigenaar bij toewijzing|Informatie die aangeeft of moet worden gedeeld met de vorige eigenaar bij toewijzing.|  
|Marketing|Toestaan Automatisch antwoord maken|Geeft aan of het maken van een automatisch antwoord is toegestaan|  
|Toestaan Automatisch afmelden|Geeft aan of het automatisch afmelden is toegestaan.|  
|Toestaan Kennisgeving automatisch afmelden|Geeft aan of een bevestigingse-mail automatisch mag worden verzonden.|  
|Marketinge-mailuitvoering toestaan|Geeft aan of marketinge-mailuitvoering is toegestaan.|  
| Outlook-synchronisatie|Adresboeksynchronisatie toestaan|Geeft aan of achtergrondsynchronisatie van het adresboek in Microsoft Office Outlook is toegestaan.|  
|Geplande offlinesynchronisatie|Geeft aan of offline achtergrondsynchronisatie in Outlook is toegestaan.|  
|Geplande synchronisatie toestaan|Geeft aan of geplande synchronisaties naar Outlook zijn toegestaan.|  
|Frequentie navraage-mails|Normale navraagfrequentie die wordt gebruikt voor het verzenden van e-mails in Outlook.|  
|Minimale frequentie adressynchronisatie|Normale frequentie die wordt gebruikt voor adresboeksynchronisatie in Outlook.|  
|Minimale frequentie offline synchronisatie|Normale frequentie die wordt gebruikt voor offline achtergrondsynchronisatie in Outlook.|  
|Minimale synchronisatiefrequentie|Minimale frequentie tussen geplande [!INCLUDEOutlooksynchronizaties.|  
|Maximale Auto-Tag-cycli|Maximum aantal navraagcycli die worden uitgevoerd voor auto-tagging van e-mail als een nieuwe e-mail is ontvangen.|  
|Auto-Tag-interval|Normale navraagfrequentie die wordt gebruikt voor auto-tagging van e-mail in Outlook.|  
|ISV-configuratie|Weergaveconfiguratie serviceagenda|U kunt visuele stijlen definiëren voor serviceagenda’s.

Meer informatie: [Weergaveconfiguratie serviceagenda](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/service-calendar-appearance-configuration)|

  
## <a name="next-steps"></a>Volgende stappen

[Oplossingen en patches distribueren](use-segmented-solutions-patches-simplify-updates.md)