---
title: Overzicht van de SharePoint-verbinding | Microsoft Docs
description: Bekijk de beschikbare functies, antwoorden en voorbeelden voor SharePoint
services: 
suite: powerapps
documentationcenter: 
author: sarafankit
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/12/2017
ms.author: karthikb
ms.openlocfilehash: 7d2ceb0dc033477604f6f679dae972641087d469
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="connect-to-sharepoint-from-powerapps"></a>Verbinding maken met Sharepoint vanuit PowerApps
![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

Maak verbinding met een SharePoint-site om automatisch een app te genereren op basis van een lijst, een volledig nieuwe app te bouwen of een bestaande app bij te werken.

## <a name="known-issues"></a>Bekende problemen
U kunt gegevens uit een aangepaste lijst toevoegen, maar geen bibliotheek. Bovendien worden niet alle typen kolommen ondersteund en ondersteunen niet alle typen kolommen alle typen kaarten.

| Type kolom | Ondersteuning | Standaardkaarten |
| --- | --- | --- |
| Eén tekstregel |Ja |Tekst weergeven |
| Meerdere tekstregels |Ja |Tekst weergeven |
| Keuze |Ja (alleen enkelvoudige waarden) |Zoekopdracht weergeven |
| Getal |Ja |Percentage weergeven<br>Classificatie weergeven<br>Tekst weergeven |
| Valuta |Ja |Percentage weergeven<br>Classificatie weergeven<br>Tekst weergeven |
| Datum en tijd |Ja |Tekst weergeven |
| Opzoeken |Ja (alleen enkelvoudige waarden) |Zoekopdracht weergeven<br>Zoekopdracht bewerken |
| Boolean (Ja/Nee) |Ja |Tekst weergeven<br>Wisselknop weergeven |
| Persoon of groep |Ja (alleen enkelvoudige waarden) |Zoekopdracht weergeven<br>Zoekopdracht bewerken |
| Hyperlink |Ja |URL weergeven<br>Tekst weergeven |
| Afbeelding |Ja (alleen-lezen) |Afbeelding weergeven<br>Tekst weergeven |
| Berekend |Ja (alleen-lezen) | |
| Taakresultaat |Nee | |
| Externe gegevens |Nee | |
| Beheerde metagegevens |Ja (alleen-lezen) | |
| Waardering |Nee | |

Bovendien ondersteunt PowerApps geen kolommen die meerdere waarden of selecties ondersteunen.

* Voor opzoekkolommen moet het selectievakje **Meerdere waarden toestaan** zijn uitgeschakeld.
  
    ![Selectievakje om meerdere waarden toe te staan in een opzoekkolom](./media/connection-sharepoint-online/lookup.png)
* Voor kolommen met beheerde metagegevens moet het selectievakje **Meerdere waarden toestaan** zijn uitgeschakeld.
  
    ![Selectievakje om meerdere waarden toe te staan in een kolom met beheerde metagegevens](./media/connection-sharepoint-online/metadata.png)
* Voor een kolom van het type Persoon of groep moet de optie **Nee** onder **Meerdere selecties toestaan** zijn geselecteerd.
  
    ![Opties om meerdere selecties toe te staan voor een kolom van het type Persoon of groep](./media/connection-sharepoint-online/person-group.png)
* Voor keuzekolommen moet de optie **Vervolgkeuzelijst** of **Keuzerondjes** onder **Keuzen weergeven met** zijn geselecteerd.
  
    ![Opties om keuzes weer te geven voor een keuzekolom](./media/connection-sharepoint-online/choice.png)

Kolommen die spaties bevatten, kunnen door PowerApps worden gelezen. De spaties worden echter wel vervangen door de hexadecimale escape-code **'\_x0020\_'**. **'Naam kolom'** wordt in SharePoint bijvoorbeeld weergegeven als **'Naam_x0020_kolom'** in de gegevensindeling of in een formule in PowerApps.

## <a name="prerequisites"></a>Vereisten
Open PowerApps door *een* van deze stappen uit te voeren:

* [Registreer u](../signup-for-powerapps.md) voor PowerApps, [installeer PowerApps Studio voor Windows](http://aka.ms/powerappsinstall), open het en meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
* [Open de webversie van PowerApps Studio](https://create.powerapps.com/api/start) in een browser.
  
    Zie [Create or edit apps in a browser](../create-app-browser.md) (Apps in een browser maken of bewerken) voor een lijst met ondersteunde browsers en de beperkingen in de preview-versie van de webversie van PowerApps Studio.

## <a name="create-an-app"></a>Een app maken
* [Genereer automatisch een app](../app-from-sharepoint.md) op basis van gegevens in een SharePoint-lijst.
  
    De app heeft standaard drie schermen: een om in records te bladeren, een om details van één record weer te geven en een om record te maken of bij te werken. Nadat de app is gegenereerd, wilt u waarschijnlijk [het bladerscherm](../customize-layout-sharepoint.md) en [de schermen voor details en bewerken](../customize-forms-sharepoint.md) aan uw wensen aanpassen.
  
    **Opmerking**: Als de SharePoint-lijst een kolom van het type **Keuze**, **Opzoeken** of **Persoon of groep** bevat, raadpleegt u [Gegevens in een galerie weergeven](connection-sharepoint-online.md#show-data-in-a-gallery) verderop in dit onderwerp.
* Bouw uw eigen app door [verbinding te maken met SharePoint](../connect-to-sharepoint.md), de concepten in [Een volledig nieuwe app maken](../get-started-create-from-blank.md) te lezen en deze toe te passen op SharePoint in plaats van Excel.

## <a name="add-a-sharepoint-list-to-an-existing-app"></a>Een SharePoint-lijst toevoegen aan een bestaande app
1. Open in PowerApps Studio de app die u wilt bijwerken.
2. Klik of tik op het lint, op het tabblad **Weergeven**, op **Gegevensbronnen**
3. Klik of tik in het rechterdeelvenster op **Gegevensbron toevoegen**.
   
    ![Gegevensbron toevoegen](./media/connection-sharepoint-online/add-data-source.png)
4. Klik of tik op **Nieuwe verbinding**, klik of tik op **SharePoint** en klik of tik op **Verbinden**.
   
    ![SharePoint-verbinding toevoegen](./media/connection-sharepoint-online/add-sharepoint.png)
5. Geef het type SharePoint-site op waarmee u verbinding wilt maken:
   
    ![Type verbinding opgeven](./media/connection-sharepoint-online/choose-type.png)
   
   * Klik of tik op **Rechtstreekse verbinding maken (cloudservices)** om verbinding te maken met SharePoint Online.
   * Klik of tik op **Verbinding maken via een on-premises gegevensgateway** om verbinding te maken met een on-premises SharePoint-site.
     
       Geef **Windows** op als verificatietype en geef uw referenties op. (Als uw referenties een domeinnaam bevatten, geef deze dan op als *domein\alias*.)
     
       ![Referenties opgeven](./media/connection-sharepoint-online/specify-creds.png)
     
       **Opmerking**: Als er geen on-premises gegevensgateway is geïnstalleerd, [installeert u er een](../gateway-reference.md) en klikt of tikt u op het pictogram om de lijst met gateways te vernieuwen.
     
       Klik of tik onder **Een gateway kiezen** op de gateway die u wilt gebruiken.
     
       ![Gateway kiezen](./media/connection-sharepoint-online/choose-gateway.png)
6. Klik of tik op **Verbinden**.
7. Klik of tik onder **Verbinding maken met een SharePoint-site** op een vermelding in de lijst **Recente sites** (of typ of plak de URL voor de site die u wilt gebruiken) en klik of tik op **Ga**.
   
    ![Een SharePoint-site selecteren](./media/connection-sharepoint-online/select-sp-site.png)
8. Schakel onder **Een lijst kiezen** het selectievakje in voor een of meer lijsten die u wilt gebruiken en klik of tik op **Verbinden**:  
   
    ![Tabellen in SharePoint selecteren](./media/connection-sharepoint-online/select-sp-tables.png)
   
    Niet alle soorten lijsten worden standaard weergegeven. Als de naam van de lijst die u wilt gebruiken niet wordt weergegeven, scrolt u naar beneden en typt u de lijstnaam in het vak **Een aangepaste lijstnaam invoeren**.
   
    ![Aangepaste lijst in SharePoint](./media/connection-sharepoint-online/custom-list.png)
   
    De gegevensbronnen worden toegevoegd aan uw app.
   
    ![Lijst met gegevensbronnen die zijn toegevoegd aan de app](./media/connection-sharepoint-online/data-sources-list.png)

## <a name="show-data-in-a-gallery"></a>Gegevens weergeven in een galerie
Als u gegevens uit een van deze typen kolommen in een galerie wilt weergeven, gebruikt u de formulebalk om de eigenschap **Tekst** van een of meer besturingselementen **Label** in die galerie in te stellen:

* Voor een **keuze**- of **opzoek**kolom geeft u **ThisItem.[Kolomnaam].Value** op om gegevens weer te geven in die kolom.
  
    Geef bijvoorbeeld **ThisItem.Locatie.Value** op als u een **keuze**kolom hebt met de naam **Locatie** en geef **ThisItem.Postcode.Value** op als u een **opzoek**kolom met de naam **Postcode** hebt.
* Voor een kolom van het type **Persoon of groep** geeft u **ThisItem.[Kolomnaam].DisplayName** op om de weergavenaam van de gebruiker of de groep weer te geven.
  
    Geef bijvoorbeeld **ThisItem.Manager.DisplayName** op om weergavenamen weer te geven uit een kolom van het type **Persoon of groep** genaamd **Manager**.
  
    U kunt ook andere informatie over gebruikers weergeven, zoals e-mailadressen of functies. Als u een volledige lijst met opties wilt weergeven, geeft u **ThisItem.[Kolomnaam].** op (inclusief de punt aan het eind).
  
    **Opmerking**: Voor een kolom van het type **CreatedBy** geeft u **ThisItem.Author.DisplayName** op om de weergavenamen weer te geven van gebruikers die items in de lijst hebben gemaakt. Voor een kolom van het type **ModifiedBy** geeft u **ThisItem.Editor.DisplayName** op om de weergavenamen weer te geven van gebruikers die items in de lijst hebben gewijzigd.
* Voor een kolom met **beheerde gegevens** geeft u **ThisItem.[Kolomnaam].Label** op om gegevens in die kolom weer te geven.
  
    Geef bijvoorbeeld **ThisItem.Talen.Label** op als u een kolom met **beheerde metagegevens** genaamd **Talen** hebt.

## <a name="next-steps"></a>Volgende stappen
* Lees hoe u [gegevens uit een gegevensbron weergeeft](../add-gallery.md).
* Lees hoe u [gegevens weergeeft en records maakt of bijwerkt](../add-form.md).
* Bekijk andere soorten [gegevensbronnen](../connections-list.md) waarmee u verbinding kunt maken.

