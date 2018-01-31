---
title: Een stroom maken om projectgoedkeuringen te beheren | Microsoft Docs
description: In deze taak maken we een stroom die het goedkeuringsproces voor projecten aanstuurt.
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/09/18
ms.author: mblythe
ms.openlocfilehash: 4af1571bb72c713c6186f5237d6b3791eb95808b
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="create-a-flow-to-manage-project-approvals"></a>Een stroom maken om projectgoedkeuringen te beheren
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

In deze taak maken we een stroom die het goedkeuringsproces voor projecten aanstuurt. Microsoft Flow is geïntegreerd met SharePoint. U kunt dus makkelijk rechtstreeks vanuit een lijst een stroom maken. De stroom die we maken wordt geactiveerd als een item wordt toegevoegd aan de lijst **Projectaanvragen**. De stroom verzendt een e-mailbericht naar de fiatteur van het project, die de aanvraag rechtstreeks via e-mail goedkeurt of afkeurt. Vervolgens verzendt de stroom een e-mail met een goedkeuring of afkeuring naar de projectaanvrager en werkt de SharePoint-lijsten dienovereenkomstig bij.

## <a name="step-1-configure-the-flow-template"></a>Stap 1: Stroomsjabloon configureren
1. Klik of tik in de lijst **Projectaanvragen** op **Stroom** en vervolgens op **Stroom maken**.
   
    ![Een stroom maken](./media/sharepoint-scenario-approval-flow/03-01-01-create-flow.png)
2. Klik of tik in het rechterdeelvenster op **Goedkeuring starten wanneer een nieuw item is toegevoegd**.
   
    ![Een goedkeuringsstroom maken](./media/sharepoint-scenario-approval-flow/03-01-02-approval-flow.png)
3. Als u nog niet bent aangemeld, meldt u zich aan bij SharePoint en Outlook en klikt of tikt u op **Doorgaan**.
   
    ![Aanmelden om sjabloon te gebruiken](./media/sharepoint-scenario-approval-flow/03-01-03-continue.png)
   
    U ziet nu de sjabloon voor deze stroom, die u nu kunt voltooien. De vakken in de stroom stellen stappen voor. Hierin komt de invoer uit vorige stappen terecht, evenals de door u opgegeven invoer. Elke stap kan vervolgens uitvoer voor de volgende stappen leveren.
   
    ![Goedkeuringssjabloon](./media/sharepoint-scenario-approval-flow/03-01-04-template.png)
4. Voer in het vak **Toegewezen aan** een naam in die geldig is in uw tenant.
   
    ![Contactpersoon voor goedkeurings-e-mail](./media/sharepoint-scenario-approval-flow/03-01-05-approval-email.png)
   
    Het volgende vak in de stroom reageert op de beslissing van de projectfiatteur en leidt de stroom om naar een van de twee *vertakkingen*: **Indien ja** of **Indien nee**.
   
    ![Voorwaarde voor goedkeuring](./media/sharepoint-scenario-approval-flow/03-01-06-condition.png)

## <a name="step-2-create-actions-for-approve--yes"></a>Stap 2: Acties maken voor goedkeuring = ja
De standaardinstelling is dat met deze vertakking per e-mail wordt gemeld dat de aanvraag is goedgekeurd. Daarnaast wordt de lijst **Projectaanvragen** bijgewerkt en wordt er een item toegevoegd aan de lijst **Projectgegevens** omdat het project is goedgekeurd.

1. Klik of tik in de vertakking **Indien ja** op **Maker van item informeren over goedkeuring** en klik vervolgens op **Bewerken** om de standaardopties te zien voor het e-mailbericht dat wordt verzonden naar de aanvrager.
   
    ![E-mailinstellingen bewerken](./media/sharepoint-scenario-approval-flow/03-01-07-yes-email.png)
2. Standaard wordt aan de persoon die het lijstitem heeft gemaakt, een e-mail verzonden met de onderwerpregel en de hoofdtekst die u hier ziet. U kunt deze desgewenst bijwerken.
   
    ![Standaard-e-mailinstellingen](./media/sharepoint-scenario-approval-flow/03-01-07a-yes-email-defaults.png)
3. Klik of tik op **Een actie toevoegen**.
   
    ![Een actie toevoegen](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
4. Zoek onder **Kies een actie** op 'SharePoint' en klik of tik op **SharePoint: item bijwerken**.
   
    ![Actie Item bijwerken](./media/sharepoint-scenario-approval-flow/03-00-02-update.png)
5. Voer de URL van de SharePoint-site en de lijstnaam in.
   
    ![Itemparameters bijwerken](./media/sharepoint-scenario-approval-flow/03-00-03-update-list.png)
6. Selecteer het vak **Id** en klik of tik in het dialoogvenster voor *dynamische inhoud* op **Id**.
   
    ![Dynamische inhoud van lijst-id](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
   
    Dynamische inhoud is op basis van de vorige stappen beschikbaar in de hele stroom. In dit geval zijn de SharePoint-lijstgegevens beschikbaar, die we kunnen gebruiken in de acties die we maken.
7. Selecteer het vak **Titel**, zoek in het dialoogvenster voor dynamische inhoud op 'Titel' en klik of tik op **Titel**.
   
    ![Dynamische inhoud van lijsttitel](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
8. Voer 'Ja' in in het vak **Goedgekeurd**. Dit deel van de stroom moet er nu uitzien als in de volgende afbeelding.
   
    ![Update van lijst](./media/sharepoint-scenario-approval-flow/03-01-08-yes-update-complete.png)
9. Klik of tik opnieuw op **Een actie toevoegen**. Deze keer voegen we een item toe aan de lijst **Projectdetails** voor het goedgekeurde project.
   
    ![Een actie toevoegen](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
10. Zoek onder **Kies een actie** op 'SharePoint' en selecteer **SharePoint: item maken**.
    
    ![Actie Item maken](./media/sharepoint-scenario-approval-flow/03-01-09-create.png)
11. Voer de URL van de SharePoint-site en de lijstnaam in.
    
    ![Itemparameters maken](./media/sharepoint-scenario-approval-flow/03-01-10-yes-create-list.png)
12. Selecteer het vak **Titel**, zoek in het dialoogvenster voor dynamische inhoud op 'Titel' en klik of tik op **Titel**.
    
    ![Dynamische inhoud van lijsttitel](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
13. Selecteer het vak **RequestId** en klik of tik in het dialoogvenster voor dynamische inhoud op **Id**.
    
    ![Dynamische inhoud van lijst-id](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
14. Voer 'Niet-toegewezen' in in het vak **PMAssigned**. Dit deel van de stroom moet er nu uitzien als in de volgende afbeelding.
    
    ![Item maken voltooid](./media/sharepoint-scenario-approval-flow/03-01-11-yes-create-complete.png)

## <a name="step-3-review-action-for-approve--no"></a>Stap 3: Controleer actie voor goedkeuren = nee
De standaardinstelling is dat met deze vertakking per e-mail wordt gemeld dat de aanvraag is geweigerd. De lijst **Projectaanvragen** wordt ook bijgewerkt. We voegen geen item toe aan de lijst **Projectdetails** omdat er nog niets gebeurd met het project.

1. Klik of tik in de vertakking **Indien nee** op **Maker van item informeren over afwijzing** en klik vervolgens op **Bewerken** om de standaardopties te zien voor het e-mailbericht dat wordt verzonden naar de aanvrager.
   
    ![E-mailinstellingen bewerken](./media/sharepoint-scenario-approval-flow/03-01-12-no-email.png)
2. Standaard wordt aan de persoon die het lijstitem heeft gemaakt, een e-mail verzonden met de onderwerpregel en de hoofdtekst die u hier ziet. U kunt deze desgewenst bijwerken.
   
    ![Standaard-e-mailinstellingen](./media/sharepoint-scenario-approval-flow/03-01-13-no-email-defaults.png)
3. Klik of tik op **Een actie toevoegen**.
   
    ![Een actie toevoegen](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
4. Zoek onder **Kies een actie** op 'SharePoint' en klik of tik op **SharePoint: item bijwerken**.
   
    ![Actie Item bijwerken](./media/sharepoint-scenario-approval-flow/03-00-02-update.png)
5. Voer de URL van de SharePoint-site en de lijstnaam in.
   
    ![Itemparameters bijwerken](./media/sharepoint-scenario-approval-flow/03-00-03-update-list.png)
6. Selecteer het vak **Id** en klik of tik in het dialoogvenster voor dynamische inhoud op **Id**.
   
    ![Dynamische inhoud van lijst-id](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
7. Selecteer het vak **Titel**, zoek in het dialoogvenster voor dynamische inhoud op 'Titel' en klik of tik op **Titel**.
   
    ![Dynamische inhoud van lijsttitel](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
8. Voer 'Nee' in in het vak **Goedgekeurd**. Dit deel van de stroom moet er nu uitzien als in de volgende afbeelding.
   
    ![Update van lijst](./media/sharepoint-scenario-approval-flow/03-01-08-no-update-complete.png)
9. Klik of tik rechtsboven in het scherm op **Stroom maken**.
   
    De stroom is nu klaar en moet, als u de vakken samenvouwt, eruitzien als in de volgende afbeelding.
   
    ![Voltooide stroom](./media/sharepoint-scenario-approval-flow/03-01-16-flow-complete.png)

10. Klik of tik rechtsboven in het scherm op **Gereed**.
   
    ![Knop Gereed](./media/sharepoint-scenario-approval-flow/03-01-15a-done-button.png)

## <a name="step-4-run-the-approval-flow"></a>Stap 4: Goedkeuringsstroom uitvoeren
1. Klik in de lijst **Projectaanvragen** op **Snel bewerken** en voeg een item toe, bijvoorbeeld:
   
   * **Title** = "Nieuw monitor voor Ilene"

   * **Description** = "Ilene heeft een 24-inch monitor nodig"

   * **ProjectType** = "Nieuwe hardware"

   * **RequestDate** = "03-02-2017"

   * **Requestor** = "Ilene de Crom"

   * **EstimatedDays** = "1"

   * **Approved** = "In wachtrij"

     ![Item aan lijst toegevoegd](./media/sharepoint-scenario-approval-flow/03-02-01-list-add.png)
2. Klik bovenaan de pagina op **Gereed** als u klaar bent.
   
    ![Vinkje Gereed](./media/sharepoint-scenario-approval-flow/03-02-02-done.png)
3. Controleer het postvak van het e-mailaccount van de fiatteur. Als het goed is, hebt u een e-mail ontvangen, zoals de volgende.
   
    ![E-mail aan Arnaud Schoonen](./media/sharepoint-scenario-approval-flow/03-02-03-allan-email.png)
4. Nadat u op **Goedkeuren** of **Weigeren** hebt geklikt, wordt door de stroom een ander proces uitgevoerd en krijgt u rechtstreeks feedback via e-mail, zoals hieronder weergegeven.
   
    ![Goedkeuringsactie voltooid](./media/sharepoint-scenario-approval-flow/03-02-04-action-complete.png)
5. De stroom verzendt een e-mail met het antwoord van Arnaud aan Ilene, zoals in de volgende afbeelding. Deze e-mail is afkomstig *van* Ilene omdat zij eigenaar is van de stroom.
   
    ![E-mail aan Ilene de Crom](./media/sharepoint-scenario-approval-flow/03-02-05-megan-email.png)

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies bestaat uit het [maken van een app voor het beheren van projecten](sharepoint-scenario-build-app.md).

