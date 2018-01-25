## <a name="delegation"></a>Delegering
Indien mogelijk worden filter- en sorteerbewerkingen door PowerApps gedelegeerd naar de gegevensbron, waarna de resultaten op aanvraag per pagina worden weergegeven. Als u bijvoorbeeld een app start waarin een besturingselement **[Galerie](../controls/control-gallery.md)** wordt weergegeven met daarin verschillende gegevens, wordt in eerste instantie alleen de eerste set met records overgebracht naar het apparaat. Als de gebruiker gaat scrollen, worden er aanvullende gegevens opgehaald uit de gegevensbron. Het resultaat is een snellere starttijd voor de app en toegang tot zeer grote gegevenssets.

Delegering is echter niet altijd mogelijk. Het verschilt per gegevensbron welke functies en operatoren ze ondersteunen voor delegering. Als volledige delegering van een formule niet mogelijk is, wordt er in de ontwerpomgeving een waarschuwing weergegeven bij het deel dat niet kan worden gedelegeerd. Een oplossing is dan om de formule zo aan te passen dat deze alleen functies en operatoren bevat die kunnen worden gedelegeerd.  In deze [lijst](../delegation-list.md) ziet u welke gegevensbronnen en bewerkingen kunnen worden gedelegeerd.

Als delegering niet mogelijk is, wordt er door PowerApps slechts een klein aantal records opgehaald om lokaal mee te werken. De filter- en sorteerfuncties worden dan toegepast op een beperkte set records. De inhoud van het besturingselement **[Galerie](../controls/control-gallery.md)** is dan mogelijk niet volledig, wat verwarrend kan zijn voor gebruikers. 

Zie [Overzicht van delegeren](../delegation-overview.md) voor meer informatie.

