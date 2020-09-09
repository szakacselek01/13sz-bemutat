# 13sz osztály bemutatkozása
Osztály projekt a git technológia bemutatása céljából.  
A gitHub repo-n van eleve egy **developer** ág

# Előkészületek

## Meghívás kollaborátornak
A projekt github oldalán meghívjuk a tanulókat a projektbe

## Klónozás, developer repo létrehozása
- A tanulók klónozzák a projektet `git clone url`
- A tanulók létrehozzák a developer ágat a helyi repojukon: `git branch developer`
- majd átkpacsolnak erre az ágra: `git checkout developer`
- Innentől kezdve itt doloznak

## Felhasználói adatok beállítása
Conzol ablakban beállítják a felhasználói adatokat.  
User név: `git config --global user.name xy`  
Email: `git config --global user.email xy@gmail.com`

## Branch létrehozása helyi repo-kon
- Branch létrehozás: `git branch developer`  
- átkapcsolás a developer ágra: `git checkout developer`  
- branch lekérdezése (azon állunk-e?): `git branch`

## Images és Tanulok mappa létrehozása
A master fejlesztője létrehoz egy Images és Tanulok mappát.  
Belerak valamit, hogy tudja commitolni. 
- `git add .`
- `git commit -m "Images, Tnulok folder created"`
- `git push origin master`

## Images mappa átadása a developer ágnak a gitHub-on
- gitHub: pull request kezdeményezése
- gitHub: pull request végrehajtása
- midnen developer helyi repo: pull (mindenki megkapja a mappát)

# A fejlesztés folyamata
## A bemutatkozás oldal elkészítése (developer ágon)
### Tanulók, branch nevek, bemutatkozás oldalak
Fejlesztő | Branch | Oldal név
-- | :--: | --
Kovács Nándor | **master** | index.html
Csontos Krisztián | developer/**master** | csontos.html
Farkas Cintia | developer | cintia.html
Horváth Márió | developer | mario.html
Juhász Gábor | developer | gabor.html
Nagy János Péter | developer | janos.html
Nagy Zoltán Albert | developer | zoltan.html
Orsós Ákos | developer | akos.html
Szakács Elek | developer | elek.html
Thoma Krisztián  | developer | krisztian.html
Tóth Lajos Szabolcs | developer | lajos.html
Urbán Tibor | developer | tibor.html

### Feladat leírása
Töltsön le magáról egy képet az **Images** mappába  
Készítse el a html oldalt a megadott néven a **Tanulok** mappába:  
- legyen címe
- legyen title
- tartalmazzon egy rövid bemutatkozó szöveget, 
- legyen benne egy fotó,
- legyen rajt egy link az index.html-re **vissza** szöveggel.

### Színpad, commit, push
`git add .`  
`git commit -m "bemutatkozó oldal create"`  
`git push origin developer` 

### A github-on pull request, és merge (master user csinálja)
A github-bon annak gazdája a keletkezett branch-eken végigmegy és pull request segítségével mergeli az összeset.

### Tanulók: pull
Ha kész az összes merge, akkor a tanulók átváltanak master-re: `git branch master`  
Utána pull-al lehúzzák saját repójukba a végeredményt: `git pull`

## Konfliktus kezelési gyakorlat
A **master** átváltoztatja a az index oldal címét: **Osztály névsor**-ra
- `git add .`  
- `git commit -m "index cím modify by master"`  
- `git push origin master` 
A **developer/master** tanuló ugyancsak átváltoztatja az index oldal címét: **Oszály bemutatkozás**-ra
- `git add .`  
- `git commit -m "index cím modify by developer"`  
- `git push origin developer` 
A **master** pullRequest-el át akarja vinni a **developer/master** változtatását a **master** ágra:
- konfliktus keletkezik
- eldönti hogy melyik jó, és javít (commit)
- mindkét ágban ez lesz
- minden developer: 
  - **developer** ágban pull
  - **master** ágban pull

