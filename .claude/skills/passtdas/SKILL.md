---
name: passtdas
description: >-
  Verwenden, um zu prüfen, ob method.json noch zu der Art passt, wie hier tatsächlich gearbeitet
  wird - und, falls die Methode in ein Projekt erst eingeführt werden soll, um das vorzuschlagen.
  Ordnet die Dateien des Projekts den vier Rollen zu, benennt die Regeln, die für diese Art Projekt
  umgeformt werden müssen, schreibt die Deklaration mit ihren Anpassungen und lässt den
  Kohärenzprüfer laufen. Endet mit einem Vorschlag zur Entscheidung.
---

# Passt die Methode noch?

*Setzt die Regeln A1, A2 und C1 um. Die Autorität ist der
Regelkatalog von **agent-project-rules** (`method/rules.md` unter
`https://github.com/nanatsusaya/agent-project-rules`), der **nicht** in diesem
Repository liegt. Diese Datei ist nur die Prozedur.*

Dieses Projekt hat eine `method.json`. Der übliche Fall ist deshalb die
**Überprüfung**, nicht die Einführung: Passt, was dort steht, noch zu dem, wie
hier tatsächlich gearbeitet wird? Der Einführungsfall steht am Ende, für den
Fall, dass diese Prozedur in ein anderes Projekt kopiert wird.

Auch eine Überprüfung ist ein Vorschlag. Wie die Methode hier aussieht, ist eine
Entscheidung über die Arbeitsweise dieses Projekts, und die gehört Daniel.

**Leitplanken (nicht verletzen):**

- **Vorschlagen, nicht verordnen.** Leg die Bindungen und Anpassungen vor, die
  du ändern willst, und hol eine Entscheidung, bevor du schreibst.
- **Erfinde keine Rolle, die es nicht gibt.** Ein leeres Verzeichnis ist kein
  Fortschritt.
- **Übernimm keine Regel, die du hier nicht begründen kannst.** Eine Regel, die
  dort angewandt wird, wo ihre Begründung nicht trägt, kostet dasselbe und
  bringt nichts — und der vergeudete Aufwand lehrt alle, dass die Methode
  Bürokratie ist.
- **Behaupte nie, der Prüfer sei durchgelaufen, ohne ihn laufen zu lassen.**
- **Weite niemals eine Anpassung, um einen echten Defekt zuzudecken.**

## 1. Den Ist-Zustand lesen

- `method.json`: die vier Bindungen, die `authorities`, die `language`, die
  `ignore`-Liste, die Anpassungen mit Grund und Datum.
- Die vier gebundenen Artefakte. Gibt es sie noch, sind sie gefüllt, sagen sie
  noch, was sie sagen sollen?
- Was sich seit der letzten Überprüfung geändert hat: neue Ordner, ein
  verschobener Schwerpunkt, ein Werkzeug, das dazugekommen ist.

## 2. Die Fragen, an denen eine Deklaration veraltet

- **Stimmen die Rollen noch?** Ein Artefakt, das umbenannt oder verschoben
  wurde, bricht die Bindung, und der Prüfer sagt es.
- **Ist eine Anpassung überholt?** Ihr Grund kann weggefallen sein. Eine
  Anpassung, deren Begründung nicht mehr trägt, ist eine abgeschaltete Prüfung
  ohne Rechtfertigung. Für dieses Projekt sind das zwei:
  - **L1 `narrowed`** — hängt daran, dass der deutsche Korpus unter
    amerikanischer Rechtschreibung wenige Befunde erzeugt. Miss das nach, statt
    es anzunehmen.
  - **G1 `narrowed`** — hängt daran, dass auf `main` kein Schutz liegt. Wird je
    ein Ruleset eingerichtet, gehört die Anpassung zurückgenommen und
    `authorities.gate` gesetzt.
- **Ist `ignore` noch leer?** Sie soll es sein. `ignore` nimmt Dokumente aus
  *jeder* Prüfung, nicht nur aus der Rechtschreibung — auch aus dem Link- und
  dem Withdrawn-Scan. Wächst die Liste, wächst ein blinder Fleck.
- **Ist `language.allow` noch kurz?** Eine Freistellung ist ein Loch, und der
  Prüfer nennt jedes in jedem Bericht beim Namen. Zwei Wörter kann man prüfen.
- **Ist die Katalogversion noch aktuell?** Steht in `method/VERSION` im
  Katalog-Repository (siehe unten). Ist der Katalog nicht erreichbar, ist die
  Frage offen und nicht beantwortet.

## 3. Den Prüfer laufen lassen

Katalog und Prüfer liegen **nicht** in diesem Repository, sondern unter
`https://github.com/nanatsusaya/agent-project-rules`. Auf diesem Rechner steht ein
Clone neben dem Vault-Ordner, dann läuft aus der Vault-Wurzel:

```
node "../agent-project-rules/checks/check-method.mjs" .
```

Das ist eine Konvention, keine Zusicherung — nichts im Repository erzwingt, wo
der Clone liegt oder dass es einen gibt. **Findest du ihn nicht, berichte, dass
die Prüfung nicht laufen konnte**, und halt an: eine Überprüfung ohne Prüfer ist
eine Behauptung. Als eigenen Befehl, nicht in eine Pipeline gehängt.

Berichte, was er sagt — **einschließlich dessen, was er nicht geprüft haben
will**, und einschließlich der Zahl gelesener Verweise. Liest er null Verweise,
ist ein grüner Lauf ein stiller Leerlauf und beweist nichts.

Ein grüner Lauf allein beweist auch nichts über die Anpassungen (E3). Wer eine
Anpassung ändert, testet sie gegen: Verstoß einbauen, Fehlschlag bestätigen,
zurücknehmen.

## 4. Den Vorschlag vorlegen und warten

Zeig Daniel:

- welche Datei welche Rolle spielt, und welche Rolle ungebunden ist
- jede Regel, die du verengen, fallenlassen, ersetzen oder aufschieben willst,
  mit ihrem Grund
- was angelegt werden müsste, und was du **nicht** anzulegen vorschlägst
- alles, was die Methode einen Defekt nennen würde — ein Fakt mit zwei
  Autoritäten, eine Regel an zwei Stellen, Dokumentation, die Wissen
  voraussetzt, das nicht mehr im Repository steht

Dann halt an und warte. Schreib noch keine Datei.

## 5. Erst danach schreiben

Ist die Form abgestimmt, schreib die Änderung an `method.json` und an den
Artefakten. Vier Arten von Anpassung gibt es: `dropped`, `narrowed`, `replaced`,
`deferred`. **Nur `narrowed` lässt die zugehörige Prüfung weiterlaufen** — die
anderen drei schalten sie ab, und auch das nur, wenn der Eintrag vollständig ist
(Grund und ISO-Datum).

`CLAUDE.md` **nennt die Regeln, statt auf sie zu verlinken**: ein Agent, der
eine Aufgabe bearbeitet, hat dieses Repository und sonst nichts, und eine
Anweisung, etwas Externes abzurufen, ist ein Abruf, der scheitern, blockiert
oder übersprungen werden kann.

Wie jede Änderung geht auch diese über einen Pull Request. Auf `main` liegt kein
Schutz — diese Grenze hält nur, weil du sie hältst.

## Der Einführungsfall

Gibt es keine `method.json` — also in einem anderen Projekt, in das diese Datei
kopiert wurde:

1. **Lies das Projekt erst.** Was ist es, für wen, und was wäre ein Scheitern?
   Code mit Build-Kette oder ein Textkorpus? Wie lange läuft es? Was gibt es
   schon an Betriebsregeln, Entscheidungen, Status, Log?
2. **Bilde das Vorhandene auf die vier Rollen ab.** Binde lieber an etwas, das
   es gibt, als eine Datei anzulegen. Eine Rolle, die das Projekt wirklich nicht
   nutzt, wird an `null` gebunden **und** als Anpassung erklärt; sie
   stillschweigend wegzulassen ist das Einzige, was nicht erlaubt ist.
3. **Trag die `authorities` ein:** wo die Review-Grenze konfiguriert ist, wo die
   Tickets liegen, was nach Zugangsdaten sucht. Alle drei sind optional. Es sind
   Adressen, die ein Mensch liest, nie etwas, das ein Agent abruft.
4. **Ordne das Projekt einem Archetyp zu** — `method/adapting.md` im Katalog —
   und schreib für jede Regel, die du ändern willst, den Grund als Satz, nach
   dem ein Fremder handeln könnte. „Nicht anwendbar" ist kein Grund.

Danach weiter bei Schritt 4 oben.
