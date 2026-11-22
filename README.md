# Laboratorio interattivo di programmazione · Interactive Programming Lab · Interaktivni učni laboratorij

[🇮🇹 Italiano](#italiano) · [🇬🇧 English](#english) · [🇸🇮 Slovenščina](#slovenščina)

Piattaforma didattica web per l'insegnamento della programmazione nella scuola secondaria. Il progetto comprende due ambienti collegati: **Python Lab** e **SQL Lab**. Gli studenti svolgono esercizi direttamente dal browser; gli insegnanti gestiscono classi, attività e monitoraggio dei progressi.

---

## Italiano

### Che cos'è

Il progetto è una piattaforma interattiva per imparare e mettere in pratica **Python** e **SQL**. Non richiede l'installazione di un ambiente di sviluppo sul computer dello studente: il codice viene eseguito nel browser, mentre account, classi, esercizi e progressi sono gestiti tramite **Supabase**.

La piattaforma è composta da due pagine:

- `index.html` – **Python Lab**, ambiente per scrivere ed eseguire programmi Python;
- `sql_lab.html` – **SQL Lab**, ambiente per scrivere ed eseguire query SQL su un database didattico SQLite.

### Funzioni per gli studenti

**Accesso e progressi**
- Accesso tramite codice personale di 8 caratteri e nome o nickname.
- Ogni studente utilizza un codice personale associato alla propria classe.
- Il completamento degli esercizi, i tentativi e l'utilizzo degli aiuti vengono registrati e sincronizzati con Supabase.

**Python Lab**
- Editor di codice con numeri di riga, indentazione con `Tab`, parentesi automatiche e regolazione della dimensione del testo.
- Esecuzione di Python nel browser tramite **Pyodide**.
- Inserimento dei dati richiesti da `input()` in un campo dedicato, con un valore per riga.
- Evidenziazione della riga in cui si è verificato un errore, quando la posizione è riconoscibile.
- Anteprima in tempo reale del codice negli esercizi di completamento.
- Ambiente libero per sperimentare con il codice.
- Percorso di disegno con **Turtle**: 30 esercizi guidati e una superficie grafica nel browser basata su Canvas.

La raccolta Python comprende **295 esercizi**, suddivisi in sette tipologie:

| Tipologia | Numero |
|---|---:|
| Laboratori eseguibili | 85 |
| Completa il codice | 49 |
| Quiz | 49 |
| Correggi il codice | 41 |
| Scrivi un programma | 36 |
| Prevedi l'output | 20 |
| Riordina le righe di codice | 15 |
| **Totale** | **295** |

I 30 esercizi Turtle sono già inclusi nel totale dei 295 esercizi Python.

**SQL Lab**
- Esecuzione delle query nel browser tramite **SQLite** e `sql.js`.
- Database didattico iniziale con nomi delle tabelle in sloveno e dati dimostrativi.
- Esercizi con verifica del risultato e possibilità di eseguire una query senza inviarla alla correzione.
- Ambiente SQL libero per provare query e modifiche; il database di prova può essere ripristinato.
- Filtri per categoria e argomento.

La raccolta SQL comprende **235 esercizi**. Lo schema didattico utilizza, tra le altre, le tabelle `dijaki`, `predmeti`, `vpisi`, `izdelki` e `narocila`.

**Aiuti e soluzioni**
- Gli esercizi possono offrire suggerimenti.
- Dopo cinque tentativi non corretti è possibile richiedere la visualizzazione della soluzione, se la relativa funzione è stata configurata nel backend.
- Le risposte corrette e le soluzioni sono conservate separatamente dai contenuti visibili agli studenti.

### Funzioni per gli insegnanti

L'area insegnanti richiede l'accesso con un account autorizzato.

- Creazione e gestione di classi Python o SQL e definizione del numero massimo di studenti.
- Generazione di codici personali per gli studenti; ogni codice è destinato a un solo studente.
- Importazione di raccolte di esercizi in formato JSON e aggiornamento degli esercizi esistenti tramite il loro ID.
- Creazione, modifica ed eliminazione degli esercizi.
- Esportazione di una copia della raccolta.
- Consultazione dei progressi per classe e per studente, inclusi esercizi completati e tentativi.
- Modalità di anteprima e prova degli esercizi senza modificare i progressi degli studenti.

### Tecnologie

- **HTML, CSS e JavaScript** per l'interfaccia.
- **Pyodide** per eseguire Python nel browser.
- **Turtle + Canvas** per le attività grafiche supportate dal laboratorio.
- **SQLite tramite sql.js** per il laboratorio SQL.
- **Supabase** per autenticazione, classi, esercizi, soluzioni e progressi.
- **GitHub Pages** per la pubblicazione come sito statico.

### Pubblicazione e configurazione

1. Pubblicare `index.html` e `sql_lab.html` nella cartella principale del repository GitHub utilizzato da GitHub Pages.
2. Configurare nelle pagine i valori del progetto Supabase (`SUPABASE_URL` e chiave pubblicabile). La chiave `service_role` non deve mai essere inserita nel codice del browser o in un repository pubblico.
3. Applicare al progetto Supabase le migrazioni SQL e le policy di sicurezza necessarie per classi, codici personali, esercizi, soluzioni e progressi.
4. Abilitare l'accesso anonimo per gli studenti in Supabase Auth e predisporre gli account insegnante autorizzati.
5. Importare le raccolte JSON dall'area insegnanti, assegnandole alla classe corretta.
6. Verificare l'accesso di uno studente, l'esecuzione di alcuni esercizi e la registrazione dei progressi sul sito pubblicato.

Le librerie Pyodide, sql.js e Supabase JS vengono caricate da CDN: durante l'utilizzo è quindi necessaria una connessione Internet.

### Note importanti

- Il codice Python e le query SQL vengono eseguiti nel browser dello studente. I laboratori non costituiscono un ambiente server isolato per l'esecuzione di codice non attendibile e non devono essere usati per elaborare dati riservati.
- L'ambiente Turtle implementa nel browser le funzioni grafiche utilizzate dagli esercizi; non è una replica completa di tutte le funzionalità della libreria Turtle standard.
- Le raccolte JSON importate dagli insegnanti possono contenere soluzioni e risposte. **Non pubblicare tali file in un repository GitHub pubblico**: caricarli tramite l'area insegnanti.
- La chiave pubblicabile di Supabase può essere presente nel frontend solo se le autorizzazioni e le policy RLS del progetto sono configurate correttamente. Non inserire mai chiavi segrete o `service_role` nel frontend.

---

## English

### What is this project?

This project is a web-based learning platform for teaching and practising **Python** and **SQL**. Students do not need to install a development environment on their computers: code runs in the browser, while authentication, classes, exercises and learning progress are managed with **Supabase**.

The platform consists of two pages:

- `index.html` – **Python Lab**, where students write and run Python programs;
- `sql_lab.html` – **SQL Lab**, where students write and run SQL queries against an educational SQLite database.

### Student features

**Access and progress tracking**
- Students sign in with an 8-character personal access code and a name or nickname.
- Each personal code is associated with a class and intended for one student.
- Exercise completion, attempts and hint usage are recorded and synchronised with Supabase.

**Python Lab**
- Code editor with line numbers, `Tab` indentation, automatic bracket pairing and adjustable text size.
- Python execution in the browser using **Pyodide**.
- A dedicated input area for values read by `input()`, with one value per line.
- Error-line highlighting when the runtime provides a recognisable line location.
- Live code preview in fill-in-the-code exercises.
- A free coding area for experimentation.
- A **Turtle** drawing pathway with 30 guided exercises and a browser-based Canvas drawing surface.

The Python collection contains **295 exercises** across seven activity types:

| Exercise type | Count |
|---|---:|
| Executable labs | 85 |
| Fill in the code | 49 |
| Quizzes | 49 |
| Debug the code | 41 |
| Write a program | 36 |
| Predict the output | 20 |
| Reorder code lines | 15 |
| **Total** | **295** |

The 30 Turtle exercises are already included in the 295-exercise Python collection.

**SQL Lab**
- SQL queries run in the browser using **SQLite** and `sql.js`.
- A preloaded educational database with Slovenian table names and sample records.
- Exercises with result checking, plus an option to run a query without submitting it for checking.
- A free SQL workspace for testing queries and changes; the sample database can be reset.
- Filters by category and topic.

The SQL collection contains **235 exercises**. Its educational schema includes tables such as `dijaki`, `predmeti`, `vpisi`, `izdelki` and `narocila`.

**Hints and solutions**
- Exercises can provide hints.
- After five incorrect attempts, students can request to reveal the solution, provided the corresponding backend function is configured.
- Correct answers and solutions are stored separately from the content that students can read.

### Teacher features

The teacher area requires an authorised teacher account.

- Create and manage Python or SQL classes and set class capacity.
- Generate personal student access codes; each code is intended for one student.
- Import exercise collections from JSON and update existing exercises by ID.
- Create, edit and delete exercises.
- Export a backup of the exercise collection.
- Review progress by class and by student, including completed exercises and attempts.
- Preview and test exercises without changing student progress.

### Technology stack

- **HTML, CSS and JavaScript** for the user interface.
- **Pyodide** to run Python in the browser.
- **Turtle + Canvas** for the drawing activities supported by the lab.
- **SQLite via sql.js** for SQL exercises.
- **Supabase** for authentication, classes, exercises, solutions and progress tracking.
- **GitHub Pages** for static website hosting.

### Deployment and configuration

1. Place `index.html` and `sql_lab.html` in the root of the GitHub repository used by GitHub Pages.
2. Configure the Supabase project values in the pages (`SUPABASE_URL` and the publishable key). Never put the `service_role` key in browser code or in a public repository.
3. Apply the SQL migrations and security policies required for classes, personal access codes, exercises, solutions and progress tracking.
4. Enable anonymous sign-in for students in Supabase Auth and create authorised teacher accounts.
5. Import the JSON exercise collections from the teacher area and assign them to the appropriate class.
6. Test student sign-in, several exercises and progress synchronisation on the published site.

Pyodide, sql.js and Supabase JS are loaded from CDNs, so an Internet connection is required while using the platform.

### Important notes

- Python code and SQL queries run in the student's browser. These labs are not a server-side sandbox for untrusted code and should not be used to process confidential data.
- The browser-based Turtle environment implements the drawing functions used by the exercises; it is not a complete implementation of every feature in the standard Turtle library.
- JSON collections imported by teachers may contain solutions and answer keys. **Do not publish these files in a public GitHub repository**; upload them through the teacher area instead.
- A Supabase publishable key may be included in frontend code only when the project's permissions and Row Level Security (RLS) policies are correctly configured. Never expose secret keys or the `service_role` key in the frontend.

---

## Slovenščina

### Kaj je ta projekt?

Projekt je spletna učna platforma za poučevanje in utrjevanje programiranja v jezikih **Python** in **SQL**. Dijakom na računalnik ni treba nameščati razvojnega okolja, saj se koda izvaja v brskalniku. Za prijavo, razrede, vaje in spremljanje napredka skrbi **Supabase**.

Platformo sestavljata dve strani:

- `index.html` – **Python Lab**, okolje za pisanje in izvajanje programov v Pythonu;
- `sql_lab.html` – **SQL Lab**, okolje za pisanje in izvajanje poizvedb SQL nad učno podatkovno zbirko SQLite.

### Funkcije za dijake

**Dostop in spremljanje napredka**
- Dijak vstopi z osemmestno osebno kodo ter imenom ali vzdevkom.
- Vsaka osebna koda je povezana z razredom in je namenjena enemu dijaku.
- Opravljene vaje, število poskusov in uporaba namigov se beležijo ter sinhronizirajo s Supabase.

**Python Lab**
- Urejevalnik kode s številkami vrstic, zamikanjem s tipko `Tab`, samodejnim vstavljanjem oklepajev in prilagodljivo velikostjo pisave.
- Izvajanje kode Python v brskalniku s pomočjo **Pyodide**.
- Ločeno polje za vhodne vrednosti funkcije `input()`; vsaka vrednost je v svoji vrstici.
- Označevanje vrstice z napako, kadar izvajalno okolje omogoča določitev njene lokacije.
- Predogled kode v živo pri vajah za dopolnjevanje kode.
- Prosto okolje za samostojno preizkušanje kode.
- Učna pot risanja s **Turtle**: 30 vodenih vaj in risalna površina v brskalniku, ki temelji na Canvas.

Zbirka Python vsebuje **295 vaj** v sedmih oblikah:

| Vrsta vaje | Število |
|---|---:|
| Izvedljivi laboratoriji | 85 |
| Dopolni kodo | 49 |
| Kvizi | 49 |
| Popravi kodo | 41 |
| Napiši program | 36 |
| Napovej izpis | 20 |
| Uredi vrstni red vrstic kode | 15 |
| **Skupaj** | **295** |

Vseh 30 vaj Turtle je že vključenih v zbirko 295 vaj Python.

**SQL Lab**
- Izvajanje poizvedb SQL v brskalniku s pomočjo **SQLite** in knjižnice `sql.js`.
- Vnaprej pripravljena učna podatkovna zbirka s slovenskimi imeni tabel in podatki za primere.
- Vaje s preverjanjem rezultatov in možnostjo, da dijak poizvedbo samo izvede, ne da bi jo oddal v preverjanje.
- Prosto okolje SQL za preizkušanje poizvedb in sprememb; začetno podatkovno zbirko je mogoče ponastaviti.
- Filtriranje vaj po kategoriji in temi.

Zbirka SQL vsebuje **235 vaj**. Učna shema med drugim vključuje tabele `dijaki`, `predmeti`, `vpisi`, `izdelki` in `narocila`.

**Namigi in rešitve**
- Pri vajah so lahko na voljo namigi.
- Po petih nepravilnih poskusih lahko dijak zahteva prikaz rešitve, če je ustrezna funkcija nastavljena v zalednem sistemu.
- Pravilni odgovori in rešitve so shranjeni ločeno od vsebine, ki je dostopna dijakom.

### Funkcije za učitelje

Za vstop v učiteljsko okolje je potreben pooblaščen učiteljski račun.

- Ustvarjanje in upravljanje razredov Python ali SQL ter določanje največjega števila dijakov.
- Ustvarjanje osebnih dostopnih kod za dijake; vsaka koda je namenjena enemu dijaku.
- Uvažanje zbirk vaj v obliki JSON in posodabljanje obstoječih vaj glede na njihov ID.
- Ustvarjanje, urejanje in brisanje vaj.
- Izvoz varnostne kopije zbirke vaj.
- Pregled napredka po razredih in posameznih dijakih, vključno z opravljenimi vajami in številom poskusov.
- Predogled in preizkušanje vaj brez spreminjanja napredka dijakov.

### Uporabljene tehnologije

- **HTML, CSS in JavaScript** za uporabniški vmesnik.
- **Pyodide** za izvajanje Pythona v brskalniku.
- **Turtle + Canvas** za grafične naloge, ki jih podpira laboratorij.
- **SQLite prek knjižnice sql.js** za vaje SQL.
- **Supabase** za avtentikacijo, razrede, vaje, rešitve in spremljanje napredka.
- **GitHub Pages** za objavo statične spletne strani.

### Objava in nastavitev

1. Datoteki `index.html` in `sql_lab.html` shranite v korensko mapo repozitorija GitHub, ki ga objavljate prek GitHub Pages.
2. V straneh nastavite podatke projekta Supabase (`SUPABASE_URL` in javni ključ). Ključa `service_role` nikoli ne vključite v kodo brskalnika ali javni repozitorij.
3. V Supabase izvedite potrebne SQL-migracije in varnostne politike za razrede, osebne kode, vaje, rešitve in spremljanje napredka.
4. V Supabase Auth omogočite anonimno prijavo dijakov in ustvarite pooblaščene učiteljske račune.
5. Zbirke vaj JSON uvozite prek učiteljskega okolja in jih dodelite ustreznemu razredu.
6. Na objavljeni strani preverite prijavo dijaka, reševanje nekaj vaj in sinhronizacijo napredka.

Knjižnice Pyodide, sql.js in Supabase JS se nalagajo s CDN-jev, zato je za uporabo platforme potrebna internetna povezava.

### Pomembne opombe

- Koda Python in poizvedbe SQL se izvajajo v dijakovem brskalniku. Laboratorija nista strežniško izolirano okolje za izvajanje nezaupanja vredne kode in nista namenjena obdelavi zaupnih podatkov.
- Brskalniško okolje Turtle podpira grafične funkcije, ki jih uporabljajo pripravljene vaje; ne gre za popolno izvedbo vseh funkcij standardne knjižnice Turtle.
- Zbirke JSON, ki jih uvažajo učitelji, lahko vsebujejo rešitve in pravilne odgovore. **Teh datotek ne objavljajte v javnem repozitoriju GitHub**; uvozite jih prek učiteljskega okolja.
- Javni ključ Supabase je lahko vključen v odjemalsko kodo samo ob pravilno nastavljenih dovoljenjih in pravilih Row Level Security (RLS). Skrivnih ključev ali ključa `service_role` nikoli ne vključite v frontend.
