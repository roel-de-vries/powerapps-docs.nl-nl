---
title: Zelfstudie voor het delen van een modelgestuurde app met PowerApps | Microsoft Docs
description: In deze zelfstudie leert u hoe u een modelgestuurde app deelt
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-share-a-model-driven-app-with-powerapps"></a>Zelfstudie: Een modelgestuurde app delen met PowerApps

[!INCLUDE [powerapps](../../includes/powerapps.md)]-apps gebruiken op rollen gebaseerde beveiliging voor delen. Het fundamentele concept van op rollen gebaseerde beveiliging is dat een beveiligingsrol bevoegdheden bevat die een set acties definiëren die kunnen worden uitgevoerd in de app. Alle appgebruikers moeten aan een of meer van de vooraf gedefinieerde of aangepaste rollen worden toegewezen. Rollen kunnen ook worden toegewezen aan teams. Wanneer een gebruiker of een team aan een van deze rollen wordt toegewezen, worden aan die persoon of teamleden de bevoegdheden verleend die bij die rol horen. 

In deze zelfstudie voert u de taken voor het delen van een modelgestuurde app uit zodat anderen deze kunnen gebruiken. U leert het volgende:
- Een aangepaste beveiligingsrol maken
- Gebruikers toewijzen aan de aangepaste beveiligingsrol
- De beveiligingsrol aan een app toewijzen

## <a name="prerequisites"></a>Vereisten
Voor het delen van een app moet u over de [!INCLUDE [powerapps](../../includes/powerapps.md)]-rol Omgevingsbeheerder of Systeembeheerder beschikken. 

## <a name="sign-in-to-powerapps"></a>Aanmelden bij PowerApps
Meld u aan bij [PowerApps](https://powerapps.microsoft.com/). Als u nog geen [!INCLUDE [powerapps](../../includes/powerapps.md)]-account hebt, selecteert u de koppeling **Gratis aan de slag**.

## <a name="share-an-app"></a>Een app delen 
In de zelfstudie wordt het bedrijf Contoso gevolgd, een bedrijf dat handelt in producten voor de cosmetische verzorging van honden en katten. Een app met een aangepaste entiteit voor het bijhouden van het cosmetische verzorgingsbedrijf voor huisdieren is al gemaakt en gepubliceerd. De app moet nu worden gedeeld, zodat de medewerkers van het cosmetische dierverzorgingsbedrijf deze kunnen gebruiken. Als de app moet worden gedeeld, moet een beheerder of de maker van de app een of meer beveiligingsrollen toewijzen aan gebruikers en aan de app. 

## <a name="create-or-configure-a-security-role"></a>Een beveiligingsrol maken of configureren
De [!INCLUDE [powerapps](../../includes/powerapps.md)]-omgeving bevat [vooraf gedefinieerde rollen](#about-predefined-security-roles) die overeenkomen met algemene gebruikerstaken. Voor deze beveiligingsrollen zijn toegangsniveaus gedefinieerd waarmee toegang wordt geboden tot de minimale hoeveelheid benodigde zakelijke gegevens om de app te kunnen gebruiken. Houd er rekening mee dat de app voor dierverzorging van Contoso is gebaseerd op een aangepaste entiteit. Als de entiteit is aangepast, moeten de bevoegdheden expliciet worden opgegeven voordat gebruikers met de app kunnen werken. Dit kunt u op een van de volgende manieren doen.
- U kunt een bestaande vooraf gedefinieerde beveiligingsrol uitbreiden, zodat deze de bevoegdheden voor records bevat op basis van de aangepaste entiteit. 
- U kunt een aangepaste beveiligingsrol maken voor het beheren van de bevoegdheden voor de gebruikers van de app. 

Omdat de omgeving waarin de records voor dierverzorging worden bijgehouden tevens wordt gebruikt voor andere, door het bedrijf Contoso uitgevoerde apps, wordt er een specifieke aangepaste beveiligingsrol voor de app voor dierverzorging gemaakt. Daarnaast zijn twee verschillende sets toegangsbevoegdheden vereist.
- Dierverzorgers hoeven alleen records te lezen, bij te werken en te koppelen aan andere records. Zij krijgen dus een beveiligingsrol met bevoegdheden voor lezen, schrijven en toevoegen. 
- Dierverzorgingsplanners hebben alle bevoegdheden nodig die dierverzorgers ook hebben, plus de mogelijkheid om te maken, toe te voegen, te verwijderen en te delen. Aan hun beveiligingsrol moeten dus bevoegdheden worden toegevoegd voor maken, lezen, schrijven, toevoegen, verwijderen, toewijzen, toevoegen aan en delen.

Zie [Beveiligingsrollen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles) voor meer informatie over bevoegdheden voor toegang en bereik.

## <a name="create-a-custom-security-role"></a>Een aangepaste beveiligingsrol maken
1. Selecteer op de site [!INCLUDE [powerapps](../../includes/powerapps.md)] de optie **Modelgestuurd** > **Apps** > **…**> **Koppeling delen**.
2. Selecteer in het dialoogvenster **Deze app delen** onder **Een beveiligingsrol maken** de optie **Beveiligingsinstelling**.
3. Selecteer op de pagina **Instellingen** de optie **Nieuw**.  

4. U kunt in de ontwerper voor beveiligingsrollen de acties (zoals lezen, schrijven of verwijderen) en het bereik voor deze acties selecteren. Met het bereik bepaalt u hoe diep of hoog binnen de hiërarchie van omgevingen de gebruiker een bepaalde actie kan uitvoeren. Geef in het vak **Rolnaam** de tekst *Dierverzorgers* op.
5. Selecteer het tabblad **Aangepaste entiteiten** en zoek de gewenste aangepaste entiteit. Voor dit voorbeeld wordt de aangepaste entiteit **Huisdier** gebruikt. 
6. Op de rij **Huisdier** selecteert u elk van de volgende bevoegdheden vier keer tot het globale bereik voor de organisatie ![Globale bereik organisatie](media/share-model-driven-app/organizational-scope-privilege.png) is geselecteerd: **Lezen, Schrijven, Toevoegen**
> [!div class="mx-imgBorder"] 
> ![Nieuwe beveiligingsrol](media/share-model-driven-app/custom-security-role.png)
7. Aangezien de app voor dierverzorging tevens gerelateerd is aan de accountentiteit, selecteert u het tabblad **Kernrecords** en selecteert u op de rij **Account** de optie **Lezen** vier keer tot het globale bereik voor de organisatie ![Globale bereik organisatie](media/share-model-driven-app/organizational-scope-privilege.png) is geselecteerd. 
8. Kies **Opslaan en sluiten**. 
9. Geef in de ontwerper voor beveiligingsrollen in het vak **Rolnaam** de tekst *Dierverzorgingsplanners* op. 
10. Selecteer het tabblad **Aangepaste entiteiten** en zoek de gewenste entiteit **Huisdier**. 
11. Op de rij **Huisdier** selecteert u elk van de volgende bevoegdheden vier keer tot het globale bereik voor de organisatie ![Globale bereik organisatie](media/share-model-driven-app/organizational-scope-privilege.png) is geselecteerd: **Maken, Lezen, Schrijven, Verwijderen, Toevoegen, Toevoegen aan, Toewijzen, Delen**
12. Aangezien de app voor dierverzorging tevens gerelateerd is aan de accountentiteit en planners accountrecords moeten kunnen maken en wijzigen, selecteert u het tabblad **Kernrecords** en selecteert u op de rij **Account** elk van de volgende bevoegdheden vier keer tot het globale bereik voor de organisatie ![Globale bereik organisatie](media/share-model-driven-app/organizational-scope-privilege.png) is geselecteerd. 
    **Maken, Lezen, Schrijven, Verwijderen, Toevoegen, Toevoegen aan, Toewijzen, Delen**
13. Kies **Opslaan en sluiten**.

## <a name="assign-security-roles-to-users"></a>Beveiligingsrollen toewijzen aan gebruikers
Beveiligingsrollen bepalen de toegang van een gebruiker tot gegevens middels een reeks toegangsniveaus en bevoegdheden. De combinatie van toegangsniveaus en machtigingen van een specifieke beveiligingsrol bepaalt limieten op de weergave van gegevens voor de gebruiker en op de interacties van de gebruiker met die gegevens.

### <a name="assign-a-security-role-to-pet-grooming-technicians"></a>Een beveiligingsrol toewijzen aan dierverzorgers
1. Selecteer in het dialoogvenster **Deze app delen** onder **Gebruikers toewijzen aan de beveiligingsrol** de optie **Beveiligingsgebruikers**.
2. Selecteer de dierverzorgers in de lijst die wordt weergegeven.
3. Selecteer **Rollen beheren**.

    > [!div class="mx-imgBorder"] 
    > ![Rollen beheren](media/share-model-driven-app/select-users-for-security-roles.png)

4. Selecteer in het dialoogvenster **Gebruikersrollen beheren** de beveiligingsrol **Dierverzorgers** die u eerder hebt gemaakt en selecteer vervolgens **OK**.

### <a name="assign-a-security-role-to-pet-grooming-schedulers"></a>Een beveiligingsrol toewijzen aan dierverzorgingsplanners
1. Selecteer in het dialoogvenster **Deze app delen** onder **Gebruikers toewijzen aan de beveiligingsrol** de optie **Beveiligingsgebruikers**.
2. Selecteer de dierverzorgingsplanners in de lijst die wordt weergegeven.
3. Selecteer **Rollen beheren**.
4. Selecteer in het dialoogvenster **Gebruikersrollen beheren** de beveiligingsrol **Dierverzorgingsplanners** die u eerder hebt gemaakt en selecteer vervolgens **OK**.


## <a name="add-security-roles-to-the-app"></a>Beveiligingsrollen toevoegen aan de app
Vervolgens moeten een of meer beveiligingsrollen worden toegewezen aan de app. Gebruikers hebben op basis van hun toegewezen beveiligingsrollen toegang tot apps.
1. Selecteer in het dialoogvenster **Deze app delen** onder **De beveiligingsrol toevoegen aan uw app** de optie **Mijn apps**.
2. Selecteer in de rechterbenedenhoek van de apptegel van de app voor dierverzorging van Contoso de knop **Meer opties (...)** en selecteer vervolgens **Rollen beheren**.

    ![Rollen beheren voor de app](media/share-model-driven-app/manage-roles.png)

4. In de sectie **Rollen** kunt u opgeven of u apptoegang aan alle beveiligingsrollen of geselecteerde rollen wilt geven. Selecteer de rollen **Dierverzorgingsplanners** en **Dierverzorgers** die u eerder hebt gemaakt.

    > [!div class="mx-imgBorder"] 
    > ![Beveiligingsrollen selecteren voor de app](media/share-model-driven-app/app-security-roles.png)

5. Selecteer **Opslaan**.
 
## <a name="share-the-link-to-your-app"></a>De koppeling delen met uw app
1. Kopieer de URL die in het dialoogvenster **Deze app delen** wordt weergegeven onder **De koppeling naar uw app rechtstreeks delen met gebruikers**.
 
2. Selecteer **Sluiten**.
3. Plak de URL van de app op een locatie waar uw gebruikers toegang ertoe hebben. U kunt deze bijvoorbeeld op een SharePoint-site plaatsen of via e-mail verzenden.

> [!div class="mx-imgBorder"] 
> ![De koppeling delen](media/share-model-driven-app/share-model-driven-URL.PNG)

U kunt de URL van de app ook vinden op het tabblad **Eigenschappen** in de appontwerper. 

> [!div class="mx-imgBorder"] 
> ![URL voor app kopiëren](media/share-model-driven-app/app-designer-copy-web-url.png)

## <a name="about-predefined-security-roles"></a>Vooraf gedefinieerde beveiligingsrollen
Deze vooraf gedefinieerde rollen zijn beschikbaar met een [!INCLUDE [powerapps](../../includes/powerapps.md)]-omgeving.


|Beveiligingsrol  |*Bevoegdheden  |Beschrijving |
|---------|---------|---------|
|Omgevingsmaker     |  Geen       | Hiermee kunt u met Microsoft Flow nieuwe aan een omgeving gekoppelde resources maken, waaronder apps, verbindingen, aangepaste API's, gateways en stromen. Hiermee hebt u echter geen toegang tot gegevens in een omgeving. Meer informatie: [Overzicht van omgevingen](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|systeembeheerder     |  Maken, Lezen, Schrijven, Verwijderen, Aanpassingen, Beveiligingsrollen       | Personen met deze rol zijn volledig gemachtigd om de omgeving te beheren, inclusief het maken, wijzigen en toewijzen van beveiligingsrollen. Hiermee kunt u alle gegevens in de omgeving weergeven. Meer informatie: [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|systeemaanpasser     | Maken (zelf), Lezen (zelf), Schrijven (zelf), Verwijderen (zelf), Aanpassingen         | Hiermee hebt u volledige machtigingen voor het aanpassen van de omgeving. De systeemaanpasser kan echter alleen records weergeven voor de omgevingsentiteiten die de aanpasser maakt. Meer informatie: [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Common Data Service-gebruiker     |  Lezen, Maken (zelf), Schrijven (zelf), Verwijderen (zelf)       | Hiermee kunnen gebruikers een app in de omgeving uitvoeren en veelvoorkomende taken uitvoeren voor de records waarvan ze eigenaar zijn.        |
|Gemachtigde     | Handelen namens een andere gebruiker        | Hiermee kunt u code uitvoeren als een andere gebruiker of door een andere gebruiker te imiteren.  Deze rol wordt doorgaans gebruikt met een andere beveiligingsrol zodat toegang tot records kan worden verkregen. Meer informatie: [Een andere gebruiker imiteren](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*Deze bevoegdheid heeft een globaal bereik, tenzij anders aangegeven.

## <a name="next-steps"></a>Volgende stappen
[Een modelgestuurde app uitvoeren op een mobiel apparaat](../../user/run-app-client-model-driven.md)



