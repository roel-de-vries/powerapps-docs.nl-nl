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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-connection-roles"></a>Verbindingsrollen configureren

Met Common Data Service voor Apps kunt u **verbindingen** tussen entiteitsrecords definiëren zonder een entiteitsrelatie te maken. In modelgestuurde apps kunnen mensen een benoemde koppeling maken tussen records om een minder formele relatie in te stellen waarvoor het niet nodig is een werkelijke entiteitsrelatie te maken. Enkele voorbeelden zijn *vriend*, *broer/zus*, *partner*, *genodigde* en *belanghebbende*. Sommige verbindingen kunnen ook wederzijds zijn, zoals *kind* en *ouder*, *echtgenoot* en *echtgenote* of *arts* en *patiënt*.

Wanneer mensen een verbinding tussen twee records instellen, kunnen zij ook een beschrijving en aanvullende informatie toevoegen, zoals begin- en einddatums voor de relatie. Meer informatie: [Verbindingen maken om relaties tussen records te definiëren en weer te geven](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records).

Iedereen met schrijftoegang tot de entiteit **Verbindingsrol** kan instellen welke verbindingen beschikbaar zijn voor gebruik door personen.

## <a name="view-connection-roles"></a>Verbindingsrollen weergeven

Er is al een aantal standaardverbindingsrollen in CDS voor Apps geconfigureerd. Als u deze wilt weergeven, moet u naar het gebied met instellingen gaan. 

### <a name="navigate-to-the-settings-area"></a>Navigeren naar het gebied met instellingen

1. Bewerk tijdens het weergeven van een modelgestuurde app de URL om alles na `dynamics.com` te verwijderen en de pagina te vernieuwen.
1. Navigeer naar **Instellingen** > **Bedrijf** > **Bedrijfsbeheer** en selecteer vervolgens **Verbindingsrollen**.

![Verbindingsrollen in de Bedrijfsbeheer-instellingen](media/navigate-settings-connection-roles.png)

In deze weergave kunt u alle verbindingsrollen zien die voor deze omgeving beschikbaar zijn en u kunt ze hier bewerken.

> [!NOTE]
> Als u verbindingsrollen met een oplossing wilt distribueren, moet u ervoor zorgen dat ze in de oplossing zijn opgenomen die u wilt distribueren. Meer informatie: [Verbindingsrollen aan een oplossing toevoegen](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>Geef verbindingsrollen in de oplossingenverkenner weer.

Omdat verbindingsrollen *oplossingen ondersteunen*, wat betekent dat ze in een oplossing kunnen worden opgenomen, kunt u verbindingsrollen ook toevoegen aan een oplossing die u distribueert.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De meeste verbindingsrollen die u kunt zien in het gebied **Instellingen**, worden gedefinieerd in de *interne* **Standaardoplossing** (niet te verwarren met de **Common Data Service-standaardoplossing**). Deze interne **Standaardoplossing** bevat alle aanpassingen in het systeem. Als u de **Standaardoplossing** wilt weergeven, kiest u de weergave **Alle oplossingen - intern**.

## <a name="add-connection-roles-to-a-solution"></a>Verbindingsrollen aan een oplossing toevoegen

In het algemeen wordt het afgeraden om onderdelen in de interne **Standaardoplossing** te bewerken. Binnen de **Common Data Service-standaardoplossing** of een oplossing die u hebt gemaakt om in te werken, kunt u de opdracht **Bestaande toevoegen** gebruiken om standaardverbindingsrollen in uw oplossing te halen.

![Bestaande verbindingsrol toevoegen](media/add-existing-connection-role.png)

Zodra u de verbindingsrol aan uw oplossing toevoegt, kunt u deze bewerken waar deze zichtbaar is.

## <a name="create-or-edit-connection-roles"></a>Maak of bewerk verbindingsrollen.

> [!IMPORTANT]
> Als u van plan bent een oplossing te distribueren die nieuwe verbindingsrollen of wijzigingen in de bestaande verbindingsrollen bevat, moet u deze aan de oplossing toevoegen die u distribueert. Als u nieuwe verbindingsrollen met het gebied **Instellingen** bewerkt of maakt, worden deze verbindingsrollen toegevoegd aan de interne **Standaardoplossing** en worden ze niet opgenomen in de oplossing die u distribueert, tenzij u deze eerst aan uw oplossing toevoegt. Meer informatie [Verbindingsrollen aan een oplossing toevoegen](#add-connection-roles-to-a-solution)

Selecteer in de lijst **Verbindingsrollen** een van de verbindingsrollen om deze te bewerken.
Er zijn drie stappen om een verbindingsrol te definiëren. Deze stappen worden duidelijk in het formulier genoemd.

![Formulier Verbindingsrol maken](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>De verbindingsrol omschrijven

Stel de volgende velden in:

|Veld|Beschrijving|
|--|--|
|**Name**|(Vereist) De tekst waarmee de verbinding wordt beschreven.|
|**Categorie van verbindingsrol**|Een groep waarmee de categorie van de verbinding wordt beschreven. Meer informatie: [Waarden van categorie van verbindingsrol](#connection-role-category-values)|
|**Beschrijving**|Geef een definitie op voor de rol.|

#### <a name="connection-role-category-values"></a>Waarden van Categorie van verbindingsrol

De standaardwaarden **Categorie van verbindingsrol** zijn:
- Onderneming
- Gezin
- Sociaal
- Sales
- Overig
- Belanghebbende
- VERKOOPTEAM
- Service

U kunt nieuwe categorieën toevoegen of bestaande categorieën aanpassen door de algemene optieset **Categorie** te bewerken. Meer informatie: [Algemene optiesets maken en bewerken voor Common Data Service voor Apps (selectielijsten)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>Recordtypen selecteren

Selecteer welke recordtypen beschikbaar moeten zijn om te verbinden.

> [!NOTE]
> Hoewel **Alle** standaard is geselecteerd, moet u nagaan welke typen geschikt zijn voor de verbindingsrol die u toevoegt.

### <a name="matching-connection-roles"></a>Overeenkomende verbindingsrollen

In deze optionele stap kunt u alle rollen definiëren die op een wederzijdse manier worden toegepast. Het is niet vereist, maar verbindingen hebben meer betekenis als deze worden gedefinieerd.

Zo kunnen mensen instellen dat Gerard een *Vriend* van Maria is, maar betekent dit dat Maria een *Vriend* van Gerard is? We hopen het maar. Maar als Gerard de *Vader* is van Maria, betekent dit niet dat Maria de *Vader* is van Gerard. Voor een juiste instelling hiervan is deze extra stap vereist.

Als mensen een verbindingsrol instellen die geen overeenkomende verbindingsrol heeft, wordt de rol alleen weergegeven wanneer de verbinding wordt weergegeven vanuit de record waarop de verbinding is toegepast. Wanneer de rol wordt weergegeven vanuit de verbonden record, is de rol leeg tenzij een overeenkomende rol is ingesteld.

Voor roldefinities zoals *Vriend*, *Echtgenoot*, *Collega* of *Broer/zus* kunt u het beste de overeenkomende rol aan de rol zelf toewijzen. Als één overeenkomende verbindingsrol is geconfigureerd, wordt deze enige overeenkomende verbindingsrol in beide richtingen toegepast.

> [!IMPORTANT]
> U moet een nieuwe verbindingsrol opslaan zonder deze overeenkomende verbindingsrol voordat u de overeenkomende verbindingsrol aan de rol zelf kunt toewijzen.

U ziet dat sommige verbindingsrollen al zijn geconfigureerd met overeenkomende verbindingsrollen. *Voormalige werknemer* hoort bij *Voormalige werkgever* en omgekeerd. Dit type van een een-op-een overeenkomende verbindingsrol komt heel vaak voor.

U kunt meerdere overeenkomende verbindingsrollen configureren om complexe relaties te beschrijven. Als u een verbindingsrol maakt zoals *Vader*, kunt u nog twee rollen configureren zoals *Dochter* en *Zoon* en beide als overeenkomende verbindingsrollen toepassen op *Vader*. Zo ook horen beide verbindingsrollen *Dochter* en *Zoon* bij *Vader*. Uiteraard moet u vervolgens een equivalente rol voor *Moeder* instellen die op dezelfde manier hoort bij *Dochter* en *Zoon*.

> [!TIP]
> Voordat u een complexe set verbindingsrollen maakt, kunt u bekijken of een eenvoudigere set van rollen voldoende is. Zo kunt u bijvoorbeeld in plaats van een complexe set verbindingsrollen te maken, zoals *Vader*, *Moeder*, *Zoon*, en *Dochter*, eenvoudigweg *Ouder* en *Kind* gebruiken.

Als meerdere overeenkomende verbindingsrollen zijn geconfigureerd, vertegenwoordigen deze verbindingsrollen de enige geldige wederzijdse rollen. De eerste wordt automatisch als de standaardwaarde toegepast. Als de standaardwaarde niet correct is, moeten mensen de verbinding handmatig bewerken en kiezen tussen geldige opties die in de configuratie zijn gedefinieerd.

### <a name="see-also"></a>Zie ook
<!-- This is in the basics guide. It needs to be migrated -->
[Verbindingen maken om relaties tussen records te definiëren en weer te geven](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[Algemene optiesets maken en bewerken voor Common Data Service voor Apps (selectielijsten)](create-edit-global-option-sets.md)<br />
[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)


