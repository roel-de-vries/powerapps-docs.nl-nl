---
title: Gegevens importeren en exporteren vanuit Common Data Service voor Apps
description: Gegevens massaal importeren en exporteren vanuit Excel- of CSV-bestanden naar entiteiten in Common Data Service voor Apps met behulp van de functionaliteit voor het ophalen van gegevens uit Excel en voor het exporteren van gegevens
author: sabinn-msft
ms.service: powerapps
ms.topic: conceptual
ms.component: cds
ms.date: 05/14/2018
ms.author: sabinn
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-or-export-data-from-common-data-service-for-apps"></a>Gegevens importeren en exporteren vanuit Common Data Service voor Apps

Als u gegevens massaal wilt importeren en exporteren vanuit Microsoft Excel- of CSV-bestanden, gebruikt u de functies voor het ophalen van gegevens uit Excel en voor het exporteren van gegevens voor bijgewerkte Common Data Service voor Apps-omgevingen.

Er zijn twee manieren waarop u bestanden kunt importeren in entiteiten vanuit Excel- of CSV-bestanden.

## <a name="option-1-import-by-creating-and-modifying-a-file-template"></a>Optie 1: importeren door een bestandsjabloon te maken en aan te passen

Elke entiteit heeft vereiste velden die in uw invoerbestand aanwezig moeten zijn. U wordt aangeraden een sjabloon te maken. Exporteer eerst gegevens uit de entiteit. Gebruik hetzelfde bestand (gewijzigd met uw gegevens) om gegevens te importeren in de entiteit. Deze sjabloon bespaart tijd en moeite. U hoeft geen rekening te houden met de vereiste velden voor elke entiteit.

1. Bereid de bestandssjabloon voor.

    a. Exporteer de entiteitsgegevens naar het CVS-bestand. Voer de stappen in **Gegevens exporteren naar CSV** uit.  
    b. Definieer een plan om ervoor te zorgen dat de gegevens uniek zijn. Gebruik **Primaire sleutels** of **Alternatieve sleutels**.  
    c. Raadpleeg het volgende gedeelte voor instructies om ervoor te zorgen dat de gegevens uniek zijn voordat u ze in een entiteit importeert. 

1. Wijzig het bestand met uw gegevens.

    - Kopieer gegevens vanuit uw Excel- of CSV-bestand in de sjabloon die u zojuist hebt gemaakt.

1. Importeer het bestand.  
    a. Vouw in [powerapps.com](https://web.powerapps.com/) de sectie **Gegevens** uit. Selecteer **Entiteiten** in het linkernavigatievenster.  
    b. Selecteer de entiteit waarnaar u gegevens wilt importeren.  
    c. Selecteer de drie puntjes of het menu bovenaan. Selecteer **Gegevens ophalen**. Selecteer **Gegevens ophalen uit Excel**.  

    > [!NOTE]
    > Als u gegevens wilt importeren in meer dan één entiteit, selecteert u in het bovenste menu **Gegevens ophalen**. Selecteer **Gegevens ophalen uit Excel**. Vervolgens kunt u meerdere entiteiten kiezen en **Volgende** selecteren.

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van het importeren van gegevens naar een entiteit **Account**](./media/data-platform-import-export/import-data-to-account.png)

    d. Op het scherm **Gegevens importeren** geeft u aan of u gegevens uit een Excel- of een CSV-bestand wilt importeren.  
    e. Selecteer **Uploaden**.  
    f. Kies uw bestand . Volg de aanwijzingen om uw bestand te uploaden.  

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van het uploaden van een bestand naar een entiteit **Account**](./media/data-platform-import-export/upload-account.png)

    g. Als het bestand is geüpload en de **Toewijzingsstatus** groen is, selecteert u **Importeren** in de rechterbovenhoek. Raadpleeg het volgende gedeelte om naar eventuele toewijzingfouten te navigeren en deze op te lossen.  

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van een succesvolle **toewijzingsstatus** en de knop **Importeren**](./media/data-platform-import-export/success-map-imp.png)

    h. Zodra het importeren met succes is voltooid, ziet u het totale aantal invoegingen en bijwerkingen.  

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van een succesvolle import waarbij het aantal invoegingen en bijwerkingen wordt getoond](./media/data-platform-import-export/success-imp-insert.png)

    > [!NOTE]
    > Gebruik de logica van Upsert (bijwerken of invoegen) om de record bij te werken, als deze al bestaat, of om een nieuwe record in te voegen.

## <a name="option-2-import-by-bringing-your-own-source-file"></a>Optie 2: importeren door uw eigen bronbestand te gebruiken

Als u een gevorderde gebruiker bent en weet wat de vereiste velden voor een bepaalde entiteit zijn voor Common Data Service voor Apps, definieer dan uw eigen Excel- of CSV-bronbestand. Voer de stappen **Het bestand importeren** uit.

## <a name="navigate-mapping-errors"></a>Naar toewijzingsfouten navigeren

Als u toewijzingsfouten krijgt nadat u uw bestand hebt geüpload, selecteert u **Toewijzingsstatus**. Voer de volgende stappen uit om de veldtoewijzingsfouten te controleren en te herstellen.

1. Gebruik het vervolgkeuzemenu rechts onder **Weergeven** om door **Niet-toegewezen velden**, **Velden met fout** of **Vereiste velden** te navigeren.

    > [!TIP]
    > Afhankelijk van de vraag of u een waarschuwing of een fout krijgt, inspecteert u **Niet-toegewezen velden** of **Velden met fout** via het vervolgkeuzemenu in **Veldtoewijzingen**.

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van een gedeeltelijke overeenkomst als gevolg van waarschuwingen met veldtoewijzingen](./media/data-platform-import-export/partial-match.png)

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van problemen met navigeren door veldtoewijzingen](./media/data-platform-import-export/navigate-mappings.png)

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van het controleren en herstellen van waarschuwingen met veldtoewijzingen](./media/data-platform-import-export/inspect-warnings.png)

2. Nadat u alle fouten en waarschuwingen hebt hersteld, selecteert u **Wijzigingen opslaan** in de rechterbovenhoek. U gaat naar het scherm **Gegevens importeren** terug.
3. Als de kolom **Toewijzingsstatus** **Voltooid** in groen bevat, selecteert u **Importeren** in de rechterbovenhoek.
4. Als u het bericht **De importbewerking is geslaagd** krijgt, wordt het totale aantal invoegingen en bijwerkingen getoond.

## <a name="ensure-uniqueness-when-you-import-data-into-an-entity-from-excel-or-csv"></a>Zorgen voor uniciteit wanneer u gegevens importeert in een entiteit vanuit Excel of CSV

In Common Data Service voor Apps-entiteiten wordt een primaire sleutel gebruikt als unieke identificatie voor records in een entiteitstabel van Common Data Service. De primaire sleutel voor een Common Data Service-entiteit is een GUID (Globally Unique Identifier). De primaire sleutel vormt de standaardbasis voor recordidentificatie. Gegevensbewerkingen, zoals het importeren van gegevens in Common Data Service-entiteiten, gebruiken de primaire standaardsleutels.

Voorbeeld:  
De primaire sleutel voor een **Account**-entiteit is **accountid**.

   > [!div class="mx-imgBorder"] 
   > ![Voorbeeldexportbestand van een entiteit **Account** die **accountid** als de primaire sleutel bevat](./media/data-platform-import-export/export-pk.png)

Soms werkt een primaire sleutel niet wanneer u gegevens vanuit een externe bron integreert. Gebruik Common Data Service om alternatieve sleutels te definiëren die een unieke identificatie vormen voor een record in plaats van de primaire sleutel.

Voorbeeld:  
Voor een **Account**-entiteit moet u **transactioncurrencyid** als alternatieve sleutel instellen met behulp van een op een natuurlijke sleutelgebaseerde identificatie. Gebruik bijvoorbeeld **Euro** in plaats van de eerder weergegeven GUID-waarde **88c6c893-5b45-e811-a953-000d3a33bcb9**. U kunt ook **valutasymbool** of **valutanaam** als sleutels kiezen.

   > [!div class="mx-imgBorder"] 
   > ![Voorbeeld van het maken van een alternatieve sleutel in een entiteit **Valuta**](./media/data-platform-import-export/create-ak.png)

   > [!div class="mx-imgBorder"] 
   > ![Voorbeeldexportbestand van een entiteit **Account** die **valutanaam** als een natuurlijke sleutel bevat](./media/data-platform-import-export/export-nk.png)

Gebruikers kunnen primaire sleutels nog steeds als id's gebruiken nadat ze alternatieve sleutels hebben opgegeven. In het vorige voorbeeld is het eerste bestand nog steeds geldig als GUID's geldige gegevens zijn.

## <a name="export-data-to-csv"></a>Gegevens exporteren naar CSV

U kunt een eenmalige gegevensexport uitvoeren vanuit een standaardentiteit of een aangepaste entiteit. Ook kunt u gegevens vanuit meerdere entiteiten tegelijk exporteren. Als u de gegevens vanuit meerdere entiteiten exporteert, wordt elke entiteit naar het eigen Microsoft CSV-bestand geëxporteerd.

1. Vouw in [powerapps.com](https://web.powerapps.com/) de sectie **Gegevens** uit. Selecteer **Entiteiten** in het linkernavigatievenster.
1. Selecteer de entiteit waaruit u gegevens wilt exporteren.
1. Selecteer de drie puntjes of het menu bovenaan. Selecteer **Exporteren**. Selecteer **Gegevens**.

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeld van het exporteren van gegevens vanuit een entiteit **Account**](./media/data-platform-import-export/export-account.png)

    > [!NOTE]
    > Als u gegevens vanuit meerdere entiteiten wilt exporteren, selecteert u in het bovenste menu **Exporteren**. Selecteer **Gegevens**. U kunt meerdere entiteiten kiezen.

1. Nadat de export met succes is voltooid, kunt u **Geëxporteerde gegevens downloaden** selecteren. Deze download biedt een koppeling naar het downloadbare CSV-bestand.

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeldexport dat een succesvolle export met een koppeling naar het downloadbare bestand toont](./media/data-platform-import-export/export-success.png)

## <a name="unsupported-data-types"></a>Niet-ondersteunde gegevenstypen

De volgende gegevenstypen worden momenteel niet ondersteund.

- Tijdzone
- Optieset voor meervoudige selectie
- Afbeelding
