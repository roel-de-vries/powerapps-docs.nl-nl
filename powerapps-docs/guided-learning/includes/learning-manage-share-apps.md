Het is fantastisch om apps te ontwikkelen voor uw eigen zakelijke behoeften, maar de werkelijke kracht van PowerApps schuilt in het delen van die apps met anderen. Nu u weet hoe u een app moet ontwikkelen, leert u in dit onderwerp hoe u die app kunt delen. U kunt een app delen met specifieke gebruikers of groepen of u kunt de app delen met uw hele organisatie. Wanneer u een app met andere personen deelt, kunnen zij de app uitvoeren vanuit Dynamics 365 in een browser of in PowerApps Mobile voor Windows, iOS of Android. Als u iemand bijdragerechten geeft, kan die persoon de app ook bijwerken.

## <a name="prepare-to-share-an-app"></a>Het delen van een app voorbereiden
Voordat u een app met iemand kunt delen, moet u de app opslaan in de cloud. Geef de app een duidelijke naam en beschrijving, zodat iedereen weet wat uw app doet en de app gemakkelijk uit een lijst is te kiezen. Klik of tik in PowerApps Studio op **Bestand** en voer een beschrijving in.

![App-beschrijving](./media/learning-manage-share-apps/app-description.png)

Houd er rekening mee dat alle wijzigingen die u in een gedeelde app aanbrengt, ook worden doorgevoerd bij degenen met wie u de app hebt gedeeld zodra u de wijzigingen opslaat. Dat kan prima zijn als u de app verbetert, maar kan ook van invloed zijn op anderen als u functies verwijdert of daar aanzienlijke wijzigingen in aanbrengt.

## <a name="share-an-app"></a>Een app delen
Op een app-tegel in web.powerapps.com klikt u op de knop met het beletselteken (. . .) en klikt u vervolgens op **Delen**.

![Een app delen vanuit web.powerapps.com](./media/learning-manage-share-apps/share-app.png)

Vanuit hier kunt u een app delen en tevens het versiebeheer voor apps bepalen, waarover meer in het volgende onderwerp. Geef aan met welke gebruikers en groepen u de app wilt delen en welke rol zij krijgen: **gebruiker** of **medewerker**. Klik of tik op **Opslaan**.

![Gebruikers en groepen selecteren](./media/learning-manage-share-apps/select-users.png)

Als u ervoor kiest om gebruikers via e-mail te informeren, ontvangt iedereen met wie u de app hebt gedeeld een e-mailbericht met een koppeling naar Dynamics 365. App-medewerkers ontvangen ook een koppeling naar web.powerapps.com.  Als iemand niet de koppeling naar Dynamics 365 volgt, wordt de app daar niet voor die persoon weergegeven. De app verschijnt in dat geval in AppSource, maar gebruikers moeten de app dan zelf aan Dynamics 365 toevoegen.

![App in Dynamics 365](./media/learning-manage-share-apps/dynamics-365.png)

## <a name="permissions-and-licensing"></a>Machtigingen en licenties
We gaan niet verder in op machtigingen en licenties, maar we willen het wel hebben over enkele basisbeginselen met betrekking tot delen:

* Gebruikers en medewerkers hebben machtigingen nodig voor alle gegevensverbindingen en gateways waarvan een gedeelde app gebruikmaakt. Sommige machtigingen zijn impliciet aan de app gekoppeld, maar andere moeten expliciet worden verleend.
* Als de app gebruikmaakt van Common Data Service voor Apps-entiteiten, moeten gebruikers en medewerkers toegang hebben tot de Common Data Service for Apps-database. Medewerkers hebben ook een PowerApps P2-licentie nodig als ze rechtstreeks met entiteiten werken.

Apps delen is eenvoudig en het is een uitstekende manier om een app die u handig vindt beschikbaar te stellen aan mensen in uw organisatie. In het volgende onderwerp leggen we uit hoe u kunt bepalen welke versie van een app actief is wanneer u de app gebruikt en deelt.

