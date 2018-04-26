---
title: Multimediabestanden insluiten in een app en uploaden | Microsoft Docs
description: Multimediabestanden weergeven in een app en ze uploaden naar een gegevensbron
documentationcenter: ''
author: karthik-1
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 07/12/2017
ms.author: sharik
ms.openlocfilehash: 7ee752f5606f10f66ad7c8dc49e05233225c0a89
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="using-multimedia-files-in-powerapps"></a>Multimediabestanden gebruiken in PowerApps
In dit onderwerp wordt beschreven hoe u multimediabestanden insluit in uw app, hoe u pentekeningen uploadt naar een gegevensbron en hoe u afbeeldingen van een gegevensbron weergeeft in uw app. De gegevensbron die in dit onderwerp wordt gebruikt is een Excel-bestand in OneDrive voor Bedrijven.

## <a name="prerequisites"></a>Vereisten
[Registreer u](../signup-for-powerapps.md) voor PowerApps en [installeer](http://aka.ms/powerappsinstall) PowerApps. Meld u bij het openen van PowerApps aan met dezelfde referenties die u hebt gebruikt om u te registreren.

## <a name="add-media-from-a-file-or-the-cloud"></a>Media uit een bestand of de cloud toevoegen
U kunt kiezen welk type mediabestand u toevoegt (bijvoorbeeld afbeeldingen, video's of audio).

1. Op het tabblad **Inhoud** selecteert u **Media**.

2. Onder **Media** selecteert u **Afbeeldingen**, **Video's** of **Audio**. Daarna selecteert u **Bladeren**:

    ![Door media bladeren][1]

3. Selecteer het bestand dat u wilt toevoegen en selecteer vervolgens **Openen**.

    De map **Afbeeldingen** op uw computer wordt geopend. U kunt een afbeelding uit de map selecteren of naar een andere map navigeren.

4. Wanneer u klaar bent met het toevoegen van bestanden drukt u op ESC om terug te keren naar de standaardwerkruimte.

5. Op het tabblad **Invoegen** selecteert u **Media** en daarna selecteert u **Afbeelding**, **Video** of **Audio**:

    ![Mediatype selecteren][8]

6. Als u een afbeeldingsbesturingselement hebt toegevoegd, stelt u de eigenschap **[Image](controls/properties-visual.md)** in op het bestand dat u hebt toegevoegd:  

    ![De afbeeldingseigenschap instellen](./media/add-images-pictures-audio-video/imageproperty.png)

    > [!NOTE]
> Geef alleen de bestandsnaam op, zonder extensie, tussen enkele aanhalingstekens.

7. Als u een video- of audiobesturingselement hebt toegevoegd, stelt u de eigenschap **Media** in op het bestand dat u hebt toegevoegd:  

    ![De media-eigenschap instellen](./media/add-images-pictures-audio-video/mediaproperty.png)

    > [!NOTE]
> U kunt een YouTube-video afspelen door de eigenschap **Media** van een videobesturingselement in te stellen op de geschikte URL, tussen dubbele aanhalingstekens.

## <a name="add-media-from-azure-media-services"></a>Media toevoegen vanuit Azure Media Services
1. Upload en publiceer uw video-asset vanuit uw Azure Media Services-account via **AMS > Instellingen > Assets**.

2. Nadat de video is gepubliceerd, kopieert u de URL.

3. Voeg vanuit PowerApps het besturingselement **Video** toe vanuit **Invoegen > Media**.

4. Stel de eigenschap **Media** in op de URL die u hebt gekopieerd.

    Zoals in deze afbeelding wordt weergegeven, kunt u elke streaming-URL kiezen die wordt ondersteund door Azure Media Services:

    ![De media-eigenschap instellen](./media/add-images-pictures-audio-video/ams-with-powerapps.png)

## <a name="add-images-from-the-cloud-to-your-app"></a>Afbeeldingen uit de cloud toevoegen aan uw app
In dit scenario slaat u afbeeldingen op in een cloudopslagaccount (bij OneDrive voor Bedrijven). U gebruikt een Excel-tabel om het pad naar de afbeeldingen op te geven en u geeft de afbeeldingen weer in een galeriebesturingselement in uw app.

In dit scenario gebruikt u de map [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip), die ook enkele JPEG-bestanden bevat.

> [!NOTE]
> Het pad naar deze afbeeldingen in het Excel-bestand moet slash-tekens bevatten. Wanneer PowerApps afbeeldingspaden opslaat in een Excel-tabel, worden er backslash-tekens gebruikt. Als u afbeeldingspaden gebruikt uit een dergelijke tabel, dient u dus de slash-tekens in de paden in de Excel-tabel te vervangen door backslash-tekens. Anders worden de afbeeldingen niet weergegeven.  

1. Download eerst [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) en pak de map **Assets** uit naar uw cloudopslagaccount.

2. Wijzig de naam van de map **Assets** naar **Assets_images**.

3. Maak in een Excel-werkblad een tabel van één kolom en vul deze met de volgende gegevens:

    ![Tabel Jackets](./media/add-images-pictures-audio-video/jackets.png)

4. Noem de tabel **Jackets** en noem het Excel-bestand **Assets.xlsx**.

5. Voeg in uw app de tabel **Jackets** toe als gegevensbron.  

6. Voeg het besturingselement **Alleen afbeeldingen** toe (tabblad **Invoegen** > **Galerie**) en stel de eigenschap **Items** in op `Jackets`:  

    ![Eigenschap Items](./media/add-images-pictures-audio-video/items-jackets.png)

    De galerie wordt automatisch bijgewerkt met de afbeeldingen:  

    ![Afbeeldingen Jacket](./media/add-images-pictures-audio-video/images.png)

    Als u de eigenschap **Items** instelt, wordt de Excel-tabel automatisch bijgewerkt met een kolom met de naam **PowerAppsId**.

    Het pad naar een afbeelding kan in de Excel-tabel ook de URL naar een afbeelding zijn. Een voorbeeld hiervan is het voorbeeldbestand [Flooring Estimates](http://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx). U kunt het downloaden naar uw cloudopslagaccount. Voeg dan de tabel `FlooringEstimates` toe als gegevensbron in uw app en stel vervolgens het galeriebesturingselement in op `FlooringEstimates`. De galerie wordt automatisch bijgewerkt met de afbeeldingen.

## <a name="upload-pen-drawings-to-the-cloud"></a>Pentekeningen uploaden naar de cloud
In dit scenario leert u hoe u pentekeningen uploadt naar uw gegevensbron, OneDrive voor Bedrijven, en ontdekt u hoe de tekeningen daar worden opgeslagen.

1. In Excel voegt u **Afbeelding [image]** toe aan cel A1.

2. Volg de volgende stappen om een tabel te maken:    

   1. Selecteer cel A1.

   2. Selecteer **Tabel** op het lintmenu **Invoegen**.

   3. Selecteer in het dialoogvenster **Mijn tabel bevat veldnamen** en selecteer **OK**.

       ![Een tabel maken](./media/add-images-pictures-audio-video/create-table.png)

       Uw Excel-bestand is nu opgemaakt als tabel. Zie [Format the data as a table](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370) voor meer informatie over tabelopmaak in Excel.

   4. Noem de tabel **Drawings**:

       ![De naam van de tabel wijzigen naar Drawings](./media/add-images-pictures-audio-video/name-media-table.png)

3. Sla het Excel-bestand op in OneDrive voor Bedrijven met de naam **SavePen.xlsx**.

4. Maak in PowerApps een [lege app](get-started-create-from-blank.md).

5. Voeg in uw app het OneDrive voor Bedrijven-account toe als [gegevensbron](add-data-connection.md):

   1. Klik of tik op het tabblad **Weergeven** en tik of klik daarna op **Gegevensbronnen**.

       ![](./media/add-images-pictures-audio-video/choose-data-sources.png)

   2. Klik of tik op **Een gegevensbron toevoegen** en klik of tik daarna op **OneDrive voor Bedrijven**.

       ![](./media/add-images-pictures-audio-video/select-source.png)

   3. Klik of tik op **SavePen.xlsx**.

   4. Selecteer de tabel **Drawings** en tik of klik op **Verbinden**.

       ![Verbinden](./media/add-images-pictures-audio-video/savepen.png)  

       Nu wordt de tabel Drawings vermeld als gegevensbron.

6. Selecteer op het tabblad **Invoegen** de optie **Tekst** en selecteer daarna **Peninvoer**.

7. Noem het nieuwe besturingselement **MyPen**:  

    ![Naam wijzigen](./media/add-images-pictures-audio-video/rename-mypen.png)

8. Voeg op het tabblad **Invoegen** het besturingselement **Knop** toe en stel de eigenschap **OnSelect** in op deze formule:

    **Patch(Tekeningen, Standaard(Tekeningen), {Afbeelding:MyPen.Image})**

9. Voeg het besturingselement **Afbeeldingengalerie** toe (tabblad **Invoegen** > **Galerie**) en stel de eigenschap **Items** in op `Drawings`. De eigenschap **Image** van het galeriebesturingselement wordt automatisch ingesteld op `ThisItem.Image`.

    Deel de besturingselementen zodanig in dat uw scherm er als volgt uitziet:  

    ![Voorbeeldscherm](./media/add-images-pictures-audio-video/screen.png)

10. Druk op F5 of selecteer Voorbeeld ( ![Knop Voorbeeld](./media/add-images-pictures-audio-video/preview.png) ).

11. Teken iets in MyPen en selecteer de knop.

    In de eerste afbeelding van het galeriebesturingselement wordt weergegeven wat u hebt getekend.

12. Voeg nog iets toe aan uw tekening en selecteer de knop.

    In de tweede afbeelding van het galeriebesturingselement wordt weergegeven wat u hebt getekend.

13. Sluit het voorbeeldvenster door op ESC te drukken.

    In uw cloudopslagaccount is automatisch de map **SavePen_images** gemaakt. Deze map bevat uw opgeslagen afbeeldingen met id's als bestandsnaam. Als u de map wilt bekijken, moet u mogelijk het browservenster vernieuwen door bijvoorbeeld op F5 te drukken.

    In **SavePen.xlsx** staat in de kolom **Afbeelding** het pad naar de nieuwe afbeeldingen.

### <a name="known-limitations"></a>Bekende beperkingen
[Lees deze beperkingen door](connections/cloud-storage-blob-connections.md#known-limitations) voor informatie over het delen van Excel-gegevens binnen uw organisatie.

## <a name="for-more-information"></a>Voor meer informatie
Test uw apps op verschillende platforms, waaronder in [een browservenster](https://home.dynamics.com/) en op een telefoon.

Zie de [tips van professionals over het vastleggen van afbeeldingen](https://powerapps.microsoft.com/blog/image-capture-pro-tips/) en de informatie over [aangepaste connectors voor het uploaden van de afbeelding](https://powerapps.microsoft.com/blog/custom-api-for-image-upload/) voor meer informatie over geavanceerde scenario's waarbij multimedia rechtstreeks moeten worden geüpload naar een andere gegevensbron.

U kunt bestanden ook uploaden naar een gegevensbron met de [Patch](functions/function-patch.md)-functie.

[1]: ./media/add-images-pictures-audio-video/add-image-video-audio-file.png
[3]: ./media/add-images-pictures-audio-video/add-intro-sound.png
[4]: ./media/add-images-pictures-audio-video/add-picture.png
[5]: ./media/add-images-pictures-audio-video/camera-gallery.png
[6]: ./media/add-images-pictures-audio-video/audio-gallery.png
[7]: ./media/add-images-pictures-audio-video/pen-gallery.png
[8]: ./media/add-images-pictures-audio-video/mediaoptions.png
[9]: ./media/add-images-pictures-audio-video/imageproperty.png
[10]: ./media/add-images-pictures-audio-video/mediaproperty.png
[11]: ./media/add-images-pictures-audio-video/renamecamera.png
