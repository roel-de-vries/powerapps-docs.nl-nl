---
title: Aangepaste besturingselementen voor gegevensvisualisaties in modelgestuurde apps gebruiken in PowerApps | MicrosoftDocs
description: Lees hoe u aangepaste besturingselementen voor velden gebruikt
ms.custom: ''
ms.date: 06/07/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 0d6064cd-4d38-4fc2-a564-735cb453a4b2
caps.latest.revision: 8
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="tutorial-use-custom-controls-for-model-driven-app-data-visualizations"></a>Zelfstudie: Aangepaste besturingselementen voor gegevensvisualisaties in modelgestuurde apps gebruiken in PowerApps

In deze zelfstudie leert u hoe u een aangepast besturingselement voor een veld configureert. 

Met aangepaste besturingselementen kunt u de onderdelen van de appgebruikersinterface, zoals een veld dat of weergave die traditioneel tekst bevat, transformeren tot visualisaties. Voor velden, formulieren, dashboards, weergaven en rasters kunnen aangepaste besturingselementen worden geconfigureerd. Er kan bijvoorbeeld een schuifregelaar worden geconfigureerd voor een getalveld.

   > [!div class="mx-imgBorder"] 
   > ![Aangepast besturingselement schuifregelaar](media/slider-control.PNG "Besturingselement schuifregelaar voor een veld")

En voor een weergave kan het bewerkbare raster worden geconfigureerd. 

   > [!div class="mx-imgBorder"] 
   > ![Besturingselement bewerkbaar raster](media/editable-grid-example.png)

U kunt één type aangepast besturingselement instellen dat in de webbrowserclient wordt weergegeven terwijl een ander aangepast besturingselement wordt weergegeven in uw Dynamics 365-app voor telefoons of tablets. U kunt bijvoorbeeld een aangepast besturingselement voor het invoer van getallen gebruiken voor een veld in webbrowserclients en een aangepast besturingselement met een schuifregelaar voor de telefoonapp. Als de aanpassing is gepubliceerd, kunnen gebruikers het besturingselement bewerken en de waarde wijzigen, zoals het besturingselement verschuiven met het aangepaste besturingselement van de lineaire schuifregelaar. Wijzigingen worden automatisch opgeslagen wanneer het formulier wordt gesloten net zoals wanneer de gebruiker een traditioneel veld op een formulier wijzigt.  
  
## <a name="use-a-custom-control-to-add-visualizations-to-a-field"></a>Een aangepast besturingselement gebruiken om visualisaties aan een veld toe te voegen  
 Met de stappen in deze procedure wijzigt u het standaardlabel en het tekstvakveld van het veld **Budgetbedrag** in het aangepaste besturingselement met schuifregelaar voor de entiteit Verkoopkans. U kunt vergelijkbare stappen gebruiken om een bestaand veld te vervangen door een aangepast besturingselement of een aangepast besturingselement voor een aangepast veld configureren.  
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**.  
  
2.  Open een formulier zoals het **hoofdformulier** voor de entiteit Verkoopkans. 
  
3.  Dubbelklik in de formuliereneditor op het veld waaraan u een aangepast besturingselement wilt toevoegen, zoals het veld **Budgetbedrag** op het hoofdformulier voor verkoopkansen. U kunt ook een aangepast veld maken. 
  
4.  Selecteer op de pagina **Veldeigenschappen** het tabblad **Besturingselementen** en selecteer vervolgens **Besturingselement toevoegen**.  
  
5.  Selecteer op de pagina Besturingselement toevoegen het besturingselement dat u wilt gebruiken, zoals het besturingselement **Lineaire schuifregelaar** en selecteer vervolgens **Toevoegen**.  

   > [!div class="mx-imgBorder"] 
   > ![Besturingselement lineaire schuifregelaar toevoegen](media/add-slider.PNG "Besturingselement lineaire schuifregelaar toevoegen")  
  
6.  Kies de client waarin u het besturingselement wilt weergeven.  
  
    - **Web**. Als u het aangepaste besturingselement in elke webbrowser beschikbaar wilt maken, selecteert u de optie **Web** naast het besturingselement. Houd er rekening mee dat door het instellen van de optie **Web** het besturingselement ook wordt weergegeven in webbrowsers op pc's, Macs en mobiele apparaten.  
  
    - **Telefoonnummer**. Als u het aangepaste besturingselement beschikbaar wilt maken op telefoons met Dynamics 365 for phones, selecteert u de optie **Telefoon** naast het besturingselement.  
  
    - **Tablet**. Als u het aangepaste besturingselement beschikbaar wilt maken op tablets met Dynamics 365 for tablets, selecteert u de optie **Tablet** naast het besturingselement.  
  
   > [!div class="mx-imgBorder"] 
   > ![De clientapps kiezen voor het weergeven van het aangepaste besturingselement](media/choose-client.png "De clientapps kiezen voor het weergeven van het aangepaste besturingselement")  
  
7.  Selecteer het potloodpictogram ![Pictogram Eigenschap aangepaste besturingselement bewerken](media/ccf-pencil-icon.png "Pictogram Eigenschap aangepaste besturingselement bewerken") naast **Min**, **Max** en **Stap**, stel de hieronder beschreven eigenschapoptie in en selecteer vervolgens **OK**.  
  
   > [!div class="mx-imgBorder"] 
   > ![Eigenschappen aangepast besturingselement toevoegen](media/ccf-add-properties.png "Eigenschappen aangepast besturingselement toevoegen")
  
   - **Min**. Stel de minimale geaccepteerde waarde in. U kunt hieraan een statische waarde binden die u invoert of de waarde binden aan een bestaand veld. In dit voorbeeld is **Binden aan een statische waarde** **Valuta** en is de minimumwaarde die kan worden ingevoerd *Nul*.  
  
       - **Binden aan een statische waarde**. Selecteer het gegevenstype, zoals een geheel getal (Whole.None) valuta, drijvende komma (FP) of decimalen. Vervolgens voert u een getal in dat de minimale geaccepteerde waarde voor het veld vertegenwoordigt.  
  
       - **Aan waarden voor een veld binden**. Selecteer een veld in de lijst die wordt gebruikt als de minimale geaccepteerde waarde.  
  
   - **Max**. Stel de maximale waarde voor het veld in. Net als bij de minimale waarde kunt u een statische waarde binden die u invoert of de waarde binden aan een bestaand veld zoals eerder is beschreven. In dit voorbeeld is **Binden aan een statische waarde** **Valuta** en is de maximumwaarde die kan worden ingevoerd **1 miljard**.  
  
   - **Stap**. Dit geeft de eenheid weer om te verhogen of te verlagen bij het optellen of aftrekken van de huidige waarde. Selecteer voor budgetbedrag bijvoorbeeld 100 dollar voor toename/afname.  
  
   - **Standaardbesturingselement verbergen**. Als u deze optie selecteert, wordt het besturingselement verborgen zodat het besturingselement en de gegevens niet zichtbaar zijn in clients die het aangepaste besturingselement niet ondersteunen. De klassieke Dynamics 365-webclient ondersteunt de meeste aangepaste besturingselementen niet. Standaard is deze optie niet geselecteerd en geeft de klassieke Dynamics 365-webclient het standaard, gewoonlijk op tekst gebaseerde besturingselement weer.  
  
       > [!NOTE]
       >  Het standaardbesturingselement wordt aangeduid met **(standaard)** na de besturingselementnaam.  
       >   
       > > [!div class="mx-imgBorder"] 
       > > ![Standaardbesturingselement](media/default-control.png "Standaardbesturingselement")  
  
8.  Selecteer **OK** om de pagina **Veldeigenschappen** te sluiten.  
  
9. Selecteer om de aanpassing te activeren de optie **Opslaan** op het entiteitformulier en selecteer vervolgens **Publiceren**.  
  
10. Selecteer **Opslaan en sluiten** om de formuliereneditor te sluiten.  
  
### <a name="see-the-custom-control-in-action"></a>Bekijk het aangepaste besturingselement in actie  
 Open een record die het veld met het aangepaste besturingselement bevat, zoals het verkoopkansformulier uit het eerdere voorbeeld, en bekijk hoe het veld is gewijzigd.  
  
   > [!div class="mx-imgBorder"] 
   > ![Besturingselement met schuifregelaar weergegeven op formulier](media/slider-control.PNG "Besturingselement met schuifregelaar weergegeven op formulier")  
  
 Het veld wordt nu weergegeven als een besturingselement met schuifregelaar in plaats van als tekstveld. 

## <a name="use-the-editable-grid-control-on-a-view-or-sub-grid"></a>Het besturingselement voor een bewerkbaar raster gebruiken in een weergave of subraster

Met bewerkbare rasters kunnen gebruikers de opmaak direct inline bewerken vanuit weergaven en subrasters wanneer zij een webapp, telefoon of tablet gebruiken. Meer informatie: [Rasters (lijsten) bewerkbaar maken met het aangepaste besturingselement Bewerkbare rasters](make-grids-lists-editable-custom-control.md) 
  
## <a name="next-steps"></a>Volgende stappen  
[Velden maken en bewerken](../common-data-service/create-edit-fields.md)
