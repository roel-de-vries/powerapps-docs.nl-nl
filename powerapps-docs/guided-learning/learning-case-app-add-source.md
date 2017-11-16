---
title: Een gegevensbron en stroom toevoegen (Common Data Service) | Microsoft Docs
description: Aanvullende gegevens importeren en een stroom vanuit de app activeren
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: Y057qUJ2NNk
courseduration: 11m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: 42f0d43984c88dc9a5e6ffe67ca3b7ff6cedf8b7
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="add-a-data-source-and-flow-common-data-service"></a>Een gegevensbron en stroom toevoegen (Common Data Service)
In deze sectie hebben we tot nu toe een app gegenereerd op basis van de entiteit Case uit de Common Data Service, de app verkend om te zien hoe deze wordt samengesteld en hebben we de app op verschillende manieren aangepast. In het laatste onderwerp van deze sectie brengen we nog een standaardentiteit in en gebruiken we Microsoft Flow om een e-mail te verzenden. De app activeert een stroom zodat de persoon die een case heeft geopend op de hoogte wordt gesteld wanneer de case wordt bijgewerkt. We voeren in dit onderwerp een bepaald scenario uit, maar de vaardigheden die u hier leert kunnen op allerlei apps worden toegepast. Laten we beginnen met de entiteiten.

## <a name="review-entity-relationships"></a>Entiteitrelaties bekijken
Zo meteen voegen we de entiteit Contact toe, maar eerst bekijken we hoe de entiteiten Case en Contact met elkaar in verband staan. In de entiteit Case ziet u dat een van de velden **CurrentContact** is, met het gegevenstype **Lookup**. Dit betekent dat dit veld wordt gebruikt in een relatie met een andere tabel.

![Velden van entiteit Case](./media/learning-case-app-add-source/case-fields.png)

Op het tabblad **Relationships** kunt u zien dat **Contact** de gerelateerde entiteit is. Houd dat in gedachten omdat we deze relatie verderop in dit onderwerp gaan gebruiken.

![Relaties van entiteit Case](./media/learning-case-app-add-source/case-relationships.png)

## <a name="add-an-entity-to-the-app"></a>Een entiteit toevoegen aan de app
Het toevoegen van een gegevensbron in PowerApps is eenvoudig. Klik of tik in het rechterdeelvenster op **Data sources** en vervolgens op **Add data source**. Kies in dit geval de verbinding **Common Data Service** en selecteer de entiteit **Contact**. Nadat u op **Connect** hebt geklikt of getikt, wordt de entiteit toegevoegd aan de app. 

![Entiteit Contact toevoegen](./media/learning-case-app-add-source/contact-entity.png)

In dit voorbeeld voegen we gegevens uit een andere entiteit toe, maar u kunt ook gegevens uit veel andere bronnen in uw apps opnemen. 

## <a name="look-up-contact-information"></a>Contactgegevens opzoeken
Nu we in onze app toegang tot gegevens van de entiteit Contact hebben, is het tijd om de app te gaan gebruiken. Zoals vermeld in de inleiding, willen we een e-mailbericht verzenden wanneer er een case wordt bijgewerkt. We gaan daarvoor twee formules en een stroom gebruiken. De eerste formule is bestemd voor het scherm voor bewerken, om precies te zijn voor de eigenschap OnSelect van de knop voor opslaan.

![Scherm voor bewerken van app](./media/learning-case-app-add-source/edit-screen.png)

Deze knop maakt standaard gebruik van de formule `SubmitForm(EditForm1)` om de update te verzenden wanneer een gebruiker gegevens in het formulier bewerkt. We gaan de formule bewerken zodat eerst wordt gezocht naar de contactgegevens voor de persoon die de huidige case heeft geopend, waarna die gegevens lokaal in de app worden opgeslagen: 

```UpdateContext({contact:LookUp(Contact, ContactId=BrowseGallery1.Selected.CurrentContact.ContactId)}); SubmitForm(EditForm1)```

Wel wat ingewikkeld, maar James geeft een heldere uitleg over het gebruik van deze formule vanaf 2:04 in de video.

## <a name="trigger-a-flow-from-the-app"></a>Een stroom vanuit de app activeren
Nu we weten wie de contactpersoon voor elke case is, kunnen we die persoon een e-mailbericht sturen. We zouden een e-mailbericht rechtstreeks vanuit de app kunnen verzenden, maar in dit voorbeeld laten we zien hoe u een stroom vanuit de app kunt activeren. Hier ziet u de stroom, en eenvoudiger kan het eigenlijk niet: op basis van een actie in een app een e-mail verzenden. We gaan hier niet verder in op stromen, maar er is een volledige serie van Gestuurd leren gewijd aan Microsoft Flow. 

![Stroom om e-mail te verzenden](./media/learning-case-app-add-source/email-flow.png)

Terug in de app moeten we de stroom aanroepen op basis van een gebeurtenis. We gebruiken de eigenschap OnSuccess van het bewerkingsformulier, waardoor de stroom wordt geactiveerd wanneer de bewerking is gelukt. Klik of tik eerst op het bewerkingsformulier en vervolgens op **Action** > **Flows** op het lint. Selecteer de stroom die u wilt gebruiken. 

![Stroom om e-mail te verzenden](./media/learning-case-app-add-source/add-flow-action.png)

De stroom is nu gekoppeld aan de gebeurtenis OnSuccess van het bewerkingsformulier en we kunnen verwijzen naar de contactpersoon voor het e-mailbericht. De volgende formule roept de stroom aan met het e-mailadres van de persoon die de case heeft geopend, samen met een onderwerpregel en de hoofdtekst van het e-mailbericht. 

```CaseResolvedEmailConfirmation.Run(contact.EmailPrimary, "Your case has been updated", "Check it out")```

Met de formule wordt een gegevensbron toegevoegd aan de app en een stroom geactiveerd die een e-mailbericht verzendt. Als u de video's in deze sectie nog niet hebt bekeken, raden wij u aan dat alsnog te doen. Ze bevatten veel van de details die we in de onderwerpen slechts vluchtig hebben bekeken.

## <a name="wrapping-it-all-up"></a>Ter afsluiting
Hiermee zijn we aan het eind van deze sectie gekomen. We hopen dat u er veel van hebt kunnen opsteken. We begonnen met het genereren van een elementaire app op basis van een entiteit en hebben de app een beetje verkend om te begrijpen hoe deze in elkaar zit. We hebben een groot deel van de tijd besteed aan het aanpassen van de app, we hebben een gegevensbron toegevoegd en gezien hoe een stroom wordt geactiveerd. We hebben in deze sectie een specifieke app voor casebeheer gemaakt, maar de vaardigheden die u hebt geleerd, kunnen voor veel soorten apps worden toegepast. Aan het begin van deze sectie hebben we al gemeld dat als u een complexere app voor casebeheer wilt maken, u zeker gebruik moet maken van de sjabloon die beschikbaar is in PowerApps Studio voor Windows. 

We gaan nu verder met het beheren van apps. In de sectie over beheren ziet u hoe u apps kunt delen en het versiebeleid kunt bepalen. Bovendien hebben we het over omgevingen, die kunnen worden gedefinieerd als containers voor apps, gegevens en andere bronnen. 

