# Automatisk madplan med Claude

Med én prompt bygger Claude en madplan-app til din husstand og en planlagt opgave, der fylder den med en ny uge hver fredag ud fra ugens tilbudsaviser.

## Det får du

- **Indkøbsliste:** Laves automatisk ud fra ugens retter og samlet efter afdeling i butikken. Du sætter og fjerner flueben, mens du handler, og fravælger en dag, hvis I spiser ude.
- **Opskrifter:** Du bladrer mellem dagene og vinger trin af undervejs. Appen minder om, hvad der skal fryses og tages op.
- **Fredagsopgave:** Claude finder ugens tilbud, vælger den butik, der giver det bedste resultat, finder opskrifterne og lægger planen i appen. Du får også hele planen som besked.
- **Skifte om søndagen:** Appen skifter selv til den nye uge med en tom liste. Den gamle uge forsvinder, og opgaven sletter den ved næste kørsel.
- **Deling:** Alle i husstanden kan bruge den samme liste og se hinandens flueben.

Hver ret bygger på en rigtig opskrift fra Valdemarsro, Coop, REMA 1000, DR Mad, Altomkost eller Madensverden. Mængderne tilpasses din husstand, og proteinet justeres, så I når jeres mål. Under hver opskrift står et link til originalen og hvad der er ændret.

## Filerne

| Fil | Hvad den er |
| --- | --- |
| [`madplan-app.html`](madplan-app.html) | Appen. Den er tom for madplaner og indeholder ingen personlige oplysninger. |
| [`prompts/startprompt.md`](prompts/startprompt.md) | Prompten, du indsætter i en ny Claude-chat. |
| [`prompts/fredagsopgave.md`](prompts/fredagsopgave.md) | Prompten til den planlagte opgave. Claude udfylder felterne i dobbelte vinkler. |

## Det skal du bruge

Du skal have en Claude-konto, hvor du kan oprette apps (artifacts) og planlagte opgaver. Hvert voksent medlem, der skal sætte flueben, skal også have en Claude-konto.

Hav svarene på disse spørgsmål klar. Claude spørger om dem, når du indsætter startprompten.

| Det skal Claude vide | Eksempel |
| --- | --- |
| Antal voksne og børn, og hvor stor en portion børnene spiser | 2 voksne og 2 børn, der hver spiser en halv voksenportion |
| Budget for en hel uge | 800 kr. inkl. 40 kr. til olie, krydderier og bouillon |
| Allergener og hvad der skal undgås | Nødder og jordnødder |
| Mål for kosten | 50-65 g protein pr. voksen pr. aften |
| Særlige ønsker til retterne | Mindst én ret med fisk, børnevenligt, til hverdagsbrug |
| Butikker | REMA 1000, Netto, Lidl, føtex, gerne andre landsdækkende kæder |
| Land og sprog | Danmark, dansk |

## Trin for trin

Opsætningen tager cirka 15 minutter og sker i én chat med Claude.

1. Start en ny chat med Claude, hvor Claude kan oprette apps og planlagte opgaver.
2. Vedhæft filen `madplan-app.html`. Kopiér indholdet af `prompts/startprompt.md` ind i beskeden, og indsæt hele `prompts/fredagsopgave.md` sidst i samme besked.
3. Svar på Claudes spørgsmål om din husstand.
4. Åbn appen fra det link, Claude giver dig, og læg den på hjemmeskærmen. På iPhone: Safari, del-knappen, Føj til hjemmeskærm. På Android: Chrome, de tre prikker, Føj til startskærm.
5. Tjek opsætningen med punkterne herunder.

Er næste uges tilbudsavis ikke ude endnu, skriver opgaven det tydeligt og lægger ikke en plan i appen.

## Kontrol

Opsætningen virker, når alle fire punkter er opfyldt.

- [ ] Du kan sætte et flueben, og det forsvinder, når du trykker igen.
- [ ] Nederst på listen står der, at afkrydsningerne følger med på alle dine enheder.
- [ ] Du har en planlagt opgave ved navn Ugentlig madplan, der kører om fredagen.
- [ ] Du har fået en besked med planen, og den sidste linje siger, at planen er gemt i appen.

## Del med husstanden

Åbn appens side på claude.ai, vælg del, og inviter den anden på e-mail som redaktør (Editor). Vedkommende skal være logget ind på sin egen Claude-konto. Deler du med et link, kan andre se appen, men deres flueben kommer ikke med på den fælles liste.

Del aldrig linket til din egen app offentligt. Så kan andre se jeres madplan og indkøbsliste.

## Fejlfinding

| Problem | Løsning |
| --- | --- |
| Flueben kan ikke ændres | Luk appen helt, og åbn den igen. Hjælper det ikke, så bed Claude tjekke, at appen svarer til filen `madplan-app.html`. |
| Fanerne Indkøb og Opskrifter står nederst eller mangler | Det er en ældre udgave af filen. Bed Claude udgive den nyeste udgave på den samme app, så linket og fluebenene bevares. |
| Der står, at der ikke er en plan | Tjek, om fredagsopgaven er kørt, og læs den sidste linje i dens besked. Bed Claude køre opgaven igen. |
| Beskeden siger, at planen ikke blev gemt | Bed Claude læse fejlen og gemme planen i appen igen. Planen findes stadig i beskederne. |
| Priser eller varer passer ikke i butikken | Priserne kommer fra tilbudsaviser og butikkernes webshop. Udvalg og pris kan variere fra butik til butik. |
| Du vil ændre budget eller allergener | Bed Claude rette prompten i den planlagte opgave. |

## Sådan virker appen

Appen læser planer fra samlingen `plans` i sin database og viser den plan, hvor dags dato ligger mellem `start` og `end`. Fluebenene ligger i `checks/<plan-id>`, så de nulstilles automatisk med en ny plan. Skemaet for en plan står i `prompts/fredagsopgave.md`.

Claude skal udgive `madplan-app.html` uændret, så afkrydsning og ugeskifte virker, som de er testet.

## Forbehold

Planerne laves af AI ud fra offentlige tilbudsaviser og opskriftssider. Tjek altid varedeklarationen, hvis nogen i husstanden har allergier. Projektet er ikke tilknyttet Anthropic eller de nævnte butikker og madsider.

## Licens

MIT, se [LICENSE](LICENSE).
