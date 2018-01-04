Een van de grootste voordelen van PowerApps is dat u geen traditionele toepassingscode hoeft te schrijven: u hoeft dus geen ontwikkelaar te zijn om apps te maken! Maar u hebt wel een manier nodig om logica in een app op te nemen en om het navigeren, filteren, sorteren en andere functionaliteit van een app te regelen. Hier komt het gebruik van formules van pas. Als u Excel-formules hebt gebruikt, zal de manier waarop PowerApps werkt u bekend voorkomen. In dit onderwerp laten we een aantal basisformules voor tekstopmaak zien en behandelen we drie van de formules die PowerApps opneemt in de gegenereerde app. U krijgt een voorproefje van wat formules zoal kunnen doen. Vervolgens kijken we naar andere formules in de gegenereerde app en laten we zien hoe u uw eigen formules kunt schrijven.

## <a name="understanding-formulas-and-properties"></a>Over formules en eigenschappen
In het vorige onderwerp hebben we het veld Price opgenomen in de galerie van het bladerscherm, maar de prijs werd weergegeven als een gewoon getal zonder valutasymbool. Stel dat we een dollarteken willen toevoegen en de tekstkleur willen wijzigen afhankelijk van de prijs van het item (bijvoorbeeld rood als de prijs hoger is dan $ 5 en groen als dat niet zo is). De volgende afbeelding geeft een indruk van hoe dat eruitziet.

![Tekstopmaak voor kleur en valuta](./media/learning-spo-app-explore-formulas/text-formatting.png)

Laten we beginnen met de valuta-opmaak. Standaard haalt PowerApps voor elk item een waarde op voor de prijs, die is ingesteld als de **Text**-*eigenschap* van het label dat de prijs bevat.

![Standaardopmaak van prijs](./media/learning-spo-app-explore-formulas/price-default.png)

Als u het dollarteken als valutasymbool wilt toevoegen, klikt of tikt u op het label-besturingselement en stelt u in de formulebalk de eigenschap **Text** in voor deze formule.

![Valutanotatie van prijs](./media/learning-spo-app-explore-formulas/price-formatted.png)

De formule (`Text(Price, "[$-en-US]$ ##.00"`) maakt gebruik van de **Tekst**-*functie* om aan te geven hoe het getal moet worden opgemaakt. Dat lijkt veel op een Excel-formule, maar PowerApps-formules verwijzen naar besturingselementen en andere app-elementen in plaats van naar cellen in een werkblad. Als u eerst op een besturingselement en vervolgens op de vervolgkeuzelijst met eigenschappen klikt of tikt, wordt een lijst met eigenschappen weergegeven die relevant zijn voor het besturingselement. Hieronder ziet u bijvoorbeeld een gedeeltelijke lijst van de eigenschappen voor een label. Sommige eigenschappen zijn relevant voor een scala van besturingselementen en andere alleen maar voor een specifiek besturingselement.

![Eigenschappen instellen](./media/learning-spo-app-explore-formulas/properties.png)

Als u de kleur voorwaardelijk wilt opmaken op basis van de prijs, gebruikt u een formule als de volgende voor de eigenschap **Color** van het label: `If(Price > 5, Color.Red, Color.Green)`.

![Kleuropmaak van prijs](./media/learning-spo-app-explore-formulas/color-formatted.png)

## <a name="formulas-included-in-the-generated-app"></a>Formules die zijn opgenomen in de gegenereerde app
Nu u weet hoe formules worden gebruikt in combinatie met eigenschappen, gaan we drie voorbeelden bekijken van formules die PowerApps gebruikt in de gegenereerde app. De voorbeelden hebben allemaal betrekking op het bladerscherm en werken met de eigenschap OnSelect, die bepaalt wat er gebeurt wanneer een gebruiker op een app-besturingselement klikt of tikt.

* De eerste formule is gekoppeld aan het besturingselement **IconNewItem1**: ![pictogram Nieuw item](./media/learning-spo-app-explore-formulas/icon-add-item.png). U klikt of tikt op dit besturingselement om van het bladerscherm naar het scherm voor bewerken/maken te gaan en een item te maken. 
  
  * De formule is `NewForm(EditForm1);Navigate(EditScreen1, ScreenTransition.None)`
  * De formule *opent* eerst een nieuw bewerkingsformulier en vervolgens het scherm voor bewerken/maken zodat u een nieuw item kunt maken. Een waarde van `ScreenTransition.None` betekent dat er geen overgang tussen schermen is (zoals vervagen).
* De tweede formule is gekoppeld aan het besturingselement **IconSortUpDown1**: ![pictogram Galerie sorteren](./media/learning-spo-app-explore-formulas/icon-sort.png). U klikt of tikt op dit besturingselement om de lijst met items in de galerie van het bladerscherm te sorteren.
  
  * De formule is `UpdateContext({SortDescending1: !SortDescending1})`
  * De formule gebruikt `UpdateContext` voor het bijwerken van een *variabele* met de naam `SortDescending1`. De waarde van de variabele gaat heen en weer door op het besturingselement te klikken of te tikken. Dat maakt de galerie in dit scherm duidelijk hoe de items moeten worden gesorteerd (zie de video voor meer informatie). 
* De derde formule is gekoppeld aan het besturingselement **NextArrow1**: ![pijl Ga naar details](./media/learning-spo-app-explore-formulas/icon-arrow.png). U klikt of tikt op dit besturingselement om van het bladerscherm naar het detailscherm voor bewerken/maken te gaan.
  
  * De formule is `Navigate(DetailScreen1, ScreenTransition.None)`
  * De formule navigeert naar het detailscherm, ook deze keer zonder overgang.

Er zitten veel andere formules in de app, neem dus even de tijd om te klikken op besturingselementen en te zien welke formules voor diverse eigenschappen worden ingesteld.

## <a name="wrapping-it-all-up"></a>Ter afsluiting
Daarmee zijn we aan het eind gekomen van de verkenning van de gegenereerde app en van de schermen, besturingselementen, eigenschappen en formules die de werking en de mogelijkheden van de app bepalen. Als u alles gevolgd hebt, weet u nu beter hoe een gegenereerde app werkt. En met die kennis kunt u nu uw eigen apps gaan maken. 

Voordat we verdergaan naar de volgende sectie, keren we even terug naar SharePoint om u te laten zien hoe de app nu is geïntegreerd met de lijst. Zoals u ziet, functioneert **FlooringApp** nu als een *weergave* van de lijst en u start de app door op **Openen** te klikken. Dat biedt een eenvoudige manier om uw lijsten te beheren met een prettige en gepersonaliseerde ervaring.

![App als weergave van Sharepoint-lijst](./media/learning-spo-app-explore-formulas/list-view.png)

Nu u de app-sectie van SharePoint hebt doorlopen, kunt u voor het vervolg kiezen uit twee mogelijkheden:

* [Apps beheren](https://docs.microsoft.com/powerapps/guided-learning/manage-apps#step-1)
* [Een app maken en aanpassen vanuit de Common Data Service](https://docs.microsoft.com/powerapps/guided-learning/create-app-cds#step-1)

In de sectie over beheren ziet u hoe u apps kunt delen en het versiebeleid kunt bepalen. Bovendien hebben we het over omgevingen, die kunnen worden gedefinieerd als containers voor apps, gegevens en andere bronnen. Het is voor iedereen raadzeem om de beheersectie op een bepaald moment door te nemen, maar ook de sectie over de Common Data Service bevat nuttige informatie, met meer app-aanpassingen. 

