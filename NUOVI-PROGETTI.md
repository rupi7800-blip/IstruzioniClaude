# Come applicare le regole a un nuovo progetto

Le regole valgono solo nei progetti che contengono questi file nella radice:

- `CLAUDE.md` → le regole di consumo e ruoli
- `.claude/settings.json` → il modello principale (Sonnet)
- `.claude/agents/` → gli agenti `search`, `grep`, `audit`, `advisor`
- `.claude/commands/regole.md` → il comando `/regole`

Claude Code li legge da solo all'inizio di ogni sessione, ma **solo** se sono
nel ramo principale del progetto. Questo repository (IstruzioniClaude) è la
copia originale.

## Quando crei un nuovo progetto

1. Apri una sessione di Claude Code sul nuovo progetto, scegliendo Sonnet come modello.
2. Incolla come primo messaggio il testo di `REGOLE-DA-INCOLLARE.txt`.
   Claude applica subito le regole, copia i file da IstruzioniClaude nel
   progetto e apre la pull request. Se il progetto ha già un suo `CLAUDE.md`,
   le regole vengono aggiunte in fondo senza sostituirlo.
3. Su GitHub unisci la pull request nel ramo principale (di solito `main`).
4. Dalla sessione successiva le regole sono attive da sole: non serve più
   incollare il testo, basta `/regole` se vuoi richiamarle.

## Per controllare che funzionino

- In una sessione sul progetto scrivi `/regole`: Claude conferma le regole e le applica.
- Se `/regole` non esiste, i file non sono ancora nel ramo principale.

## Quando cambi una regola

1. Modifica i file qui, in IstruzioniClaude.
2. Chiedi a Claude:

   > Ricopia le regole aggiornate da IstruzioniClaude in tutti i miei progetti.

3. Unisci le pull request.

Le copie nei progetti non si aggiornano da sole.

## Cose da ricordare

- **Ramo principale**: le nuove sessioni partono dal ramo principale del
  progetto. In StockRadar, CryptoRadar e GFIP non è `main`: le regole vanno
  unite in quel ramo, oppure imposta `main` come ramo principale in
  GitHub → Settings → General → Default branch.
- **Modello**: `settings.json` imposta Sonnet, ma se all'apertura della sessione
  scegli un altro modello vale quello che scegli.
- **Pubblicazioni**: nei progetti che pubblicano sito o app dal ramo `main`,
  unire la pull request avvia una nuova pubblicazione (il contenuto non cambia).
- **Sul tuo computer** (Claude Code installato in locale) puoi anche copiare i
  file in `~/.claude/` (`CLAUDE.md`, `agents/`, `commands/`, `settings.json`):
  valgono per tutti i progetti di quel computer. Nelle sessioni cloud no.
