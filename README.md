# fork-branch-merge-eksempel

Formålet med denne øvelse, er at få afprøvet git koncepterne `fork`, `branch`, `merge` og `pull request`

Det er nogle stærke værktøjer der kan benyttes til at splitte udviklingen af applikationer, enten ud over flere personer, eller lokalt i flere grene. 

Ved at benytte sig af værktøjerne, vil man altid have en fungerende `master` og en *(eller flere)* `brances` for hvert nye emne der skal tilføjes applikationen.


## FORK
`Fork` dette repository til din egen github konto.

* Gå på https://github.com/rts-cmk-WI81/fork-branch-merge-eksempel
* klik på `fork` ikonet øverst til højre
* vælg din egen konto i vinduet der dukker op

## CLONE
`Clone` dit forkede repo til din desktop og åben det i Visual Studio Code, lige som du plejer med et github repo.


## Branches 
I Visual Studio Code, nederst til venstre hjørne, klikkes på `master` og derefter i toppen af programmet vælges `+ Create Branch` samt der angives et nyt navn til den nye `branch` kunne f.eks. være `dev` 

*måske vil programmet spørge ind til `select a ref to create a branch from`.  Vælg `master` hvis det kommer frem, ellers vil den pr default vælge `master`*

Tjek at der ikke længere står `master` nederst til venstre, der skal stå navnet på din ny `branch`, det betyder at alle ændringer sker udelukkende i den `branch`.

I den nye `dev branch` oprettes et nyt html-dokument, kald dokumentet dit eget navn + html.

Indsæt lidt htmlkode, f.eks. en overskrift og et par linjer tekst om dig selv.

`commit` den nye `branch` og `push` til github. 

Første gang en branch pushes til github, vil den komme frem og spørge om du vil oprette en `upstream branch` det siger du ja tak til, så vil din branch også eksistere online.

*måske vil programmet spørge hvilken `origin` din `branch` skal tilhøre, her vælges `origin`. Hvis det ikke kommer frem, er alt helt som det skal være* 


## Merge
Gå på github til dit klonede repository, og tjek at `master` og `dev` branch er forskellige. Er de ikke forskellige, eller mangler `dev` så mangler du måske at `pushe` ændringerne til github. 

Klik på `Compare & Pull request` så de to `branches` kan flettes sammen.

På siden der kommer frem, skal du ved `base repository` ændre valget til dit eget, frem for `rts-cmk-wi81`, og der burde nu stå et grønt `able to merge` på skærmen.

I formularen skrives en passende besked og der klikkes på `create pull request`.

Efter github har tænkt en smule, kommer den forhåbentligt frem og siger at de to `brances` kan `merges`, klik på den grønne knap `merge pull request`



Når fletningen er udført, gå tilbage i VScode og gå ind i `source control` *(den med gaflen)*, og vælg `pull` så den lokale version stemmer overens med online versionen.

## Pull Request -> til origin

Gå på github og ind på dit forkede repository, klik på `New pull request`.

Herefter sættes `base repository` til `rts-cmk-wi81` repositoriet og hvis alt er som det skal være, vil du få en grøn `Able to merge`

Klik på den grønne `create pull request` og skriv en besked om hvad det er du forsøger at sende til originalen.

Hvis alt går igennem som forventet, vil ejeren af det originale repository nu have muligheden for at tjekke det kode du har skrevet, og enten `merge` ændringerne ind i originalen, eller afvise med en beskrivelse af hvorfor det er afvist.


## Pull Upstream

Når du vil opdatere din fork, med de nye filer der er blevet pushet, til det oprindelige repo, så følges denne guide.

I terminal vinduet i Visual Studio Code, skrives de her to linjer:

```
git remote add upstream git://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git
git fetch upstream
```

`ORIGINAL-DEV-USERNAME` skal i dette tilfælde erstattes med `rts-cmk-WI81` og
`REPO-YOU-FORKED-FROM` ersttes med `fork-branch-merge-eksempel`

*dette trin skal kun gøres 1 gang, derefter er `remote upstream` defineret* 


For at hente ændringerne, køres denne kommando *(stadig i terminalen i VScode)*, som placerer ændringerne i din `master`
```
git pull upstream master
```

*Øvelsen er klaret, når alle er kommet igennem alle punkterne, og alle har en fuldt opdateret fork, som indeholder samtlige html filer de andre har oprettet.*


*Der er ikke tid til at gennemgå alle fejlscenarier under oplægget, dem tager vi som de kommer i den efterfølgende praktiske periode* 

