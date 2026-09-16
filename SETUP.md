# Sådan sætter du Jacob's to do liste op

Alt foregår i browseren på github.com — ingen terminal, intet git nødvendigt.

## 1. Opret en GitHub-konto (spring over hvis du har en)
Gå til github.com → "Sign up" → gratis konto.

## 2. Opret et nyt repository
- Klik "+" øverst til højre → "New repository"
- Navn: `vaerkstedskoen` (eller vælg selv — husk navnet, det skal bruges i trin 4)
- Sæt det til **Public** (det er en forudsætning for at GitHub Pages er gratis, og for at kolleger uden invitation kan sende en anmodning)
- Klik "Create repository"

## 3. Læg filerne ind
I det nye (tomme) repository:
- Klik "Add file" → "Upload files"
- Træk hele indholdet af mappen du har fået (`index.html` og hele `.github`-mappen) ind i browservinduet — GitHub bevarer mappestrukturen
- Klik "Commit changes"

Vigtigt: `.github/ISSUE_TEMPLATE/anmodning.md` og `config.yml` SKAL ligge i den nøjagtige sti — det er det der styrer anmodningsformularen.

## 4. Ret dit brugernavn ind i siden
- Åbn `index.html` i repositoriet, klik blyant-ikonet ("Edit")
- Find linjen `const OWNER = "DIT-BRUGERNAVN";` og skriv dit rigtige GitHub-brugernavn i stedet
- Hvis du kaldte repositoriet noget andet end `vaerkstedskoen`, ret også `REPO`-linjen
- Klik "Commit changes"

## 5. Slå GitHub Pages til
- Gå til repositoriets "Settings" → "Pages" (i venstre menu)
- Under "Build and deployment" → "Source": vælg "Deploy from a branch"
- Branch: `main`, mappe: `/ (root)` → "Save"
- Vent ca. 1 minut, opdatér siden — der vises et grønt link øverst, noget i stil med:
  `https://dit-brugernavn.github.io/vaerkstedskoen/`

Det link er din side ("Jacob's to do liste"). Gem det som bogmærke.

## 6. Sådan bruges det i praksis

**En kollega beder om noget:** send dem linket
`https://github.com/<brugernavn>/<repo>/issues/new?template=anmodning.md`
(samme link som "+ Ny anmodning"-knappen på siden peger på). De:
1. skriver selve opgaven kort i titelfeltet øverst, fx "Kabinet til sensor",
2. udfylder deres navn, en evt. frist (ÅÅÅÅ-MM-DD) og eventuelle detaljer i teksten,
3. kan trække et billede, en PDF eller en 3D-fil direkte ind i tekstboksen, hvis der er noget at vedhæfte,
4. trykker "Submit new issue".

De skal have en gratis GitHub-konto — har de ikke det i forvejen, bliver de bedt om at oprette en, første gang de klikker.

**Du tjekker køen:** åbn din side (linket fra trin 5). Du ser alle åbne anmodninger, sorteret efter frist (dem uden frist efter alder), med navn, dato og en "Detaljer"-knap hvis der er mere at se. "Opdatér" i toppen henter de nyeste anmodninger igen, uden at du skal genindlæse hele siden.

**Du markerer noget som færdig:** klik "✓ Marker som færdig på GitHub" på kortet — det åbner selve anmodningen på GitHub, hvor du klikker "Close issue". Den flytter sig så til "Færdige" på din side (efter et "Opdatér"-klik).

**Du vil have et overblik du kan give til Claude:** klik "⇪ Eksportér build tracker" nederst på siden. Den bygger en tekst med alle åbne opgaver (mest presserende først) og de færdige — klik "Kopiér tekst" og sæt den ind i en chat med Claude, så den kan huske jeres kø og hjælpe med at pege på den næste opgave. "Gem som fil" gemmer den samme tekst som en `.md`-fil, hvis du hellere vil have den liggende.

## Værd at vide
- Fordi repositoriet er **offentligt** (en forudsætning for gratis GitHub
  Pages), kan indholdet i princippet ses af alle på internettet, hvis de
  kender linket eller støder på det — det er ikke adgangskodebeskyttet.
  Vil du hellere holde det helt privat, kræver det et betalt GitHub Pro-abonnement
  (ca. 4 USD/md.) på din konto — sig til, så hjælper jeg med at lave det om.
- Skal du undgå at hvem som helst kan oprette anmodninger (ikke kun jeres
  kolleger), kan du under Settings → Features → Issues sætte
  "Creation allowed by: Collaborators only" — så skal hver kollega først
  inviteres én gang som "Collaborator" på repositoriet.
- Siden henter data direkte fra GitHub's offentlige API uden login — det er
  begrænset til 60 opslag i timen pr. besøgende, hvilket er rigeligt til
  almindelig brug, men bemærk det hvis "Opdatér" pludselig fejler efter mange
  hurtige klik.
