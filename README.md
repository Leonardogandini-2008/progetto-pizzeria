# Progetto pizzeria – esercitazione GitHub Flow

Sito didattico HTML/CSS della pizzeria **Bella Napoli**, realizzato da **due persone** per l'esercitazione sullo sviluppo collaborativo con Git e GitHub.

Il progetto è stato svolto in coppia: le tre sezioni Pizze, Dolci e Bibite sono aree funzionali del sito, non tre sviluppatori distinti.

## File del progetto

- `index.html`: struttura e contenuto del sito, organizzato in Pizze, Dolci e Bibite.
- `style.css`: grafica responsive per computer, tablet e smartphone.
- `images/pizza1.svg`: illustrazione della pizza Diavola.

## Menu presente in `main`

**Pizze:** Margherita, Marinara, Quattro formaggi, Diavola.

**Dolci:** Tiramisù, Crostata, Panna cotta.

**Bibite:** Acqua, Cola classica (con indicazione della variante senza zucchero), Succo di frutta, Limonata.

## Organizzazione del lavoro in coppia

Il progetto è stato realizzato da due persone:

- **Persona 1 – Coordinamento:** preparazione del repository, organizzazione del lavoro, controllo delle modifiche e integrazione in `main`.
- **Persona 2 – Sviluppo:** realizzazione e aggiornamento dei contenuti del sito, con lavoro su branch dedicati e invio delle modifiche tramite Pull Request.

Le sezioni Pizze, Dolci e Bibite sono state suddivise come parti funzionali del progetto e gestite dai due partecipanti; non rappresentano tre sviluppatori separati.

Branch creati durante il lavoro:
- `menuPizza`, `menuDolci`, `menuBibite`: prima tornata di modifiche.
- `menuPizza-secondo-item`, `menuDolci-secondo-item`, `menuBibite-secondo-item`: seconda tornata.
- `conflitto-cola-classica`, `conflitto-cola-zero`: prova di modifiche concorrenti sulla stessa riga.

## Pull Request integrate

- [PR #1 – nuova pizza](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/1)
- [PR #2 – nuovo dolce](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/2)
- [PR #3 – nuova bibita](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/3)
- [PR #4 – seconda pizza e immagine corretta dopo commento di revisione](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/4)
- [PR #5 – Panna cotta](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/5)
- [PR #6 – Limonata](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/6)
- [PR #7 – modifica concorrente della descrizione Cola classica](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/7)
- [PR #8 – risoluzione della modifica concorrente con variante senza zucchero](https://github.com/Leonardogandini-2008/progetto-pizzeria/pull/8)

Tutte le otto Pull Request risultano integrate in `main`.

## Procedura completa

Il file [GUIDA_ESERCITAZIONE.md](GUIDA_ESERCITAZIONE.md) contiene i passaggi per il Project Manager e i tre sviluppatori, i comandi Git per clone/branch/commit/push/pull e la procedura per gestire un conflitto.

## Come visualizzare il sito

Aprire `index.html` nel browser. I file HTML, CSS e SVG sono già nel repository.

## Nota

Progetto didattico: non contiene sistemi reali di prenotazione, ordinazione o pagamento.
