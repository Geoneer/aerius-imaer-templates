Forked om Landbouw Emissie bestanden vanuit QGIS data layers om te zetten naar Aerius Input bestanden. 

Inleiding
---------
Valide IMAER-gml genereren gaat vrij eenvoudig met behulp van Templates.
Tijdens de IMAER-Connect masterclass (dd. 29 september en 2 oktober 2015)
zijn door de deelnemers templates gemaakt voor verschillende onderdelen van
het IMAER datamodel.

Deze templates zijn daarna nog verder bewerkt door Marco Duiker (OpenGeoGroep)
om ze meer uniform te maken en aan te passen voor aansturing middels data uit
een CSV bestand.

Voorwaarden voor gebruik
------------------------
Voor het gebruik van de templates is Python 2.x (tenminste Python 2.5, aanbevolen Python 2.7)
en de Jinja2 python module nodig. Deze laatste kan worden geinstallerd mbv easy_install.
Python 3.x is NIET geschikt.

Verder is het van belang enige vaardigheid met de commandoregel te hebben.

Gebruik
-------
Elk mapje bevat een template, data in de vorm van een example.csv bestand en een scriptje
(run_me.py) dat beide samenvoegt tot valide gml. Verder bevat elk mapje het bestand 
result.gml dat is gegenereerd met bovengenoemde onderdelen. 

Probeer eerst het result.gml te reproduceren om er zeker van te zijn dat alles goed werkt.
Tik daartoe in op de commandoregel: 
    python run_me.py >mijnresultaat.gml
Belangrijk daarbij is dat het commando python in het zoekpad (PATH) staat. Verder moet ook 
run_me.py worden gevonden. Navigeer daartoe met behulp van de commandoregel naar het mapje
waarin run_me.py is opgenomen. Dit kan met behulp van het commando:
    cd pad/naar/het/mapje/waarin/run_me/staat

Als alles goed is gegaan is mijnresultaat.gml nu gelijk aan result.gml.

Pas daarna het csv bestand aan met eigen data.

Bij het gebruik van AERIUS-Connect is het mogelijk meerdere gml-bestanden voor 1 
berekening mee te geven. Daarom is het niet nodig om bij een situatie met meerdere typen
emissiebronnen de gml-bestanden gegenereerd met verschillende templates handmatig samen 
te voegen.

Aanpassen van templates
-----------------------
Niet alle opgenomen templates gebruiken alle onderdelen van het IMAER-datamodel. Indien
u onderdelen wilt toevoegen (of een geheel eigen template wilt maken) dient u de volgende 
bestanden aan te passen:

    feature_members_template.gml
    Voeg hierin de missende onderdelen toe conform het IMAER datamodel.

    run_me.py
    Zorg ervoor dat de missende onderdelen die u heeft toegevoegd aan 
    feature_members_template.gml hier ook worden doorgegeven aan het
    template

    example.csv
    Zorg ervoor dat er ook data is opgenomen voor de missende onderdelen 
    die u heeft toegevoegd aan feature_members_template.gml

Nadere toelichting
------------------
In elk mapje dat een template bevat zijn ook opgenomen:
    base_template.gml
    gml_templating_lib
Die zijn in elk mapje gelijk, en ook gelijk aan hetgeen in base_folder staat. 


