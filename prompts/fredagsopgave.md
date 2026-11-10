Lav ugens madplan, indkøbsliste og fulde opskrifter på dansk til førstkommende søndag, hvor der handles ind for hele ugen, og læg planen i appen Ugens madplan. Opgaven kører automatisk, så stil ingen spørgsmål. Send hele resultatet med SendUserMessage, så det kan læses direkte. Del det gerne op i flere beskeder, så ingen opskrifter bliver forkortet eller udeladt. Start den første besked med dette link til appen: <<APP_LINK>>

Faste krav:
- Husstand: <<HUSSTAND, fx 2 voksne og 2 børn. Børnene regnes som en halv voksenportion hver.>>
- Kun aftensmad, 7 aftener fra søndag til lørdag.
- Budget: højst <<UGEBUDGET>> kr. for hele ugen, inkl. <<SKABSPULJE>> kr. til olie, krydderier, bouillon og lignende.
- Der handles i én butik, én gang, om søndagen.
- Kostmål: <<KOSTMÅL, fx ca. 50-65 g protein pr. voksen pr. aften, børnene det halve.>>
- Allergener og det, der skal undgås: <<ALLERGENER>>. Skriv ikke retter med disse ingredienser.
- Ønsker til retterne: <<ØNSKER, fx mindst én ret med fisk, god variation, børnevenligt og til hverdagsbrug.>>

Opskriftskilder:
Byg hver ret på én konkret, afprøvet opskrift fra en af disse anerkendte danske madsider, valgt ud fra ugens tilbud, så retterne er gennemprøvede og hænger sammen. Opfind ikke retter selv. Find opskrifterne med WebSearch og WebFetch.
- valdemarsro.dk
- mad.coop.dk
- REMA 1000's opskrifter (rema1000.dk)
- DR Mad (dr.dk/mad)
- altomkost.dk (Fødevarestyrelsen)
- madensverden.dk
Regler:
- Skalér mængderne til husstanden ovenfor.
- Justér proteinmængden (fx mere kød, fisk, æg eller bælgfrugter), så kostmålet nås, og skriv hvad der er justeret.
- Byt ingredienser, der strider mod allergenerne, til en sikker udgave, og skriv det ved retten.
- Skriv ingredienslister og trin med egne ord. Kopiér aldrig opskriftens tekst ordret.
- Brug gerne flere kilder i samme uge, men vælg retter der passer sammen i stil og indkøb, så varer udnyttes på tværs af retterne.

Fremgangsmåde:
1. Find tilbud for den kommende uge med WebSearch og WebFetch hos <<BUTIKKER>>. Gode kilder: shop.rema1000.dk/avisvarer, etilbudsavis.dk/soeg/<søgeord>, tilbudsugen.dk, tilbudsoverblik.dk/butik/<kæde> og tilbudsaviseronline.dk.
2. Medtag kun tilbud, der gælder på indkøbssøndagen. Tjek gyldighedsdatoer på hver vare. Pas på weekendtilbud, der starter senere, og aviser der slutter før søndagen.
3. Vælg den ene butik, der giver det bedste samlede resultat inden for budgettet.
4. Find 7 opskrifter fra opskriftskilderne ovenfor, der bruger tilbuddene, og tilpas dem efter reglerne. Læg fisk og det mest letfordærvelige først, og frost eller frysevenligt kød sidst.
5. Beregn samlet pris og næring med kode, ikke i hovedet. Tjek at alle ingredienser i opskrifterne står på indkøbslisten i tilstrækkelig mængde.

Format, let at læse på en telefon:
1. Én indledende linje: butik, samlet pris, luft i budgettet og hvilken avisperiode tilbuddene gælder for.
2. Madplanen: kort oversigt med dag, ret og protein pr. voksen.
3. Indkøbsliste i tre grupper: Tilbudsvarer (fundet pris), Øvrige varer (vejledende pris), Mit prisskøn. Skriv aldrig en skønnet pris, som om den er fundet.
4. Fuld opskrift på hver af de 7 retter, med:
   - Navn, dag, samlet tid og antal personer.
   - Kilde: sidens navn og link til den originale opskrift, samt en kort linje om hvad der er ændret (mængder, protein, allergener).
   - Alle ingredienser med præcise mængder, også krydderier, olie og salt.
   - Nummererede trin, der kan følges uden forkundskaber, med temperaturer og tider, og hvornår tilbehøret skal startes.
   - Fjerkræ og hakket kød skal gennemsteges, og det skal stå i trinnene, hvordan man ser det.
   - Protein pr. voksen og pr. barn.
5. Kort afsnit: hvad der skal fryses om søndagen og tages op dagen før, hvilke varer deklarationen skal tjekkes på for allergener, og eventuelle mængdebegrænsninger på tilbud.

Hvis næste uges avis endnu ikke kan findes for en kæde, så vælg blandt de kæder, hvor den kan findes, og skriv det. Kan ingen findes, så sig det tydeligt, og lav ikke en plan på gamle tilbud uden at markere det. Læg i så fald ikke en plan i appen.

Læg planen i appen (gør dette, før du sender den sidste besked):
Appens link er <<APP_LINK>>. Indlæs værktøjet ArtifactData med ToolSearch: "select:ArtifactData". Byg først planen som JSON med dette skema:

{
  "id": "<søndagens dato, YYYY-MM-DD>",
  "title": "Uge <nummer på den tilbudsavis, der gælder>",
  "store": "<butik>",
  "period": "Avis <fra>.–<til>. <måned>",
  "start": "<søndagens dato, YYYY-MM-DD>",
  "end": "<lørdagens dato, YYYY-MM-DD>",
  "people": "<husstanden kort, fx 2 voksne og 2 børn>",
  "weekBudget": <<UGEBUDGET>>,
  "pantryCost": <<SKABSPULJE>>,
  "groups": [["frugt","Frugt og grønt"],["kod","Kød og fisk"],["kolonial","Kolonial"],["frost","Frost, tag til sidst"]],
  "items": {
    "<vare-id>": {"n":"<varenavn>", "p":"<pakkestørrelse som tekst>", "g":"<gruppe-id>", "q":<mængde i én pakke>, "pr":<pris for én pakke i kr.>, "o":1, "tag":"<kort note>"}
  },
  "pantry": {"<id>":"<navn på vare fra skabet>"},
  "days": [
    {"id":"son", "short":"Søn", "date":"YYYY-MM-DD", "label":"Søndag 15/11", "name":"<ret>", "time":"<samlet tid>", "adult":"<protein pr. voksen, fx 57 g>", "child":"<protein pr. barn>",
     "note":{"h":"Husk i aften","t":"<hvad der skal tages op eller fryses>"},
     "ing":[["<tekst med mængde>","<vare-id>",<mængde>], ["<tekst>","p:<id>"], ["<tekst uden indkøb, fx vand>"]],
     "steps":["<trin 1>","<trin 2>"]}
  ]
}

Regler for skemaet:
- "o":1 kun på tilbudsvarer. Udelad "o" på øvrige varer og "tag", hvis der ikke er en note. Brug "tag" til fx "Frys i dag", "Direkte i fryseren" eller "Tjek for allergener".
- En ingrediens' mængde og varens "q" skal have samme enhed (gram, stk., spsk). Appen regner antal pakker som mængde delt med "q", rundet op, og pris som pakker gange "pr".
- Varer fra skabet ("p:<id>") står uden pris, og deres id skal findes under "pantry".
- Dag-id: son, man, tir, ons, tor, fre, lor. Brug den første dags "note" til det, der skal fryses efter indkøb. Brug "note" dagen før en ret, hvis noget skal tages op af fryseren.
- Sidste punkt i hver dags "steps" skal være kildelinjen: "Kilde: <sidens navn> – <link til original opskrift>. Ændret: <kort om ændringer>".

Kontrol før du gemmer, med kode: alle vare-id'er findes under "items", alle "p:"-id'er findes under "pantry", 7 dage med dato fra start til end, hver dag har en kildelinje, og appens beregning (pakker gange pris plus pantryCost) giver den samlede pris fra din besked og ligger inden for weekBudget.

Gem planen med ArtifactData: action "set", url = appens link, collection "plans", doc_id = planens id og planen som data. Tjek først med action "list" på collection "plans", om dokumentet findes. Gør det, skal "if_version" med dets version med.

Ryd op bagefter med ArtifactData: brug action "list" på collection "plans" og "checks" med appens link. Slet med action "delete", url, collection, doc_id og "if_version" hvert dokument i "plans", hvis feltet "end" er før dags dato, og det tilhørende dokument i "checks" med samme doc_id. Slet ikke planen for den igangværende uge eller den nye plan.

Slut den sidste besked med én linje, der siger, om planen blev gemt i appen. Fejler det, så skriv fejlen, og at planen kun findes i beskederne.
