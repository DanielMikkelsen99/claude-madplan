Jeg vil have en automatisk madplan til min husstand. Du skal lave en app og en planlagt opgave ud fra den vedhæftede fil madplan-app.html og prompten til den planlagte opgave, som står sidst i denne besked.

1. Spørg mig først, i én samlet besked, om: antal voksne og børn og børnenes portionsstørrelse, ugens budget og hvor meget af det der går til olie og krydderier, allergener, proteinmål eller andet kostmål, ønsker til retterne, hvilke butikker der skal sammenlignes, og hvilket tidspunkt fredag opgaven skal køre. Vent på mine svar.

2. Lav appen. Udgiv den vedhæftede fil præcis, som den er, som en artifact med titlen "Ugens madplan", med filen som index.html. Ret ikke koden, og lav ikke din egen version. Giv derefter artifacten capability db med declare_capabilities: {"db": {}}. Notér artifactens link.

3. Test, at en planlagt opgave kan skrive til appen: Opret en engangsopgave om 3 minutter, der indlæser værktøjet ArtifactData med ToolSearch og kalder det med action "set", url = appens link, collection "system", doc_id "ping" og data {"ok":true}. I planlagte kørsler er det ArtifactData, der skriver til appens database. Vent, til kørslen er færdig, læs dokumentet, og slet det. Lykkes det ikke, så stop og fortæl mig præcis, hvad fejlen er.

4. Lav den planlagte opgave "Ugentlig madplan". Den skal køre hver fredag på det tidspunkt, jeg har valgt, i min tidszone. Beder opgavens kørsler om godkendelse, så sig til, at jeg skal slå automatisk godkendelse til i opgavens indstillinger. Brug prompten til den planlagte opgave, og erstat alle felter i <<dobbelte vinkler>> med mine svar og appens link. Bevar resten af ordlyden.

5. Kør opgaven én gang nu, så jeg får en plan med det samme. Er der mere end to dage til næste søndag, skal planen gælde resten af denne uge i stedet, med start på den seneste søndag og kun de resterende aftener, og kravet om 7 dage gælder ikke for denne ene kørsel.

6. Giv mig til sidst linket til appen, og fortæl mig, hvordan jeg deler den med min husstand. Sig, hvis noget ikke virkede.
