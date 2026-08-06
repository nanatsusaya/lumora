---
name: moin
description: >-
  Am Anfang einer Arbeitssitzung verwenden, um sauber hochzufahren und sich zu orientieren: lesen,
  was dieses Projekt ist, welche Regeln gelten und welche Prozeduren es gibt, was zuletzt gearbeitet
  wurde und - vor allem - wo wir stehen und was der eine nächste Schritt ist, alles frisch aus den
  lebenden Dokumenten des Projekts gelesen. Diese Prozedur ist Orientierung, KEIN Startsignal für
  Arbeit - sie endet mit einer Frage, nicht mit einer Handlung. Das Gegenstück zu feierabend.
---

# Sitzungsbeginn — Hochfahren

*Setzt die Regeln S1, S2, S3 und H1 um. Die Autorität ist der
Regelkatalog von **agent-project-rules** (`method/rules.md` unter
`https://github.com/nanatsusaya/agent-project-rules`), der **nicht** in diesem
Repository liegt. Diese Datei ist nur die Prozedur.*

Eine Sitzung sauber zu beginnen ist eine Prozedur, nichts, was man aus dem
Gedächtnis rekonstruiert. Improvisiertes Hochfahren scheitert immer gleich:
Etwas wird übersprungen, und das Überspringen fällt nicht auf, weil es keine
Liste gab, von der man hätte überspringen können.

Arbeite die Schritte der Reihe nach ab. Lies jede Quelle **frisch** — traue
keinem Kontext, der von irgendwoher mitgebracht wurde — und **berichte
wahrheitsgemäß**: ein offener Pull Request, ein roter Prüflauf oder eine
liegengebliebene Aufgabe wird schlicht benannt.

**Leitplanken (nicht verletzen):**

- **Orientieren, nicht anfangen.** Das hier endet mit einer **Frage**, nie mit
  einer Handlung. Taucht im Briefing eine Aufgabe auf, benenne sie und warte.
  Wer eine Sitzung mit Arbeit eröffnet, wählt ihre Richtung anstelle von Daniel.
- **Nur lesen.** Keine Commits, keine Branches, keine Änderungen an lebenden
  Dokumenten.
- **Die lebenden Dokumente sind die Wahrheit über den Stand** — nicht diese
  Datei, nicht das Gedächtnis, nicht was letzte Sitzung galt.
- **Erfinde keinen Stand, den du nicht lesen konntest.** Fehlt ein Artefakt, sag
  dass es fehlt.

## 0. Die Artefakte finden

Lies `method.json` in der Wurzel des Vaults. Sie bindet vier Rollen an echte
Pfade:

| Rolle | Beantwortet | Datei |
|---|---|---|
| `operating-rules` | Wie wird hier gearbeitet? | `CLAUDE.md` |
| `decisions` | Was wurde entschieden, und warum? | `10 Method/ADR/` |
| `state` | Wo stehen wir? | `10 Method/STATUS.md` |
| `method-log` | Warum sieht die Arbeitsweise so aus? | `10 Method/method-log.md` |

Die Tabelle steht hier, weil sie sich selten ändert und ein Blick sie erspart —
maßgeblich ist trotzdem `method.json`. Weicht sie ab, gilt die Datei, und der
Widerspruch gehört gemeldet.

## 1. Was das hier ist

- Das Projekt und sein Ziel, aus dem Kopf von `CLAUDE.md`. Ein, zwei Sätze,
  keine Wand aus Text.
- Wie lange es schon läuft, aus dem Datum des ersten Commits.
- Nenne das Arbeitsverzeichnis, damit unzweifelhaft ist, um welches Projekt es
  geht.

## 2. Geltende Regeln und verfügbare Prozeduren

- Die tragenden Regeln aus `CLAUDE.md` — die, die prägen *wie* hier gearbeitet
  wird, nicht die ganze Datei. Eine knappe Erinnerung. Dazu gehören für dieses
  Projekt immer: die Schreibregeln für Vault-Dateien (kein `Edit`-Tool, kein
  `sed`, nur Python mit `encoding='utf-8'`, Verifikation im selben Codeblock)
  und dass `01 Kern von Lumora` unantastbar ist.
- Welche Prozeduren es gibt und wann man zu welcher greift: `/moin`,
  `/weiterimtext`, `/feierabend`, `/adr`, `/passtdas`.
- Die in `method.json` verzeichneten Anpassungen. Eine Regel, die dieses Projekt
  bewusst verengt oder fallengelassen hat, ist genau das, was eine frische
  Sitzung falsch macht. Hier sind es zwei: **L1** (der Vault ist deutsch, die
  steuernden Artefakte sind amerikanisches Englisch) und **G1** (auf `main`
  liegt kein Schutz).
- Die `authorities` aus derselben Datei. Lies sie, **rufe sie nicht ab**. Die
  Adresse zu kennen ist das, was diese Sitzung davor bewahrt, eine Frage zu
  stellen, die die letzte schon beantwortet hat.

## 3. Zuletzt gearbeitet

Die letzten abgeschlossenen Arbeitseinheiten. Da dieses Projekt fast
ausschließlich direkt auf `main` gearbeitet hat, sind das in der Regel schlicht
die letzten Commits. Ein methodischer Moment aus dem Methodenlog wird nur
erwähnt, wenn er heute etwas bedeutet.

## 4. Wo wir stehen

- **Zustand des Repositorys:** aktueller Branch, ob der Arbeitsbaum sauber ist,
  und jede Änderung, die auf Review wartet. Vorher `git fetch`, damit das den
  geteilten Stand zeigt und nicht eine veraltete lokale Sicht.
- **Zustand des Projekts:** der Abschnitt *Where we stand* aus
  `10 Method/STATUS.md`. Zusammenfassen, nicht hineinkopieren. Die offenen
  Fragen `O1..On` dort gehören ins Briefing, solange sie offen sind.

## 5. Der nächste Schritt

Aus `10 Method/STATUS.md` den **einen klarsten nächsten Schritt** benennen —
nicht die Roadmap — und dazu jede Entscheidung, die vorher fallen muss.

## 6. Mit einer Frage schließen

Liefere das Briefing knapp und ende mit der Frage, ob es wie geplant weitergeht
oder die Richtung wechselt.

Dann **halte an und warte.** Fang nichts an, bevor die Antwort da ist; die
Antwort setzt die Richtung der Sitzung.
