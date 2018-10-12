---
title: Verbindingsrollen configureren | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.author: matp
manager: brycho
ms.openlocfilehash: 4faf195f1c751e3796267d52725c1cb753c4889d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679916"
---
# <a name="configure-connection-roles"></a>Verbindingsrollen configureren

Met Common Data Service voor apps kunt u **verbindingen** definiëren tussen entiteitsrecords zonder een entiteitsrelatie te maken. In modelgestuurde apps kunnen mensen een benoemde koppeling tot stand brengen tussen records om een minder formele relatie tot stand te brengen die het maken van een daadwerkelijke entiteitsrelatie niet rechtvaardigt. Enkele voorbeelden zijn *vriend*, *bloedverwant*, *partner*, *deelnemer* en *belanghebbende*. Sommige verbindingen kunnen ook wederzijds zijn, zoals *kind* en *ouder*, *man* en *vrouw* of *dokter* en *patiënt*.

Wanneer mensen een verbinding tussen twee records instellen, kunnen ze ook een beschrijving en aanvullende informatie toevoegen, zoals begin- en einddatums voor de relatie. Meer informatie: [Verbindingen tot stand brengen om relaties tussen records te definiëren en weer te geven](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)

Iedereen met schrijftoegang tot de entiteit **Verbindingsrol** kan bepalen welke verbindingen mensen kunnen gebruiken.

## <a name="view-connection-roles"></a>Verbindingsrollen weergeven

Er is een aantal standaardverbindingsrollen vooraf geconfigureerd in CDS for Apps. Als u deze wilt weergeven, gaat u naar het instellingengedeelte. 

### <a name="navigate-to-the-settings-area"></a>Naar het instellingengedeelte navigeren

1. Bewerk de URL tijdens het weergeven van een modelgestuurde app om alles na `dynamics.com` te verwijderen en vernieuw de pagina.
1. Navigeer naar **Instellingen** > **Zakelijk** > **Ondernemingsbeheer** en selecteer vervolgens **Verbindingsrollen**.

![Verbindingsrollen in de instellingen voor Ondernemingsbeheer](media/navigate-settings-connection-roles.png)

In deze weergave ziet u alle verbindingsrollen die beschikbaar zijn voor deze omgeving. U kunt ze hier bewerken.

> [!NOTE]
> Als u verbindingsrollen wilt distribueren met een oplossing, controleert u of ze zijn opgenomen in de oplossing die u wilt distribueren. Meer informatie: [Verbindingsrollen toevoegen aan een oplossing](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>U kunt verbindingsrollen weergeven in de Solution Explorer.

Omdat verbindingsrollen *oplossingen ondersteunen*, wat betekent dat ze kunnen worden opgenomen in een oplossing, kunt u verbindingsrollen ook toevoegen aan een oplossing die u distribueert.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De meeste verbindingsrollen die u kunt zien in het gedeelte **Instellingen**, zijn gedefinieerd in de *interne* **Standaardoplossing** (niet te verwarren met de **Common Data Services-standaardoplossing**). Deze interne **Standaardoplossing** bevat alle aanpassingen in het systeem. Als u de **Standaardoplossing** wilt weergeven, kiest u de weergave **Alle oplossingen - Intern**.

## <a name="add-connection-roles-to-a-solution"></a>Verbindingsrollen toevoegen aan een oplossing

Over het algemeen wordt het niet aanbevolen om onderdelen te bewerken in de interne **Standaardoplossing**. Binnen de **Common Data Services-standaardoplossing** of een oplossing die u hebt gemaakt om in te werken, kunt u de opdracht **Bestaand item toevoegen** om een van de standaardverbindingsrollen in uw oplossing te brengen.

![Bestaande verbindingsrol toevoegen](media/add-existing-connection-role.png)

Als u de verbindingsrol eenmaal hebt toegevoegd aan uw oplossing, kunt u deze bewerken daar waar de rol zichtbaar is.

## <a name="create-or-edit-connection-roles"></a>Maak of bewerk verbindingsrollen.

> [!IMPORTANT]
> Als u van plan bent een oplossing te distribueren die nieuwe verbindingsrollen of wijzigingen in de bestaande verbindingsrollen bevat, moet u deze rollen toevoegen aan de oplossing die u wilt distribueren. Wanneer u verbindingsrollen bewerkt of nieuwe verbindingsrollen toevoegt met behulp van het gedeelte **Instellingen**, worden deze verbindingsrollen toegevoegd aan de interne **standaardoplossing** en worden ze niet opgenomen in de oplossing die u wilt distribueren, tenzij u ze eerst toevoegt aan uw oplossing. Meer informatie: [Verbindingsrollen toevoegen aan een oplossing](#add-connection-roles-to-a-solution)

In de lijst **Verbindingsrollen** selecteert u een van de verbindingsrollen om te bewerken.
Er zijn drie stappen om een verbindingsrol te definiëren die duidelijk in het formulier worden genoemd.

![Formulier Verbindingsrol maken](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>De verbindingsrol beschrijven

Stel de volgende velden in:

|Veld|Beschrijving|
|--|--|
|**Naam**|(Vereist) De tekst die de verbinding beschrijft.|
|**Categorie van verbindingsrol**|Een groep die de categorie van de verbinding beschrijft. Meer informatie: [Waarden van de verbindingsrolcategorie](#connection-role-category-values)|
|**Description**|Geef een definitie op voor de rol.|

#### <a name="connection-role-category-values"></a>Waarden voor de verbindingsrolcategorie

De standaardwaarden voor **Categorie van verbindingsrol** zijn:
- Business
- Familie
- Sociaal
- Verkoop
- Overige
- Belanghebbende
- Verkoopteam
- Service

U kunt nieuwe categorieën toevoegen of bestaande wijzigen door de globale optieset **Categorie** te bewerken. Meer informatie: [Globale optiesets maken en bewerken voor Common Data Service for Apps (selectielijsten)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>Recordtypen selecteren

Selecteer welke recordtypen beschikbaar moeten zijn om verbinding mee te maken.

> [!NOTE]
> Hoewel **Alle** standaard is geselecteerd, moet u wel kijken welke typen geschikt zijn voor de verbindingsrol die u wilt toevoegen.

### <a name="matching-connection-roles"></a>Overeenkomende verbindingsrollen

In deze optionele stap kunt u rollen definiëren die op een wederkerige manier worden toegepast. Dit is niet vereist, maar verbindingen zijn duidelijker als ze zijn gedefinieerd.

Mensen kunnen bijvoorbeeld instellen dat Glen een *Vriend* is van Mary, maar betekent dit dat Mary een *Vriend* is van Glen? Dat hopen we. Maar als Glen de *vader* is van Mary, betekent dit niet dat Mary de *vader* van Glen is. Deze extra stap is vereist om de juiste wederkerigheid tot stand te brengen.

Wanneer mensen een verbindingsrol instellen die geen overeenkomende verbindingsrol heeft, wordt de rol alleen weergegeven wanneer de verbinding wordt weergegeven van de record waarop de verbinding is toegepast. Wanneer deze wordt bekeken vanaf de verbonden record, is de rol leeg, tenzij een overeenkomende rol is ingesteld.

Voor roldefinities als *Vriend*, *Partner*, *Collega* of *Bloedverwant* kunt u de overeenkomende rol het beste toewijzen aan zichzelf. Als één overeenkomende verbindingsrol is geconfigureerd, wordt de enkele overeenkomende verbindingsrol toegepast in beide richtingen.

> [!IMPORTANT]
> U moet een nieuwe verbindingsrol opslaan zonder deze overeenkomende verbindingsrol voordat u de overeenkomende verbindingsrol kunt instellen op zichzelf.

U zult merken dat sommige verbindingsrollen al zijn geconfigureerd met de bijbehorende verbindingsrollen. *Voormalig werknemer* komt overeen met *Voormalige werkgever* en vice versa. Dit type een-op-een overeenkomende verbindingsrol is het meest voorkomende.

U kunt meerdere overeenkomende verbindingsrollen configureren om complexe relaties te beschrijven. Als u een verbindingsrol zou maken als *Vader*, kunt u nog twee andere rollen configureren, zoals *Dochter* en *Zoon*, en beide toepassen als overeenkomende verbindingsrollen met  *Vader*. Op hun beurt moeten zowel de verbindingsrol *Dochter* als de verbindingsrol *Zoon* worden afgestemd op *Vader*. U moet dan natuurlijk een gelijkwaardige rol instellen voor *Moeder* die op een vergelijkbare manier overeenkomen met *Dochter* en *Zoon*.

> [!TIP]
> Voordat u een complexe reeks verbindingsrollen maakt, kunt u kijken of een eenvoudiger reeks rollen niet volstaat. In plaats van bijvoorbeeld een complexe reeks verbindingsrollen als *Vader*, *Moeder*, *Zoon* en *Dochter* te maken, kunt u ook kijken of *Ouder* en *Kind* voor u werken.

Als meer dan één overeenkomende verbindingsrol is geconfigureerd, vertegenwoordigen die verbindingsrollen de enige geldige wederzijdse rollen. De eerste wordt automatisch toegepast als de standaardwaarde. Als de standaardwaarde niet juist is, moeten mensen de verbinding handmatig bewerken en kiezen tussen geldige opties die zijn gedefinieerd in de configuratie.

### <a name="see-also"></a>Zie ook
<!-- This is in the basics guide. It needs to be migrated -->
[Verbindingen tot stand brengen om relaties tussen records te definiëren en weer te geven](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[Globale optiesets maken en bewerken voor Common Data Service voor apps (selectielijsten)](create-edit-global-option-sets.md)<br />
[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)


