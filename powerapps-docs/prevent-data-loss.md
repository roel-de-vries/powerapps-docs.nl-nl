---
title: Beleid ter preventie van gegevensverlies (DLP) | Microsoft Docs
description: Inleiding in beleid ter preventie van gegevensverlies Microsoft PowerApps.
services: 
suite: powerapps
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/28/2016
ms.author: deonhe
ms.openlocfilehash: a9f6bf12672c425a30d05a8072aafd34945eb795
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="data-loss-prevention-dlp-policies"></a>Beleid ter preventie van gegevensverlies (DLP)

De gegevens van een organisatie zijn essentieel om succes te behalen. Gegevens moeten dus te allen tijde beschikbaar zijn om beslissingen te kunnen nemen, maar ze moeten ook worden beveiligd zodat ze niet worden gedeeld met doelgroepen die er geen toegang toe zouden mogen hebben. Als u deze gegevens wilt beveiligen, biedt Microsoft PowerApps (PowerApps) de mogelijkheid om beleid te maken en af te dwingen waarmee wordt gedefinieerd met welke consumentenservices/connectors zakelijke gegevens mogen worden gedeeld. Met dit beleid wordt gedefinieerd hoe gegevens mogen worden gedeeld. Het beleid wordt aangeduid als beleid ter preventie van gegevensverlies (DLP).  

## <a name="why-create-a-dlp-policy"></a>Waarom u DLP-beleid moet maken
U maakt DLP-beleid om op te geven met welke consumentenservices zakelijke gegevens mogen worden gedeeld. Een organisatie die gebruikmaakt van PowerApps wil bijvoorbeeld niet dat de zakelijke gegevens uit SharePoint automatisch worden gepubliceerd op Twitter. Om dit te voorkomen, kunt u een DLP-beleid maken waarmee wordt voorkomen dat SharePoint-gegevens worden gebruikt als bron voor tweets.

Voordelen van een DLP-beleid:
* Zorgt ervoor dat gegevens op een uniforme manier worden beheerd in de gehele organisatie  
* Voorkomt dat belangrijke bedrijfsgegevens per ongeluk worden gepubliceerd via services zoals sociale-mediasites.   

## <a name="managing-dlp-policies"></a>DLP-beleid beheren
### <a name="prerequisites"></a>Vereisten
Als u DLP-beleid wilt maken, bewerken of verwijderen, zijn de volgende zaken vereist:

* Machtigingen van een omgevingsbeheerder of tenantbeheerder. U vindt in het [omgevingenonderwerp](environments-administration.md) meer informatie over machtigingen

### <a name="create-a-dlp-policy"></a>Een DLP-beleid maken
Als u een DLP-beleid wilt maken, moet u machtigingen hebben voor ten minste één omgeving.  

Volg deze stappen om een DLP-beleid te maken waarmee u voorkomt dat de gegevens die in uw SharePoint-database zijn opgeslagen worden gepubliceerd op Twitter:  

1. Selecteer op het tabblad Gegevensbeleid de koppeling **Nieuw beleid**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-1.png)    
2. Voer de naam van het DLP-beleid in als *Secure Data Access for Contoso* in het label **Naam van het gegevensbeleid** boven aan de pagina die wordt geopend:   
   ![Aanmelden](./media/prevent-data-loss/create-policy-2.png)  
3. Selecteer de [omgeving](environments-administration.md) op het tabblad **Van toepassing op**.  
   ![Aanmelden](./media/prevent-data-loss/create-policy-3.png)  
4. Selecteer het tabblad **Gegevensgroepen**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-4.png)  
5. Selecteer de koppeling **+ Toevoegen** in het groepsvak **Alleen zakelijke gegevens**:    
   ![Aanmelden](./media/prevent-data-loss/create-policy-5.png)  
6. Selecteer de services **SharePoint** en **Salesforce** op de pagina **Services toevoegen**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-6.png)  
7. Selecteer de knop **Services toevoegen** om de services die u hebt geselecteerd toe te voegen aan de lijst met services die mogen worden gebruikt voor het delen van zakelijke gegevens:    
   ![Aanmelden](./media/prevent-data-loss/create-policy-7.png)  
8. Selecteer **Beleid opslaan**:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-8.png)  
9. Na enkele ogenblikken wordt uw nieuwe DLP-beleid weergegeven in de lijst met beleidsregels voor preventie van gegevensverlies:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-9.png)  
10. **Optioneel** Stuur een e-mail of bericht naar uw team met de informatie dat er een nieuw DLP-beleid beschikbaar is.

U hebt een DLP-beleid gemaakt waarmee apps gegevens kunnen delen tussen SharePoint en Salesforce en waarmee het delen van gegevens met andere services wordt geblokkeerd.  

### <a name="find-a-dlp-policy"></a>Een DLP-beleid zoeken
#### <a name="admins"></a>Beheerders
Beheerders kunt de zoekfunctie uit het beheercentrum gebruiken om specifiek DLP-beleid te zoeken.  

> [!NOTE]
> Beheerders moeten al het DLP-beleid publiceren zodat gebruikers in de organisatie zich vóór het maken van PowerApps bewust zijn van wat het beleid is.

#### <a name="makers"></a>Makers
Als u geen beheerdersmachtigingen hebt en u meer wilt weten over de DLP-beleidsregels in uw organisatie, neemt u contact op met de beheerder. U vindt ook meer informatie in het [onderwerp voor de makers van omgevingen](environments-overview.md)  

> [!NOTE]
> Alleen beheerders kunnen DLP-beleid bewerken of verwijderen.  

### <a name="edit-a-dlp-policy"></a>Een DLP-beleid bewerken
1. Open het beheercentrum door naar https://admin.powerapps.com te gaan.   
2. In het beheercentrum dat wordt geopend, selecteert u de koppeling **Gegevensbeleid** aan de linkerkant.  
   ![Aanmelden](./media/prevent-data-loss/2.png)  
3. Zoek in de lijst met bestaand DLP-beleid en selecteer de bewerkkoppeling naast het beleid dat u wilt bewerken:  
   ![Aanmelden](./media/prevent-data-loss/3.png)  
4. Breng de gewenste wijzigingen aan. U kunt bijvoorbeeld de omgeving of de services in de gegevensgroepen wijzigen.  
5. Selecteer **Beleid opslaan** om uw wijzigingen op te slaan:  
   ![Aanmelden](./media/prevent-data-loss/create-policy-8.png)  

Uw beleid is bijgewerkt. U kunt controleren of de wijzigingen aan het beleid zijn aangebracht. Ga daarvoor naar de lijst met beleidsregels voor de preventie van gegevensverlies en controleer de eigenschappen.   

### <a name="delete-a-dlp-policy"></a>Een DLP-beleid verwijderen
1. Open het beheercentrum door naar https://admin.powerapps.com te gaan    
2. In het beheercentrum dat wordt geopend, selecteert u de koppeling **Gegevensbeleid** aan de linkerkant.  
   ![Aanmelden](./media/prevent-data-loss/2.png)  
3. Zoek in de lijst met bestaand DLP-beleid en selecteer de verwijderkoppeling naast het beleid dat u wilt verwijderen:  
   ![Aanmelden](./media/prevent-data-loss/3-delete.png)  
4. Bevestig dat u het beleid echt wilt verwijderen door de knop **Verwijderen** te selecteren:  
   ![Aanmelden](./media/prevent-data-loss/4.png)  

Het beleid is nu verwijderd. U kunt controleren of het beleid niet meer wordt vermeld in de lijst met beleidsregels voor de preventie van gegevensverlies. Selecteer daarvoor de koppeling **Gegevensbeleid** aan de linkerkant en controleer de lijst met beleidsregels.   

### <a name="dlp-policy-permissions"></a>DLP-beleidsmachtigingen
Alleen tenant- en omgevingsbeheerders kunnen DLP-beleid maken en bewerken. U vindt in het [omgevingen](environments-administration.md)onderwerp meer informatie over machtigingen.  

## <a name="next-steps"></a>Volgende stappen
* [Meer informatie over omgevingen](environments-administration.md)  
* [Meer informatie over Microsoft PowerApps](getting-started.md)  
* [Meer informatie over het beheercentrum](introduction-to-the-admin-center.md)  

