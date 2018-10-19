## <a name="delegation"></a>Overdracht
Indien mogelijk, dragen PowerApps de filter- en sorteerbewerkingen over aan de gegevensbron en worden de resultaten op aanvraag weergegeven. Als u bijvoorbeeld een app start die een **[Galerie](../maker/canvas-apps/controls/control-gallery.md)**-besturingselement weergeeft dat is gevuld met gegevens, wordt in eerste instantie alleen de eerste reeks records naar het apparaat overgebracht. Als de gebruiker verder scrolt, worden extra gegevens naar de gegevensbron overgebracht. Het resultaat is een snellere start voor de app en toegang tot zeer grote gegevenssets.

Het overdragen is echter niet altijd mogelijk. Gegevensbronnen ondersteunen verschillende functies en operators als het om overdragen gaat. Als een volledige overdracht van een formule niet mogelijk is, wordt in de auteursomgeving het aandeel dat niet kan worden overgebracht, gemarkeerd met een waarschuwing. U kunt eventueel de formule aanpassen om functies en operators te vermijden die niet kunnen worden overgedragen.  De [overdrachtlijst](../maker/canvas-apps/delegation-list.md) bevat details over de gegevensbronnen en bewerkingen die kunnen worden overgedragen.

Als overdracht niet mogelijk is, haalt PowerApps slechts een kleine set records op om lokaal te bewerken. De filter- en sorteerfuncties werken dan op een beperkte set records. In de **[Galerie](../maker/canvas-apps/controls/control-gallery.md)** zijn dan niet alle gegevens beschikbaar, wat verwarrend kan zijn voor de gebruikers. 

Zie het [overdrachtoverzicht](../maker/canvas-apps/delegation-overview.md) voor meer informatie.

