# Guida completa – esercitazione GitHub Flow

Questa guida descrive il progetto realizzato da **due persone** e contiene i passaggi di collaborazione GitHub Flow. Le tre sezioni del sito (Pizze, Dolci e Bibite) sono aree funzionali del progetto, non tre ruoli di sviluppatore distinti.

Repository remoto: https://github.com/Leonardogandini-2008/progetto-pizzeria

## 1. Ruoli del gruppo

Il progetto è stato realizzato da **due partecipanti** che hanno collaborato alla progettazione e allo sviluppo. Le attività di coordinamento del repository, modifica dei file, creazione dei branch, Pull Request e integrazione sono attività del flusso di lavoro: non rappresentano quattro persone diverse.

Le sezioni Pizze, Dolci e Bibite sono aree funzionali del sito; non corrispondono a tre sviluppatori distinti.

## 2. Preparazione del repository da parte della persona che coordina

1. Creare un repository GitHub pubblico chiamato `progetto-pizzeria`.
2. Inserire i file iniziali `index.html` e `style.css`.
3. Scrivere nel README lo scopo del progetto e le regole di collaborazione.
4. Aprire **Settings → Collaborators** (o **Collaborators and teams**) e scegliere **Add people**.
5. Cercare il nome utente GitHub del secondo partecipante e inviare l'invito.
6. Il secondo partecipante deve accettare l'invito ricevuto da GitHub.

**Nota operativa:** l'invito al secondo partecipante deve essere inviato dal proprietario del repository utilizzando il suo effettivo nome utente GitHub. Non è stato inviato in questa esecuzione perché il nome utente del secondo partecipante non è stato fornito e il collegamento GitHub utilizzato per il progetto non espone l'azione di amministrazione degli inviti.

## 3. Clone del repository

Ogni sviluppatore apre il terminale e lancia:

```bash
git clone https://github.com/Leonardogandini-2008/progetto-pizzeria.git
cd progetto-pizzeria
```

Il comando `clone` crea una copia locale del repository remoto.

## 4. Creazione dei branch e lavoro in coppia

Le due persone lavorano su branch separati, senza modificare direttamente `main`. I branch possono essere organizzati per area funzionale. Per esempio, i branch `menuPizza`, `menuDolci` e `menuBibite` identificano le modifiche alle rispettive sezioni e non implicano la presenza di tre sviluppatori.

**Esempio di modifica della sezione Pizze (eseguita da uno dei due partecipanti)**

```bash
git switch -c menuPizza
# Modificare la sezione Pizze in index.html
git add index.html
git commit -m "Aggiunge una nuova pizza al menu"
git push -u origin menuPizza
```

**Esempio di modifica della sezione Dolci (eseguita da uno dei due partecipanti)**

```bash
git switch -c menuDolci
# Modificare la sezione Dolci in index.html
git add index.html
git commit -m "Aggiunge un nuovo dolce al menu"
git push -u origin menuDolci
```

**Esempio di modifica della sezione Bibite (eseguita da uno dei due partecipanti)**

```bash
git switch -c menuBibite
# Modificare la sezione Bibite in index.html
git add index.html
git commit -m "Aggiunge una nuova bibita al menu"
git push -u origin menuBibite
```

I comandi svolgono queste funzioni:

- `git switch -c` crea e seleziona un nuovo branch.
- `git add` prepara i file modificati per il commit.
- `git commit` registra una versione della modifica nel repository locale.
- `git push` pubblica il branch sul repository remoto.

## 5. Pull Request e controllo del PM

Dopo il push, lo sviluppatore apre GitHub e crea una Pull Request selezionando:

- **base:** `main`
- **compare:** il proprio branch.

La persona che svolge il ruolo di revisione controlla il riepilogo e le differenze di codice, lascia eventuali commenti, richiede le correzioni necessarie e solo dopo approva e integra la modifica con **Merge pull request**. Nel lavoro in coppia, i ruoli operativi possono essere svolti dai due partecipanti.

Se una correzione è richiesta, lo sviluppatore non deve aprire una nuova Pull Request: modifica ancora lo stesso branch, esegue un nuovo `git add`, `git commit` e `git push`. La Pull Request aperta si aggiorna automaticamente.

## 6. Aggiornamento delle copie locali dopo il merge

Dopo che le Pull Request sono state integrate, entrambi i partecipanti aggiornano la propria copia:

```bash
git switch main
git pull origin main
```

`git pull` scarica e integra nella copia locale gli aggiornamenti presenti nel branch remoto `main`.

Per vedere i branch remoti:

```bash
git fetch origin
git branch -a
```

## 7. Come gestire un conflitto

Un conflitto può verificarsi quando due sviluppatori modificano la stessa riga o la stessa parte di un file partendo dalla stessa versione.

Procedura da terminale per lo sviluppatore che deve aggiornare il proprio branch:

```bash
git switch nome-del-proprio-branch
git fetch origin
git merge origin/main
```

Se Git segnala un conflitto:

1. Aprire il file indicato da Git.
2. Cercare i marcatori `<<<<<<<`, `=======` e `>>>>>>>`.
3. Scegliere e combinare correttamente le modifiche.
4. Rimuovere i marcatori di conflitto.
5. Salvare il file e registrare la risoluzione:

```bash
git add index.html
git commit -m "Risolto il conflitto in index.html"
git push
```

La Pull Request può quindi essere ricontrollata e integrata.

## 8. Operazioni che risultano registrate in questo repository

Le seguenti attività sono visibili nella cronologia pubblica del repository:

- Repository pubblico con `index.html`, `style.css` e `README.md`.
- Tre branch iniziali: `menuPizza`, `menuDolci`, `menuBibite`.
- Tre ulteriori branch per la seconda tornata: `menuPizza-secondo-item`, `menuDolci-secondo-item`, `menuBibite-secondo-item`.
- Aggiunta di Quattro formaggi, Crostata e Succo di frutta nella prima tornata.
- Aggiunta di Diavola con illustrazione, Panna cotta e Limonata nella seconda tornata.
- Commento di revisione didattica sulla PR #4 e successiva correzione dell'immagine nello stesso branch.
- Otto Pull Request (#1–#8) integrate in `main`.
- Due branch concorrenti che hanno modificato la descrizione della Cola: dopo il merge della PR #7, GitHub ha rilevato il conflitto sulla PR #8. La risoluzione ha mantenuto la descrizione della Cola classica e aggiunto, separatamente, la disponibilità della variante senza zucchero. La PR #8 è stata quindi integrata.

## 9. Attività da completare sui computer dei due partecipanti

Il repository remoto contiene il lavoro e la cronologia descritti sopra. Per completare la parte distribuita, il proprietario deve ancora invitare il secondo partecipante usando il suo nome utente GitHub effettivo. Il secondo partecipante dovrà accettare l'invito, eseguire `git clone` e, dopo i merge, entrambi dovranno eseguire `git pull origin main` sui rispettivi computer. Queste operazioni locali non possono essere eseguite dal repository remoto.

## 10. Funzioni GitHub citate nell'esercitazione

Nella pagina del repository sono disponibili le sezioni principali di GitHub, tra cui **Code**, **Issues**, **Pull requests**, **Actions**, **Projects**, **Wiki**, **Security** e **Insights**. Sono aree con funzioni diverse: codice e branch, segnalazioni, revisioni, automazioni, pianificazione, documentazione e analisi del repository.
