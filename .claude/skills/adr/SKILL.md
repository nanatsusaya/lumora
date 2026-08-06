---
name: adr
description: >-
  Verwenden, wenn eine neue Entscheidungsakte geschrieben wird oder eine geplante ausgefüllt wird.
  Deckt ab: die Änderung einordnen - neu, Ergänzung oder Ablösung -, den Zyklus Branch → Proposed →
  Review mit offenen Fragen → Accepted → Merge, und das Nachziehen von Index und Status. Nicht für
  inhaltliche Vault-Arbeit.
---

# Eine Entscheidungsakte schreiben

*Setzt die Regeln D1, D2, D3 und G2 um. Der Katalog unter
`E:\My Projects\agent-project-rules\method\rules.md` ist die Autorität; diese
Datei ist nur die Prozedur.*

Eine Entscheidung zu verfassen ist eine wiederholbare Prozedur. Halte dich genau
daran: Entscheidungen sind **normativ**, und alles später Gebaute steht darauf.

Es bleibt eine *Entscheidungsakte*, nie eine heimliche Umsetzung. Wird ein
Abschnitt zum Entwurfsdokument, gehört der Entwurf woandershin, und diese Datei
soll sagen, welche Wahl getroffen wurde und warum die Alternativen es nicht
wurden.

**Was hier nicht hingehört: Lumora selbst.** Die Urgesetze des Kanons, die
noetischen Regeln, die Kosmologie sind Aussagen darüber, *was in dieser Welt
wahr ist*. Sie sind Inhalt und liegen in `01 Kern von Lumora` und `02`–`03`.
Prüfstein: eine Kanon-Regel gälte nicht mehr, wenn Lumora eine andere Welt
erzählte; eine Akte hier gälte weiter.

**Leitplanken (nicht verletzen):**

- **Beantworte die offenen Fragen nicht selbst.** Sie stehen da, weil sie Daniel
  gehören.
- **Ändere keine angenommene Akte.** Siehe Schritt 1.
- **Setz nicht um, worüber diese Akte noch entscheidet.**

## 0. Erst den Boden lesen

- `10 Method/STATUS.md` — der aktuelle Stand und was diese Entscheidung
  freischalten soll.
- `10 Method/ADR/ADR.md` — die Statuswerte, die nächste freie Nummer und die
  **Form einer Akte**. Der Index ist dafür die einzige Autorität; diese Prozedur
  wiederholt sie absichtlich nicht, weil zwei Beschreibungen einer Form sich
  nicht einig bleiben.
- Das zugehörige Ticket, falls es eins gibt: Kontext, Zuschnitt, Kriterien.
- **Jede angenommene Akte, auf der diese aufbaut oder die sie berührt.**
  Tatsächlich lesen, nicht aus dem Gedächtnis paraphrasieren.
- `CLAUDE.md`, besonders die Liste dessen, wobei anzuhalten und zu fragen ist.

## 1. Die Änderung einordnen

- **Eine neue Entscheidung** → eine neue Akte unter der nächsten freien Nummer.
  Nummern werden nie wiederverwendet.
- **Eine Änderung an einer angenommenen Entscheidung** → **anhalten und
  fragen.** Eine angenommene Entscheidung ist unveränderlich, außer mit
  ausdrücklicher Zustimmung, die im Abschnitt *Amendments* dieser Akte
  festgehalten wird, mit dem abgelösten Wortlaut wörtlich zitiert. Ohne diese
  Zustimmung braucht eine geänderte Entscheidung eine **ablösende** Akte, keine
  Bearbeitung.
- **Ablösung** → eine neue Akte, die benennt, was sie ablöst; der Status der
  alten wird auf `Superseded` gesetzt, in der Datei **und** im Index.

Die vier Statuswerte sind `Proposed`, `Accepted`, `Superseded` und `Planned` —
englische Wörter in deutschen Sätzen, weil sie das sind, was in die Datei
getippt wird. Eine `Planned`-Zeile darf noch keine Datei haben; jede andere muss
eine haben.

## 2. Branch und Dateien

- Von aktuellem `main` abzweigen.
- Die Akte mit `Status: Proposed` anlegen, benannt `NNNN-kurzer-titel.md`.
  `Proposed` bleibt sie nur, solange die offenen Fragen offen sind; Schritt 5
  kippt das, auf diesem Branch.
- Ihre Zeile **in derselben Änderung** in den Index eintragen. Eine nicht
  gelistete Akte ist für den Prüfer und für die nächste Sitzung unsichtbar.

Geschrieben wird wie jede Vault-Datei: Python mit `encoding='utf-8'`, kein
`Edit`-Tool, kein `sed`, Verifikation im selben Codeblock.

## 3. Was in den Körper gehört

Die Reihenfolge der vier Abschnitte steht in `10 Method/ADR/ADR.md`. Was diese
Prozedur dazu sagt, ist der Anspruch an ihren Inhalt:

1. **Context** — die Kräfte, und was eine frühere Entscheidung schon festgelegt
   hat gegenüber dem, was wirklich offen ist. Stell das Problem so dar, dass
   auch wer mit dem Ergebnis nicht einverstanden ist noch sieht, dass es das
   richtige Problem war.
2. **Decision** — was gilt. **Bevorzuge Formulierungen, die etwas prüfen
   könnte**: eine Wahl, über deren Geltung ein Befehl entscheiden kann, wird zur
   Prüfung; eine Wahl, die als Prinzip formuliert ist, wird zur Folklore.
3. **Consequences** — positive **und** negative, ehrlich. Eine Akte ohne
   negative Folgen ist nicht durchdacht, und der Leser merkt es.
4. **Alternatives considered** — jede mit einem Satz „abgelehnt, weil".

Braucht die Akte offene Fragen, kommen sie als `O1..On` ans Ende, jede mit einer
empfohlenen Voreinstellung. **Beantworte sie nicht.**

## 4. Zum Review stellen

Die Beschreibung des Pull Requests sagt was, warum, welchem Ticket oder welcher
Entscheidung es folgt, was es berührt und wie es geprüft wurde. **Stell die
offenen Fragen prominent heraus** — eine nummerierte Liste, die in Prosa
vergraben ist, wird teilweise beantwortet, und niemand merkt, welche übrig
blieben.

## 5. Wenn die Fragen beantwortet sind

Arbeite die Antworten in die Abschnitte ein, dann mach aus *Open questions*
**Resolved questions** mit `R1..Rn` — was entschieden wurde und warum.

Jetzt `Proposed → Accepted` kippen, in **Akte und Index**, **auf demselben
Branch, vor dem Merge.** Die Fragen sind beantwortet, und der Merge ist es, der
die Entscheidung annimmt — also ist der Status, den die Änderung hineinträgt,
der Status, der im Moment des Landens stimmt.

Heb das Kippen nicht für eine zweite Änderung auf. Zwischen den beiden Merges
stünde auf `main` `Proposed` über eine Entscheidung, die tatsächlich angenommen
ist — veraltete Dokumentation, die C4 einen Defekt nennt und keine Unordnung.

## 6. Nach dem Merge

`main` synchronisieren, den Branch löschen, und `10 Method/STATUS.md`
aktualisieren, wenn sich dadurch geändert hat, was als Nächstes passiert.

Denk daran: **angenommen heißt entschieden, nicht umgesetzt.** Der Status sagt
nichts darüber, dass es die Sache gibt.

## Bevor du zum Review stellst

- Trifft jeder Abschnitt unter *Decision* wirklich eine *Entscheidung*, oder
  gibt einer nur einen Überblick?
- Ist jede Abhängigkeit von einer anderen Akte mit Abschnitt zitiert?
- Sind die negativen Folgen echte, oder Beruhigung?
- Hätte sich eine der Entscheidungen so formulieren lassen, dass ein Befehl sie
  prüfen kann?
- Gehören die offenen Fragen wirklich Daniel — und sind sie unbeantwortet?
- Gibt es die Indexzeile, mit dem richtigen Status?

## Bevor es gemergt wird

- Sind aus den offenen Fragen **Resolved questions** mit `R1..Rn` geworden?
- Steht `Accepted` in der Akte **und** im Index, sodass nichts einer
  Folgeänderung überlassen bleibt?
- Läuft `node "../agent-project-rules/checks/check-method.mjs" .` grün? Der
  Prüfer vergleicht Aktenstatus gegen Indexstatus; genau das ist der Fehler, den
  niemand von Hand findet.
