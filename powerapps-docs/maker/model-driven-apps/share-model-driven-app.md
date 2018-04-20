---
title: Zelfstudie voor het delen van modelgestuurde apps met PowerApps | Microsoft Docs
description: In deze zelfstudie vindt u informatie over het delen van een modelgestuurde app
services: ''
suite: powerapps
documentationcenter: ''
author: Mattp123
manager: brycho
editor: ''
tags: ''
ms.service: powerapps
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 4f971668b506776cfd1a9cce2f61d591a4a0db5e
ms.sourcegitcommit: d7ed5144f96d1ecc17084c30ed0e2ba3c6b03c26
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2018
---
# <a name="tutorial-share-a-model-driven-app-with-powerapps"></a>Zelfstudie: Een modelgestuurde app delen met PowerApps

[!INCLUDE [powerapps](../../includes/powerapps.md)]-apps gebruiken een op rollen gebaseerde beveiliging voor delen. Het fundamentele concept in een op rollen gebaseerde beveiliging is dat een beveiligingsrol rechten bevat die een reeks acties definiëren die in de app kunnen worden uitgevoerd. Alle gebruikers van de app moeten worden toegewezen aan een of meer vooraf gedefinieerde of aangepaste rollen. Rollen kunnen eveneens worden toegewezen aan teams. Wanneer een gebruiker of een team wordt toegewezen aan een van deze rollen, krijgen de persoon of leden van het team de set bevoegdheden die aan die rol zijn gekoppeld. 

In deze zelfstudie voert u de taken uit voor het delen van een modelgestuurde app, zodat anderen deze kunnen gebruiken. U leert het volgende:
- Een aangepaste beveiligingsrol maken
- Gebruikers toewijzen aan de aangepaste beveiligingsrol
- De beveiligingsrol toewijzen aan een app

> [!IMPORTANT]
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

## <a name="prerequisites"></a>Vereisten
Voor het delen van een app moet u over de rol [!INCLUDE [powerapps](../../includes/powerapps.md)] Omgevingsbeheerder of Systeembeheerder beschikken. 

## <a name="sign-in-to-powerapps"></a>Meld u aan bij PowerApps
Meld u aan bij [PowerApps](https://powerapps.microsoft.com/). Als u nog geen [!INCLUDE [powerapps](../../includes/powerapps.md)] account hebt, selecteert u de koppeling **Gratis aan de slag**.

## <a name="share-an-app"></a>Een app delen 
De zelfstudie volgt het bedrijf Contoso: een bedrijf dat handelt in producten voor de cosmetische verzorging van honden en katten. Een app met een aangepaste entiteit voor het bijhouden van de cosmetische verzorgingsbedrijf voor honden en katten is al gemaakt en gepubliceerd. De app moet nu worden gedeeld, zodat de medewerkers van het cosmetische dierverzorgingsbedrijf deze kunnen gebruiken. Als u de app wilt delen, wijst een beheerder of de maker van de app een of meer beveiligingsrollen toe aan gebruikers en aan de app. 

## <a name="create-or-configure-a-security-role"></a>Een beveiligingsrol maken of configureren
De [!INCLUDE [powerapps](../../includes/powerapps.md)]omgeving bevat [vooraf gedefinieerde beveiligingsrollen](#about-predefined-security-roles) die overeenkomen met algemene gebruikerstaken. Voor deze beveiligingsrollen zijn toegangsniveaus gedefinieerd waarmee toegang wordt geboden tot de minimale hoeveelheid benodigde zakelijke gegevens om de app te kunnen gebruiken. Houd er rekening mee dat de dierverzorgings-app van Contoso is gebaseerd op een aangepaste entiteit. Als de entiteit is aangepast, moeten de bevoegdheden expliciet worden opgegeven voordat gebruikers met de app kunnen werken. Dit kunt u op een van de volgende manieren doen.
- U kunt een bestaande vooraf gedefinieerde beveiligingsrol uitbreiden, zodat deze de bevoegdheden voor records bevat op basis van de aangepaste entiteit. 
- U kunt een aangepaste beveiligingsrol maken voor het beheren van de bevoegdheden voor de gebruikers van de app. 

Omdat de omgeving waarin de records voor dierverzorging worden bijgehouden tevens wordt gebruikt voor andere, door het bedrijf Contoso uitgevoerde apps, wordt er een aangepaste beveiligingsrol gemaakt die specifiek is voor de dierverzorgings-app. Daarnaast zijn er twee sets toegangsbevoegdheden vereist.
- Dierverzorgers hoeven alleen records te lezen, bij te werken en te koppelen met andere records. Zij krijgen dus een beveiligingsrol met bevoegdheden voor lezen, schrijven en toevoegen. 
- Dierverzorgingsplanners hebben alle bevoegdheden nodig die dierverzorgers ook hebben, plus de mogelijkheid voor maken, toevoegen, verwijderen en delen. Aan hun beveiligingsrol moeten dus bevoegdheden worden toegevoegd voor maken, lezen, schrijven, toevoegen, verwijderen, toewijzen, toevoegen aan en delen.

Zie [Beveiligingsrollen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles) voor meer informatie over bevoegdheden voor toegang en bereik.

## <a name="create-a-custom-security-role"></a>Een aangepaste beveiligingsrol maken
1. Selecteer op de site [!INCLUDE [powerapps](../../includes/powerapps.md)] de optie **Modelgestuurd** > **Apps** > **...** > **Koppeling delen**.
2. Selecteer in het dialoogvenster **Deze app delen** onder **Een beveiligingsrol maken** de optie **Beveiligingsinstelling**.
3. Selecteer op de pagina **Instellingen** de optie **Nieuw**.  

4. U kunt in de ontwerper voor beveiligingsrollen de acties (zoals lezen, schrijven of verwijderen) en het bereik voor deze acties selecteren. Met het bereik bepaalt u hoe diep of hoog binnen de hiërarchie van omgevingen de gebruiker een bepaalde actie kan uitvoeren. Geef in het vak **Rolnaam** de optie *Dierverzorgers* op.
5. Selecteer het tabblad **Aangepaste entiteiten** en zoek vervolgens de gewenste aangepaste entiteit op. Voor dit voorbeeld wordt de aangepaste entiteit met de naam **Huisdier** gebruikt. 
6. Op de rij **Huisdier** selecteert u elk van de volgende bevoegdheden vier keer tot het globale bereik voor de organisatie, ![Organization global scope](media/share-model-driven-app/organizational-scope-privilege.png), is geselecteerd: **Lezen, Schrijven, Toevoegen**
![Nieuwe beveiligingsrol](media/share-model-driven-app/custom-security-role.png)
7. Aangezien de dierverzorgings-app tevens betrekking heeft met de accountentiteit, selecteert u het tabblad **Kernrecords** en selecteert u op de rij **Account** de optie **Lezen** vier keer tot het globale bereik voor de organisatie, ![Organization global scope](media/share-model-driven-app/organizational-scope-privilege.png), is geselecteerd. 
8. Selecteer **Opslaan en sluiten**. 
9. Geef bij de ontwerper van de beveiligingsrol in het vak **Rolnaam** *Dierverzorgingsplanners*  op. 
10. Selecteer het tabblad **Aangepaste entiteiten** en zoek vervolgens de entiteit **Huisdier** op. 
11. Selecteer in de rij **Huisdier** elk van de volgende bevoegdheden vier keer tot het globale bereik voor de organisatie, ![Organization global scope](media/share-model-driven-app/organizational-scope-privilege.png), is geselecteerd: **Maken, Lezen, Schrijven, Verwijderen, Toevoegen, Toevoegen aan, Toewijzen, Delen**
12. Aangezien de dierverzorgings-app tevens betrekking heeft op de accountentiteit en planners accountrecords moeten kunnen maken en wijzigen, selecteert u het tabblad **Kernrecords** en selecteert u op de rij **Account** elk van de volgende bevoegdheden vier keer tot het globale bereik voor de organisatie, ![Organization global scope](media/share-model-driven-app/organizational-scope-privilege.png), is geselecteerd. 
    **Maken, Lezen, Schrijven, Verwijderen, Toevoegen, Toevoegen aan, Toewijzen, Delen**
13. Selecteer **Opslaan en sluiten**.

## <a name="assign-security-roles-to-users"></a>Beveiligingsrollen aan gebruikers toewijzen
Met beveiligingsrollen kunt u de toegang van een gebruiker tot gegevens beheren met een set met toegangsniveaus en -machtigingen. De gecombineerde toegangsniveaus en -machtigingen die zijn opgenomen in een bepaalde beveiligingsrol, zorgen ervoor dat er limieten gelden voor de weergave van gegevens van de gebruiker en de interactie van de gebruiker met deze gegevens.

### <a name="assign-a-security-role-to-pet-grooming-technicians"></a>Een beveiligingsrol toewijzen aan dierverzorgers
1. Selecteer in het dialoogvenster **Deze app delen** onder **Gebruikers toewijzen aan de beveiligingsrol** **Beveiligingsgebruikers**.
2. Selecteer de dierverzorgers in de lijst die wordt weergegeven.
3. Selecteer **Rollen beheren**.

    ![Rollen beheren](media/share-model-driven-app/select-users-for-security-roles.png)

4. Selecteer in het dialoogvenster **Gebruikersrollen beheren** de beveiligingsrol **Dierverzorgers** die u eerder hebt gemaakt en selecteer vervolgens **OK**.

### <a name="assign-a-security-role-to-pet-grooming-schedulers"></a>Een beveiligingsrol toewijzen aan dierverzorgingsplanners
1. Selecteer in het dialoogvenster **Deze app delen** onder **Gebruikers toewijzen aan een beveiligingsrol** **Beveiligingsgebruikers**.
2. Selecteer de dierverzorgingsplanners in de lijst die wordt weergegeven.
3. Selecteer **Rollen beheren**.
4. Selecteer in het dialoogvenster **Gebruikersrollen beheren** de beveiligingsrol **Dierverzorgingsplanners** die u eerder hebt gemaakt, en selecteer vervolgens **OK**.


## <a name="add-security-roles-to-the-app"></a>Beveiligingsrollen toevoegen aan de app
Vervolgens moeten een of meer beveiligingsrollen worden toegewezen aan de app. Gebruikers hebben toegang tot de apps op basis van de beveiligingsrollen waaraan ze zijn toegewezen.
1. Selecteer in het dialoogvenster **Deze app delen** onder **De beveiligingsrol toevoegen aan uw app** **Mijn apps**.
2. Selecteer in de rechterbenedenhoek van de app-tegel van de dierverzorgings-app van Contoso **Meer opties (...)** , en selecteer vervolgens **Rollen beheren**.

    ![Rollen beheren voor de app](media/share-model-driven-app/manage-roles.png)

4. U kunt in de sectie **Rollen** kiezen of u alle beveiligingsrollen of geselecteerde functies toegang tot de app wilt verlenen. Selecteer de rollen **Dierverzorgingsplanners** en **Dierverzorgers** die u eerder hebt gemaakt.

    ![Selecteer Beveiligingsrollen voor de app](media/share-model-driven-app/app-security-roles.png)

5. Selecteer **Opslaan**.
 
## <a name="share-the-link-to-your-app"></a>Deel de koppeling naar uw app
1. Kopieer vanuit het dialoogvenster **Deze app delen** onder **De koppeling naar uw app rechtstreeks delen met gebruikers** de URL die wordt weergegeven.
 
2. Selecteer **Sluiten**.
3. Plak de URL van de app op een locatie waar uw gebruikers toegang ertoe hebben. U kunt deze bijvoorbeeld op een SharePoint-site plaatsen of via e-mail verzenden.

![De koppeling delen](media/share-model-driven-app/share-model-driven-URL.PNG)

De URL van de app bevindt zich op het tabblad **Eigenschappen** in de appontwerper. 
    
![App-URL kopiëren](media/share-model-driven-app/app-designer-copy-web-url.png)

## <a name="about-predefined-security-roles"></a>Informatie over vooraf gedefinieerde beveiligingsrollen
Deze vooraf gedefinieerde rollen zijn beschikbaar met een [!INCLUDE [powerapps](../../includes/powerapps.md)]-omgeving.


|Beveiligingsrol  |*Bevoegdheden  |Beschrijving |
|---------|---------|---------|
|Omgevingsmaker     |  Geen       | Hiermee kunt u met Microsoft Flow nieuwe aan een omgeving gekoppelde resources maken, waaronder apps, verbindingen, aangepaste API's, gateways en stromen. Hiermee hebt u echter geen toegang tot gegevens in een omgeving. Zie [Overzicht van omgevingen](https://powerapps.microsoft.com/blog/powerapps-environments/) voor meer informatie        |
|Systeembeheerder     |  Maken, Lezen, Schrijven, Verwijderen, Aanpassingen, Beveiligingsrollen       | Personen met deze rol hebben volledige machtiging voor het aanpassen of beheren van de omgeving, inclusief het maken, wijzigen en toewijzen van beveiligingsrollen. Hiermee kunt u alle gegevens in de omgeving weergeven. Zie [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization) voor meer informatie        |
|Systeemaanpasser     | Maken (zelf), Lezen (zelf), Schrijven (zelf), Verwijderen (zelf), Aanpassingen         | Hiermee hebt u volledige machtiging voor het aanpassen van de omgeving. De systeemaanpasser kan echter alleen records weergeven voor de omgevingsentiteiten die de aanpasser maakt. Zie [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization) voor meer informatie        |
|Common Data Service-gebruiker     |  Lezen, Maken (zelf), Schrijven (zelf), Verwijderen (zelf)       | Hiermee kunnen gebruikers een app in de omgeving uitvoeren en veelvoorkomende taken uitvoeren voor de records waarvan ze eigenaar zijn.        |
|Delegeren     | Handelen namens een andere gebruiker        | Hiermee kunt u code uitvoeren als een andere gebruiker of door een andere gebruiker te imiteren.  Deze rol wordt doorgaans gebruikt met een andere beveiligingsrol zodat toegang tot records kan worden verkregen. Zie [Een andere gebruiker imiteren](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user) voor meer informatie        |

* Deze bevoegdheid heeft een globaal bereik, tenzij anders aangegeven.

## <a name="next-steps"></a>Volgende stappen
[Snelstartgids: Een modelgestuurde app uitvoeren op een mobiel apparaat](../../user/run-app-client-model-driven.md)



