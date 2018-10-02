---
title: Het voorvoegsel voor de oplossingsuitgever wijzigen | MicrosoftDocs
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: ece684h8-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="change-the-solution-publisher-prefix"></a>Het voorvoegsel voor de oplossingsuitgever wijzigen

Elke aanpassing die u maakt, maakt deel uit van een oplossing. Elke oplossing heeft een uitgever. Standaard is de oplossing waarmee u in PowerApps werkt de **Common Data Services-standaardoplossing** die is gekoppeld aan de **CDS-standaarduitgever**.

Het voorvoegsel van de standaardaanpassing wordt willekeurig toegewezen voor deze uitgever. Het kan bijvoorbeeld `cr8a3`ijn. Dit betekent dat de naam van elk nieuw voor uw organisatie gemaakt item van metagegevens dit voorvoegsel krijgt voor de namen die een unieke identificatie vormen voor de items. Als u een nieuwe entiteit maakt met de naam **Animal**, is de unieke naam die door CDS voor Apps wordt gebruikt `cr8a3_animal`. Hetzelfde geldt voor nieuwe velden (kenmerken), relaties, of opties van optiesets.

Tenzij u uw beheerde oplossing zo distribueert dat deze samen met metagegevensitems wordt geïnstalleerd die voor een andere oplossingsuitgever zijn gemaakt, is het niet echt belangrijk wat het aanpassingsvoorvoegsel is. Het is niet zichtbaar voor de meeste mensen die uw apps gebruiken. Maar het wordt weergegeven aan ontwikkelaars en andere technische persoon die onder andere rapporten maken. Aan de hand van het voorvoegsel komt u sneller te weten met elke oplossing het item is toegevoegd.

Daarom willen veel mensen het voorvoegsel van de oplossingsuitgever wijzigen zodat het meer betekenis heeft, met name bij het weergeven van metagegevensitems die de voorvoegsels bevatten die uit andere oplossingen zijn geïmporteerd. 

> [!NOTE]
> Als u het voorvoegsel van de oplossingsuitgever wijzigt, moet u dat doen voordat u nieuwe metagegevensitems maakt. U kunt de namen van metagegevensitems niet wijzigen.
> Als u de waarde van het aanpassingsvoorvoegsel wijzigt, dient u met tab naar het volgende veld te gaan. Het **Voorvoegsel voor optiewaarde** genereert automatisch een getal dat op het aanpassingsvoorvoegsel is gebaseerd. Dit getal wordt gebruikt als u opties voor optiesets toevoegt en biedt een indicator van de oplossing die is gebruikt om de optie toe te voegen. 

## <a name="change-the-solution-publisher-prefix-for-the-cds-default-publisher"></a>Het voorvoegsel van de oplossingsuitgever de CDS-standaarduitgever wijzigen  

 1. Selecteer in de PowerApps-portal **Modelgestuurd** in de linkerbenedenhoek.
 2. Klik op **Geavanceerd** in de linkernavigatie om **Common Data Services-standaardoplossing** te openen
 3. Selecteer in de oplossingenverkenner het gebied **Informatie** in de linkernavigatie.
 4. Klik op de koppeling **Uitgever** om het formulier **CDS-standaarduitgever** te openen.
 5. Bewerk de waarde van het veld **Voorvoegsel** in het gewenste aanpassingsvoorvoegsel.
 6. Klik op **Opslaan en sluiten**.
  
## <a name="change-the-solution-publisher-prefix-for-any-publisher"></a>Het voorvoegsel van de oplossingsuitgever veranderen voor een willekeurige uitgever

Mensen die hun oplossingen distribueren, werken meestal in een oplossing die zij maken in plaats van de **Common Data Services-standaardoplossing**. Het aanpassingsvoorvoegsel wordt gewoonlijk ingesteld wanneer ze de oplossing maken. U kunt het aanpassingsvoorvoegsel maken voor een andere onbeheerde oplossing waarmee u werkt door de volgende stappen uit te voeren: 

 1. Selecteer in de PowerApps-portal **Modelgestuurd** in de linkerbenedenhoek.
 2. Klik op **Geavanceerd** in de linkernavigatie om **Common Data Services-standaardoplossing** te openen
 3. Bewerk de URL van de pagina om alles na `dynamics.com` te verwijderen en de pagina opnieuw te laden.
 4. Navigeer naar **Instellingen** > **Aanpassing** > **Aanpassingen** 
 5. Klik op **Uitgevers**. U kunt nu een lijst met beschikbare uitgevers zien.
 6. Klik op de uitgever die u wilt bewerken om het uitgeversformulier te openen.
 7. Bewerk de waarde van het veld **Voorvoegsel** in het gewenste aanpassingsvoorvoegsel.
 6. Klik op **Opslaan en sluiten**.
  
