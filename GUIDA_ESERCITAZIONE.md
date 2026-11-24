# Guida completa – esercitazione GitHub Flow

Questa guida riassume il flusso del Project Manager e dei tre sviluppatori e contiene i comandi da eseguire nei rispettivi computer.

Repository remoto: https://github.com/Leonardogandini-2008/progetto-pizzeria

## 1. Ruoli del gruppo

Il gruppo è composto da due persone:

- **Project Manager (PM):** crea il repository, prepara il file iniziale, invita i collaboratori, controlla le Pull Request e integra le modifiche.
- **Sviluppatore A:** realizza la sezione Pizze.
- **Sviluppatore B:** realizza la sezione Dolci.
- **Sviluppatore C:** realizza la sezione Bibite.

## 2. Preparazione del repository da parte del PM

1. Creare un repository GitHub pubblico chiamato `progetto-pizzeria`.
2. Inserire i file iniziali `index.html` e `style.css`.
3. Scrivere nel README lo scopo del progetto e le regole di collaborazione.
4. Aprire **Settings → Collaborators** (o **Collaborators and teams**) e scegliere **Add people**.
5. Cercare il nome utente GitHub di ciascuno dei tre sviluppatori e inviare l'invito.
6. Ogni sviluppatore deve accettare l'invito ricevuto da GitHub.

**Nota operativa:** gli inviti ai tre collaboratori vanno inviati dal proprietario del repository con il loro effettivo nome utente GitHub. Non sono stati inviati in questa esecuzione perché non erano disponibili i tre username e il collegamento GitHub utilizzato per il progetto non espone l'azione di amministrazione degli inviti.

## 3. Clone del repository

Ogni sviluppatore apre il terminale e lancia:

```bash
git clone https://github.com/Leonardogandini-2008/progetto-pizzeria.git
cd progetto-pizzeria
```

Il comando `clone` crea una copia locale del repository remoto.

## 4. Creazione dei branch e lavoro separato

Ogni sviluppatore lavora nel proprio branch, senza modificare direttamente `main`.

**Sviluppatore A – Pizze**

```bash
git switch -c menuPizza
# Modificare la sezione Pizze in index.html
git add index.html
git commit -m "Aggiunge una nuova pizza al menu"
git push -u origin menuPizza
```

**Sviluppatore B – Dolci**

```bash
git switch -c menuDolci
# Modificare la sezione Dolci in index.html
git add index.html
git commit -m "Aggiunge un nuovo dolce al menu"
git push -u origin menuDolci
```

**Sviluppatore C – Bibite**

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

Il PM controlla il riepilogo e le differenze di codice, lascia eventuali commenti, richiede le correzioni necessarie e solo dopo approva e integra la modifica con **Merge pull request**.

Se una correzione è richiesta, lo sviluppatore non deve aprire una nuova Pull Request: modifica ancora lo stesso branch, esegue un nuovo `git add`, `git commit` e `git push`. La Pull Request aperta si aggiorna automaticamente.

## 6. Aggiornamento delle copie locali dopo il merge

Dopo che il PM ha integrato le Pull Request, ciascuno sviluppatore aggiorna la propria copia:

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

## 9. Attività da completare sui computer del gruppo

Il repository remoto contiene il lavoro e la cronologia descritti sopra. Per rendere effettiva anche la parte distribuita su quattro computer, il PM deve ancora inviare gli inviti agli account reali dei tre sviluppatori e ognuno deve eseguire `git clone` e successivamente `git pull origin main` sul proprio computer. Queste operazioni locali non possono essere eseguite dal repository remoto.

## 10. Funzioni GitHub citate nell'esercitazione

Nella pagina del repository sono disponibili le sezioni principali di GitHub, tra cui **Code**, **Issues**, **Pull requests**, **Actions**, **Projects**, **Wiki**, **Security** e **Insights**. Sono aree con funzioni diverse: codice e branch, segnalazioni, revisioni, automazioni, pianificazione, documentazione e analisi del repository.
