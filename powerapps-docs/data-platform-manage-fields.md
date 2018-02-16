---
title: Aangepaste velden in een entiteit beheren | Microsoft Docs
description: Aangepaste velden in een entiteit maken, lezen, bijwerken en verwijderen.
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/20/2017
ms.author: kfend
ms.openlocfilehash: f5d769459f9d10e1d0f4bab2c1cc182407865053
ms.sourcegitcommit: e827813cd898ca9a1046b5952ea5e32ce2989a65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2018
---
# <a name="manage-custom-fields"></a>Aangepaste velden beheren
U kunt een of meer aangepaste velden in een entiteit maken en bijwerken. Als u een aangepast veld maakt, geeft u een aantal eigenschappen op, bijvoorbeeld de naam en de weergavenaam van het veld, en het type gegevens dat het kan bevatten. Zie [Entity field data types](https://docs.microsoft.com/common-data-service/entity-reference/field-data-types) (Gegevenstypen voor entiteitsvelden) en [Entity field properties](https://docs.microsoft.com/common-data-service/entity-reference/field-properties) (Eigenschappen van entiteitsvelden) voor meer informatie.

> [!NOTE]
> Elke entiteit heeft [systeemvelden](data-platform-create-entity.md#system-fields-and-the-record-title-field), zoals velden die aangeven wanneer een record voor het laatst is bijgewerkt en wie dat heeft gedaan. Daarnaast hebben [standaardentiteiten](data-platform-intro.md#standard-entities) standaardvelden. U kunt systeemvelden en standaardvelden niet wijzigen of verwijderen. Als u een aangepast veld maakt, moet dit naast deze ingebouwde velden extra functionaliteit bieden.

## <a name="create-a-field"></a>Een veld maken

1. Ga naar [powerapps.com](https://web.powerapps.com) en vouw de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster. Er wordt een lijst met entiteiten weergegeven. Klik of tik op de kolomkop **Type** om aangepaste entiteiten bovenaan de lijst weer te geven. U kunt de lijst ook filteren door een of meer tekens in het zoekvak te tikken.

2. Klik of tik op een entiteit en vervolgens bovenaan het scherm op **Add field**.

3. Geef onder **Weergavenaam** de regel tekst op waarmee het veld voor gebruikers wordt geïdentificeerd. Zie [Een app maken](data-platform-create-app.md) voor meer informatie.

4. Geef onder **Naam** de regel tekst op waarmee naar het veld wordt verwezen, bijvoorbeeld in een formule als u een app aan het maken bent.
   
    > [!IMPORTANT]
    > Geef een naam op die uniek, duidelijk en zinvol is omdat u de naam niet meer kunt wijzigen als het veld is gemaakt.

5. Geef onder **Type** het type gegevens in het veld op, bijvoorbeeld **Tekst** of **Getal**.
   
    > [!IMPORTANT]
    > Denk hier goed over na, omdat u deze eigenschap niet meer kunt wijzigen als het veld gegevens bevat. Zie [(Wat zijn entiteiten?)](data-platform-intro.md#custom-fields) voor informatie over de gegevenstypen die u kunt opgeven.

6. Wanneer u daarom wordt gevraagd, geeft u aanvullende informatie op over het opgegeven gegevenstype.

7. Schakel onder **Uniek** het selectievakje in als elke record een unieke waarde in dit veld moet bevatten.

8. Schakel onder **Vereist** het selectievakje in als elke record een waarde in dit veld moet bevatten.
   
    > [!IMPORTANT]
    > Van een aangepast veld in een standaardentiteit kan niet worden vereist dat het gegevens bevat. Deze beperking voorkomt dat u grote problemen krijgt met apps die van die entiteit afhankelijk zijn.

9. Klik of tik op **Opslaan** om uw wijzigingen in te dienen.
   
    > [!IMPORTANT]
    > De wijzigingen gaan verloren als u ze niet opslaat voordat u een andere pagina in de browser opent of de browser sluit.

Er wordt een bericht weergegeven wanneer de bewerking is voltooid. Als de bewerking is mislukt, wordt een foutbericht weergegeven met de problemen die zijn opgetreden, zodat u die kunt corrigeren.

## <a name="update-or-delete-a-field"></a>Een veld bijwerken of verwijderen
1. Klik of tik op [powerapps.com](https://web.powerapps.com) op **Beheren**, klik of tik op **Entiteiten** en vervolgens op een entiteit.
2. Klik of tik in de lijst met velden voor de geselecteerde entiteit op een veld en volg een van de volgende twee stappen:
   
   * Wijzig een of meer eigenschappen van het veld. Denk daarbij aan de [aanbevolen procedures en beperkingen](data-platform-manage-fields.md#best-practices-and-restrictions).
     
       Druk op de TAB-toets om de volgende eigenschap te selecteren. Als u alle wijzigingen ongedaan wilt maken, klikt of tikt u op het beletselteken (…) voor het veld en klikt of tikt u op **Ongedaan maken**.
   * Verwijder het veld door op het bijbehorende beletselteken (…) aan de rechterkant van het veld te klikken of tikken en vervolgens op **Verwijderen** te klikken of tikken.
3. Klik of tik op **Opslaan** om uw wijzigingen in te dienen.
   
    > [!IMPORTANT]
    > De wijzigingen gaan verloren als u ze niet opslaat voordat u een andere pagina in de browser opent of de browser sluit.

Er wordt een bericht weergegeven wanneer de bewerking is voltooid. Als de bewerking is mislukt, wordt een foutbericht weergegeven met de problemen die zijn opgetreden, zodat u die kunt corrigeren.

## <a name="best-practices-and-restrictions"></a>Aanbevolen procedures en beperkingen
Houd bij het maken en wijzigen van velden rekening met het volgende:

* Systeemvelden en hun waarden kunnen niet worden gewijzigd of verwijderd.
* In een standaardentiteit kunt u geen standaardveld wijzigen of verwijderen, een veld toevoegen waarvoor gegevens zijn vereist of een andere wijziging aanbrengen waardoor een app die van die entiteit afhankelijk is, defect kan raken.
* Bij een aangepaste entiteit moet u ervoor zorgen dat een app die van die entiteit afhankelijk is, niet defect kan raken door eventuele wijzigingen.
* Geef elk aangepast veld een naam die uniek is binnen die entiteit. U kunt de naam van een eenmaal gemaakt veld niet wijzigen.
* U kunt het gegevenstype van ieder veld wijzigen, mits het veld nog geen gegevens bevat. Als het veld al gegevens bevat, kunt u het gegevenstype alleen wijzigen als de aanwezige gegevens voldoen aan de vereisten voor het nieuwe gegevenstype. U kunt bijvoorbeeld het gegevenstype van een veld wijzigen van **Getal** in **Tekenreeks**, maar u kunt het gegevenstype niet wijzigen van **Tekenreeks** in **Getal** als het veld niet-numerieke gegevens bevat.
* Een app die gebruikmaakt van een entiteit kan defect raken als u een veld in die entiteit op een van de volgende manieren wijzigt:
  * U wijzigt het gegevenstype van het veld.
  * U stelt waarden vereist, maar een of meer records bevatten geen waarde in dat veld.
  * U stelt unieke waarden vereist, maar als twee of meer records bevatten dezelfde waarde in dat veld.

## <a name="next-steps"></a>Volgende stappen
* [Relaties tussen entiteiten definiëren](data-platform-entity-lookup.md)
* [Een app maken met behulp van entiteiten](data-platform-create-app.md)
* [Een volledig nieuwe app maken met een Common Data Service-database](data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

