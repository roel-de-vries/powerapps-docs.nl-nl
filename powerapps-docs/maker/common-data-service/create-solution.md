---
title: Een oplossing maken | MicrosoftDocs
description: Leren hoe u een oplossing maakt
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
  - PowerApps
author: Mattp123
ms.assetid: e21a4876-08b4-417a-a644-c577a27c5cf1
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-solution"></a>Een oplossing maken

Aangezien de standaardoplossing alle oplossingsonderdelen bevat, is het misschien gemakkelijker om alleen de oplossingsonderdelen te zoeken die u hebt aangepast als u een afzonderlijke oplossing maakt en daar al uw aanpassingen doet. Dit maakt het ook gemakkelijk om een back-up van uw oplossing als een kleiner bestand te exporteren. Als u dit wilt doen, moet u er altijd aan denken om de oplossingsonderdelen die u bewerkt toe te voegen aan deze oplossing. Wanneer u nieuwe oplossingsonderdelen maakt, moet u deze altijd in de context van deze oplossing maken. Op deze manier wordt het voorvoegsel van de oplossingsuitgeveraanpassing consistent toegepast. Nadat u oplossingsonderdelen in uw oplossing hebt gemaakt, of bestaande oplossingsonderdelen aan die oplossing hebt toegevoegd, kunt u ze, als u dat wilt, ook bewerken in de standaardoplossing.  
  
 Voor meer informatie over oplossingsconcepten raadpleegt u [Werken met oplossingen](solutions-overview.md).  
  
1.  Navigeer naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**. 
  
2.  Klik op **Nieuw** en vul de vereiste velden in voor de oplossing.  
  
    |Veld|Beschrijving|  
    |-----------|-----------------|  
    |**Weergavenaam**|De naam die in de lijst met oplossingen wordt weergegeven. U kunt dit later wijzigen.|  
    |**Naam**|De unieke naam van de oplossing. Dit wordt gegenereerd met behulp van de waarde die u in het Weergavenaamveld invoert. U kunt dit bewerken voordat u de oplossing opslaat, maar nadat u de oplossing hebt opgeslagen, kunt u het niet wijzigen.|  
    |**Uitgever**|U kunt de standaarduitgever selecteren of een nieuwe uitgever maken. U moet de standaarduitgever voor uw organisatie gebruiken, tenzij u van plan bent uw oplossing te distribueren.|  
    |**Versie**|Voer een nummer in voor de versie van uw oplossing. Dit is alleen belangrijk als u uw oplossing exporteert. Het versienummer wordt opgenomen in de bestandsnaam als u de oplossing exporteert.|  
  
3.  Kies **Opslaan**.  
  
 Nadat u de oplossing hebt opgeslagen, wilt u misschien informatie toevoegen aan velden die niet vereist zijn. Deze stappen zijn optioneel. Gebruik het veld **Beschrijving** om de oplossing te beschrijven en kies een HTML-webresource als een **Configuratiepagina** voor de oplossing. De configuratiepagina wordt meestal gebruikt door ISV's die oplossingen distribueren. Als dit is ingesteld, ziet u een nieuw **Configuratie**-knooppunt onder het knooppunt **Informatie** om deze webresource weer te geven. Ontwikkelaars zullen deze pagina gebruiken om instructies of besturingselementen op te nemen waarmee u configuratiegegevens kunt instellen of hun oplossing kunt starten.  
  
<a name="BKMK_AddSolutionComponents"></a>   

## <a name="add-solution-components"></a>Oplossingsonderdelen toevoegen  
 Nadat u uw oplossing hebt gemaakt, bevat die geen oplossingsonderdelen. U kunt nieuwe oplossingsonderdelen maken of de knop **Bestaande onderdelen toevoegen** in het lijstmenu gebruiken om oplossingsonderdelen van de standaardoplossing toe te voegen.  
  
 Als u dit doet, verschijnt er misschien een **Er ontbreken vereiste onderdelen**-dialoogvenster.  
   
 ![Dialoog Vereiste onderdelen toevoegen](media/crm-itpro-cust-addrequiredcomponents.PNG "Dialoog Vereiste onderdelen toevoegen")  
  
 Dit dialoogvenster waarschuwt u dat het oplossingsonderdeel afhankelijk is van andere oplossingsonderdelen. Als u **Nee, vereiste onderdelen niet toevoegen** selecteert, kan de oplossing mislukken als u die in een andere organisatie importeert waar al die vereiste componenten niet aanwezig zijn. Als de oplossingsimport slaagt, is het gedrag in de andere oplossing misschien niet hetzelfde als de oorspronkelijke organisatie, doordat de onderdelen anders zijn geconfigureerd dan die in de bronoplossing.  
  
 Over het algemeen is het een goed idee om de vereiste onderdelen op te nemen als u van plan bent de oplossing naar een andere organisatie te exporteren. Als u deze onderdelen niet toevoegt wanneer u een afzonderlijk oplossingsonderdeel toevoegt, kunt u later weer verdergaan, het oplossingsonderdeel dat u hebt toegevoegd selecteren, en klikken op **Vereiste onderdelen toevoegen** in het menu.  
  
 Als u niet van plan bent de oplossing te exporteren, of alleen als u van plan bent deze te exporteren als een onbeheerde oplossing en weer te importeren in dezelfde organisatie, is het niet noodzakelijk om vereiste onderdelen op te nemen. Als u ooit de oplossing exporteert, ziet u nog een waarschuwing die aangeeft er bepaalde vereiste onderdelen ontbreken. Als u deze oplossing alleen terug gaat importeren in dezelfde organisatie, kunt u deze waarschuwing negeren. De stappen voor het bewerken van de toepassingsnavigatie of het lint zonder een extern bewerkingsprogramma te gebruiken, verwachten dat u de oplossing terugexporteert naar dezelfde organisatie.  

> [!IMPORTANT]
>  Als u afspraken in oplossingen wilt opnemen, raden wij sterk aan niet alleen afspraken en alleen terugkerende afspraken in afzonderlijke oplossingen op te nemen. Als u afzonderlijke oplossingen met verschillende typen afspraken installeert en verwijdert, treedt een SQL Server-fout op en moet u de afspraken opnieuw maken. 
