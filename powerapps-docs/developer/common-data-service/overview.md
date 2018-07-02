---
title: Overzicht van Common Data Service for Apps voor ontwikkelaars | Microsoft Docs
description: Lees meer informatie over hoe ontwikkelaars met Common Data Service for Apps voor toegevoegde waarde kunnen zorgen.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
ms.openlocfilehash: c07a6505c0a08eca706c08cc2e4d607cd5322dfe
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2018
ms.locfileid: "36949232"
---
# <a name="common-data-service-for-apps-developer-overview"></a>Overzicht van Common Data Service for Apps voor ontwikkelaars
PowerApps biedt gebruikers, bedrijven, onafhankelijke softwareleveranciers (ISV's) en systeemintegrators (SI's) een krachtig platform voor het bouwen van Line-Of-Business-apps. De nieuwe toevoeging aan PowerApps in deze release is de uitbreiding van Common Data Service, nu Common Data Service for Apps genoemd. Deze service bevat nu de kernfunctionaliteit van het Dynamics 365-platform voor Dynamics 365 for Sales, Marketing en Customer Service.


## <a name="get-started"></a>Aan de slag
Als u al ervaring hebt met de Dynamics 365 for Sales-, Marketing- of Customer Service-apps, zult u merken dat uw ervaring goed van pas komt bij het aanpassen en uitbreiden van Common Data Service for Apps.

Als u nog geen ervaring hebt met de Dynamics 365 for Sales-, Marketing- en Customer Service-apps, bieden de volgende onderwerpen een algemeen overzicht van de belangrijke concepten die u op weg helpen bij het werken met Common Data Service for Apps.

> [!NOTE]
> - Modelgestuurde apps kunnen worden gekoppeld aan Common Data Service for Apps. Zie [Overzicht van modelgestuurde apps voor ontwikkelaars](../model-driven-apps/overview.md) voor meer informatie over hoe ontwikkelaars voor toegevoegde waarde op toepassingsniveau kunnen zorgen. De inhoud in deze sectie verwijst alleen naar uitbreidingen die ontwikkelaars op het serviceniveau kunnen toepassen. 
> - Omdat voor Common Data Service for Apps en de Dynamics 365 for Sales-, Marketing- en Customer Service-apps hetzelfde platform wordt gebruikt, vindt u in de [Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/developer-guide) meer informatie voor ontwikkelaars. In deze onderwerpen vindt u voor meer informatie een overzicht met koppelingen naar de ontwikkelaarshandleiding en andere handleidingen.


## <a name="tools-and-resources-for-developers"></a>Hulpprogramma's en resource voor ontwikkelaars

Ontwikkelaars kunnen de volgende hulpprogramma's en resources gebruiken tijdens het werken met oplossingen via Common Data Service for Apps.

### <a name="tools-available-for-download-from-nuget"></a>Hulpprogramma's die kunnen worden gedownload via NuGet

De volgende hulpprogramma's worden gedistribueerd in NuGet-pakketten. In het Engelstalige onderwerp [Developer Guide: Download tools from NuGet](/dynamics365/customer-engagement/developer/download-tools-nuget) (Ontwikkelaarshandleiding: Hulpprogramma's downloaden via NuGet) vindt u een PowerShell-script dat u kunt gebruiken om de meest recente versies van deze hulpprogramma's te downloaden en uit te pakken.

|Hulpprogramma  |Beschrijving  |
|---------|---------|
|Hulpprogramma voor het genereren van code `CrmSvcUtil.exe`|Een opdrachtregelprogramma voor het genereren van code waarmee vroege gebonden .NET Framework-klassen worden gegenereerd waarmee het entiteitsgegevensmodel wordt aangegeven dat door de organisatieservice wordt gebruikt. <br />Meer informatie: <br />[Organisatieservice](use-web-services.md#organization-service)<br />[Dynamics 365 Customer Engagement Developer Guide: Create early bound entity classes with the code generation tool](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Vroege gebonden entiteitsklassen maken met het hulpprogramma voor het genereren van code)|
|Hulpprogramma voor het migreren van de configuratie `DataMigrationUtility.exe`|Wordt gebruikt om configuratiegegevens tussen omgevingen te verplaatsen. Configuratiegegevens worden gebruikt voor het definiëren van aangepaste functionaliteit en worden meestal opgeslagen in aangepaste entiteiten. Dit hulpprogramma is niet ontworpen om zakelijke gegevens te verplaatsen. <br /> Zie [Beheerdershandleiding voor Dynamics 365 Customer Engagement: Configuratiegegevens verplaatsen tussen exemplaren en organisaties met het hulpprogramma Configuration Migration](/dynamics365/customer-engagement/admin/manage-configuration-data) voor meer informatie.|
|Package Deployer `PackageDeployer.exe`|Wordt gebruikt voor het implementeren van pakketten in instanties van Common Data Service for Apps. Een pakket is een installeerbare eenheid, dat oplossingen bevat. <br /> Meer informatie: <br />[Oplossingspakketten implementeren](introduction-solutions.md#deploy-solution-packages)<br />[Dynamics 365 Customer Engagement Developer Guide: Create packages for the Dynamics 365 Package Deployer](/dynamics365/customer-engagement/developer/create-packages-package-deployer) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Pakketten maken voor Dynamics 365 Package Deployer)|
|Registratiehulpprogramma voor invoegtoepassingen `PluginRegistration.exe`|Een hulpprogramma dat wordt gebruikt om invoegtoepassingsklassen van .NET-assembly aan te melden bij servergebeurtenissen. <br />Meer informatie: <br />[Een invoegtoepassing maken](apply-business-logic-with-code.md#create-a-plug-in)<br />[Dynamics 365 Customer Engagement Developer Guide: Walkthrough: Register a plug-in using the plug-in registration tool](/dynamics365/customer-engagement/developer/walkthrough-register-plugin-using-plugin-registration-tool) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Overzicht: Een invoegtoepassing registreren met het registratiehulpprogramma voor invoegtoepassingen)|
|Hulpprogramma SolutionPackager `SolutionPackager.exe`|Een hulpprogramma waarmee u een gecomprimeerd oplossingsbestand in Common Data Service for Apps omkeerbaar kunt splitsen in meerdere XML-bestanden en andere bestanden, zodat deze bestanden eenvoudig kunnen worden beheerd in een bronbeheersysteem.<br /> Meer informatie: <br />[Teamontwikkeling van oplossingen](introduction-solutions.md#team-development-of-solutions)<br />[Dynamics 365 Customer Engagement Developer Guide: Use the SolutionPackager tool to compress and extract a solution file](/dynamics365/customer-engagement/developer/compress-extract-solution-file-solutionpackager) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Het hulpprogramma SolutionPackager gebruiken om een oplossingsbestand te comprimeren en uit te pakken)|

### <a name="net-sdk-assemblies"></a>.NET SDK-assembly's 

Hieronder vindt u een overzicht met assembly's die .NET-ontwikkelaars kunnen gebruiken. De meest recente versies kunnen worden gedownload via de bijbehorende NuGet-pakketten.

#### <a name="work-with-data"></a>Werken met gegevens

U kunt de volgende assembly's gebruiken om te communiceren met de organisatieservice en Discovery-services.

Zie [Dynamics 365 Customer Engagement Developer Guide: Use the Dynamics 365 Organization service](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: De organisatieservice van Dynamics 365 gebruiken) voor meer informatie.

**NuGet-pakket**: [Microsoft.CrmSdk.CoreAssemblies](https://www.nuget.org/packages/Microsoft.CrmSdk.CoreAssemblies/)

|Assembly  |Naamruimten  |
|---------|---------|
|Microsoft.Crm.Sdk.Proxy.dll|[Microsoft.Crm.Sdk](/dotnet/api/microsoft.crm.sdk)<br />[Microsoft.Crm.Sdk.Messages](/dotnet/api/microsoft.crm.sdk.messages)|
|Microsoft.Xrm.Sdk.dll|[Microsoft.Xrm.Sdk](/dotnet/api/microsoft.xrm.sdk)<br />[Microsoft.Xrm.Sdk.Client](/dotnet/api/microsoft.xrm.sdk.client)<br />[Microsoft.Xrm.Sdk.Discovery](/dotnet/api/microsoft.xrm.sdk.discovery)<br />[Microsoft.Xrm.Sdk.Messages](/dotnet/api/microsoft.xrm.sdk.messages)<br />[Microsoft.Xrm.Sdk.Metadata](/dotnet/api/microsoft.xrm.sdk.metadata)<br />[Microsoft.Xrm.Sdk.Metadata.Query](/dotnet/api/microsoft.xrm.sdk.metadata.query)<br />[Microsoft.Xrm.Sdk.Organization](/dotnet/api/microsoft.xrm.sdk.organization)<br />[Microsoft.Xrm.Sdk.Query](/dotnet/api/microsoft.xrm.sdk.query)<br />[Microsoft.Xrm.Sdk.WebServiceClient](/dotnet/api/microsoft.xrm.sdk.webserviceclient)|

#### <a name="create-process-designer-workflow-extensions"></a>Uitbreidingen voor Procesontwerper (werkstroom) maken

Gebruik de volgende assembly om aangepaste activiteiten aan Procesontwerper toe te voegen. 

Zie [Dynamics 365 Customer Engagement Developer Guide: Custom workflow activities (workflow assemblies)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Aangepaste werkstroomactiviteiten (werkstroomassembly's)) voor meer informatie.

**NuGet-pakket**: [Microsoft.CrmSdk.Workflow](https://www.nuget.org/packages/Microsoft.CrmSdk.Workflow/) 

|Assembly|Naamruimten|
|---------|---------|
|Microsoft.Xrm.Sdk.Workflow.dll|[Microsoft.Xrm.Sdk.Workflow](/dotnet/api/microsoft.xrm.sdk.workflow)<br />[Microsoft.Xrm.Sdk.Workflow.Activities](/dotnet/api/microsoft.xrm.sdk.workflow.activities)<br />[Microsoft.Xrm.Sdk.Workflow.Designers](/dotnet/api/microsoft.xrm.sdk.workflow.designers)|

#### <a name="build-windows-client-applications"></a>Windows-clienttoepassingen bouwen

Gebruik de volgende assembly's om de verbinding met de organisatieservice te vereenvoudigen en Windows-clienttoepassingen te bouwen. 

Zie [Dynamics 365 Customer Engagement Developer Guide: Build Windows client applications using the XRM tools](/dynamics365/customer-engagement/developer/build-windows-client-applications-xrm-tools) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Windows-clienttoepassingen bouwen met de XRM-hulpprogramma's) voor meer informatie.

**NuGet-pakketten**:
- [Microsoft.CrmSdk.XrmTooling.CoreAssembly](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.CoreAssembly/) (Microsoft.Xrm.Tooling.Connector.dll)
- [Microsoft.CrmSdk.XrmTooling.WpfControls](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.WpfControls/) 

|Assembly|Naamruimten  |
|---------|---------|
|Microsoft.Xrm.Tooling.Connector.dll|[Microsoft.Xrm.Tooling.Connector](/dotnet/api/microsoft.xrm.tooling.connector)<br />[Microsoft.Xrm.Tooling.Connector.Model](/dotnet/api/microsoft.xrm.tooling.connector.model)|
|Microsoft.Xrm.Tooling.CrmConnectControl.dll|[Microsoft.Xrm.Tooling.CrmConnectControl](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Model](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.model)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Properties](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.properties)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Utility](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.utility)|
|Microsoft.Xrm.Tooling.WebResourceUtility.dll|[Microsoft.Xrm.Tooling.WebResourceUtility](/dotnet/api/microsoft.xrm.tooling.webresourceutility)|

#### <a name="create-packages"></a>Pakketten maken

Gebruik de volgende assembly's om pakketten te maken voor Package Deployer.

Zie [Dynamics 365 Customer Engagement Developer Guide: Create packages for the Dynamics 365 Package Deployer](/dynamics365/customer-engagement/developer/create-packages-package-deployer) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Pakketten maken voor Dynamics 365 Package Deployer) voor meer informatie.

**NuGet-pakket**: [Microsoft.CrmSdk.XrmTooling.PackageDeployment](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment/)

|Assembly|Naamruimte  |
|---------|---------|
|Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.dll|[Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase](/dotnet/api/microsoft.xrm.tooling.packagedeployment.crmpackageextentionbase)|

#### <a name="create-custom-virtual-entity-data-providers"></a>Gegevensproviders voor aangepaste virtuele entiteiten maken

Gebruik deze assembly om gegevensproviders voor aangepaste virtuele entiteiten te maken. 

Zie [Dynamics 365 Customer Engagement Developer Guide: Get started with virtual entities](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Aan de slag met virtuele entiteiten) voor meer informatie.

**NuGet-pakket**: [Microsoft.CrmSdk.Data](https://www.nuget.org/packages/Microsoft.CrmSdk.Data/)

|Assembly  |Naamruimten  |
|---------|---------|
|Microsoft.Xrm.Sdk.Data.dll|[Microsoft.Xrm.Sdk.Data](/dotnet/api/microsoft.xrm.sdk.data)<br />[Microsoft.Xrm.Sdk.Data.CodeGen](/api/microsoft.xrm.sdk.data.codegen)<br />[Microsoft.Xrm.Sdk.Data.Converters](/dotnet/api/microsoft.xrm.sdk.data.converters)<br />[Microsoft.Xrm.Sdk.Data.Exceptions](/dotnet/api/microsoft.xrm.sdk.data.exceptions)<br />[Microsoft.Xrm.Sdk.Data.Expressions](/dotnet/api/microsoft.xrm.sdk.data.expressions)<br />[Microsoft.Xrm.Sdk.Data.Infra](/dotnet/api/microsoft.xrm.sdk.data.infra)<br />[Microsoft.Xrm.Sdk.Data.Mappings](/dotnet/api/microsoft.xrm.sdk.data.mappings)|

#### <a name="extend-outlook-client"></a>Outlook-client uitbreiden

Gebruik de volgende assembly om te communiceren met Microsoft Dynamics 365 voor Outlook en Microsoft Dynamics 365 voor Microsoft Office Outlook met offlinetoegang. 

Zie [Dynamics 365 Customer Engagement Developer Guide: Extend Dynamics 365 Customer Engagement for Outlook](/dynamics365/customer-engagement/developer/extend-customer-engagement-outlook) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Dynamics 365 Customer Engagement voor Outlook uitbreiden) voor meer informatie.

**NuGet-pakket**: [Microsoft.CrmSdk.Outlook](https://www.nuget.org/packages/Microsoft.CrmSdk.Outlook/)

|Assembly|Naamruimte|
|---------|---------|
|Microsoft.Crm.Outlook.Sdk.dll|[Microsoft.Crm.Outlook.Sdk](/dotnet/api/microsoft.crm.outlook.sdk)|



## <a name="community-tools-for-common-data-service-for-apps"></a>Communityhulpprogramma's voor Common Data Service for Apps

De community van Dynamics 365 maakt hulpprogramma's. Veel van de populairste hulpprogramma's worden gedistribueerd via [XrmToolBox](https://www.xrmtoolbox.com/). XrmToolBox is een Windows-toepassing die met Common Data Service for Apps is verbonden en hulpprogramma's biedt voor taken op het gebied van aanpassingen, configuraties en bewerkingen. De toepassing wordt geleverd met meer dan 30 invoegtoepassingen waarmee beheer-, aanpassings- of configuratietaken eenvoudiger worden en minder tijd in beslag nemen.

Hieronder vindt u een lijst met communityhulpprogramma's die via XrmToolBox worden geleverd die u kunt gebruiken in Common Data Service for Apps.

|Hulpprogramma  |Beschrijving  |
|---------|---------|
|[Attribute Manager](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)|Wordt gebruikt om het kenmerktype te verwijderen, te wijzigen of de naam hiervan te wijzigen.|
|[Early Bound Generator](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.EarlyBoundGenerator/)|Hiermee kunt u vroege gebonden entiteiten/optiesets/acties genereren. Hiervoor wordt CrmSvcUtil uit de SDK gebruikt en de opdrachtregel getoond die voor het maken van de klassen wordt gebruikt.|
|[Exporteren naar Excel](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|Hiermee kunt u eenvoudig records vanuit de geselecteerde weergave/fetchxml naar Excel exporteren.|
|[FetchXML Builder](https://www.xrmtoolbox.com/plugins/Cinteros.Xrm.FetchXmlBuilder/)|Hiermee kunt u FetchXml-query's maken en testen.|
|[Browser voor metagegevens](https://www.xrmtoolbox.com/plugins/MsCrmTools.MetadataBrowser/)|Hiermee kunt u bladeren door de metagegevens van uw Dynamics CRM-organisatie.|
|[Plugin Trace Viewer](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.PluginTraceViewer/)|Bekijk het traceringslogboek van de invoegtoepassing met eenvoudige filter- en weergaveopties.|
|[Hulpprogramma Gebruikersinstellingen](https://www.xrmtoolbox.com/plugins/MsCrmTools.UserSettingsUtility/)|Hiermee kunt u persoonlijke instellingen van gebruikers bulkgewijs beheren.|

> [!NOTE]
> Hulpprogramma's die door de community zijn gemaakt, worden niet ondersteund door Microsoft. Als u vragen of opmerkingen hebt over de communityhulpprogramma's, moet u contact opnemen met de uitgever van het hulpprogramma.
