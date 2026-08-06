---
name: weiterimtext
description: >-
  Mitten in der Sitzung verwenden, um sauber von einer eben gemergten Änderung zur nächsten Aufgabe
  zu kommen - die Naht zwischen zwei Arbeitseinheiten und das Gegenstück zu moin (Hochfahren) und
  feierabend (Herunterfahren). Bestätigen, dass die Änderung wirklich gelandet ist, den Branch
  ordnen, die lebenden Dokumente nachziehen, dann die nächste Aufgabe gegen die aktuelle
  Wirklichkeit prüfen und sie NUR beginnen, wenn sie wirklich bereit und entscheidungsfrei ist;
  sonst die Entscheidung vorlegen und anhalten.
---

# Nach dem Merge — die Naht zwischen zwei Arbeitseinheiten

*Setzt die Regeln S1, S2, G1 und C4 um. Der Katalog unter
`E:\My Projects\agent-project-rules\method\rules.md` ist die Autorität; diese
Datei ist nur die Prozedur.*

Zwischen dem Abschluss einer Arbeitseinheit und dem Beginn der nächsten liegt
eine Naht, und an der Naht geht es still schief: ein Branch bleibt hängen,
`STATUS.md` driftet ab, oder die Aufgabe, die du im Kopf hattest, ist längst
erledigt.

Das hier läuft **mitten in der Sitzung** und ist deshalb bewusst leicht. Du bist
schon orientiert — brief das Projekt, seine Geschichte und seine Regeln nicht
noch einmal.

## Das Prinzip: Kontext behalten, Welt neu prüfen

Der Kontext, den du in dieser Sitzung aufgebaut hast — die Entscheidungen, die
Begründungen, das Warum — ist ein **Wert. Behalte ihn.** Diese Prozedur
verlangt nicht, ihm zu misstrauen oder bei null anzufangen.

Was sich außerhalb deiner Kontrolle ändert, ist der **geteilte, äußere
Zustand**: `main`, die offenen Pull Requests, Zuschnitt und Stand der Tickets,
die Dateien auf dem Remote. Also ist die Disziplin eng und konkret: **bevor du
in ein geteiltes Artefakt schreibst oder dich auf die nächste Aufgabe festlegst,
hol den äußeren Zustand neu und prüf ihn.**

Der Unterschied ist wichtig. Den eigenen Kontext aus Vorsicht wegzuwerfen kostet
alles, was du erarbeitet hast, und verhindert nichts.

**Leitplanken (nicht verletzen):**

- **Autonomie mit Tor — der springende Punkt.** Die Schritte 1 bis 3 laufen
  autonom. Der Beginn der nächsten Aufgabe in Schritt 5 nicht. Fang nur an, wenn
  die Aufgabe wirklich bereit und entscheidungsfrei ist. Braucht sie ein Urteil,
  das Daniel gehört, ist sie zu groß, um ohne abgestimmte Form zu starten, oder
  ist sie mehrdeutig — **halt an und frag.**
- **Merge nie.** Das hier läuft *nach* einem Merge, den jemand anders gemacht
  hat. Schritt 1 prüft das; wenn es nicht passiert ist, hält das hier an.
- **Schreib nie auf `main`.** Jede Änderung, auch das Nachziehen der Dokumente
  in Schritt 3, geht über einen Pull Request wie jede andere. Technisch hindert
  dich nichts daran — auf `main` liegt kein Schutz.

## 1. Ist die Einheit wirklich geschlossen?

Räum nichts auf, was nicht fertig ist. Erst `git fetch`, dann den echten Zustand
lesen statt ihn anzunehmen:

- Bestätige, dass die Änderung **tatsächlich gemergt** ist — nicht bloß
  eröffnet, genehmigt oder grün.
- Ist sie es nicht, oder liegt nicht committete Arbeit herum, die nicht dazu
  gehörte: **halt hier an.** Berichte den echten Zustand und lass Daniel ihn
  auflösen. Aufräumen auf falscher Annahme vernichtet Arbeit.

## 2. Branch-Hygiene

Auf den gemergten Stand synchronisieren, den gemergten Branch lokal löschen,
Remote-Tracking-Branches prunen. Ende auf `main` mit sauberem Arbeitsbaum.

## 3. Die lebenden Dokumente nachziehen — nach erneuter Prüfung

Die fertige Änderung kann verändert haben, was wahr ist; eine **parallele**
Änderung kann es schon festgehalten haben. Also vor dem Schreiben neu prüfen:

- Lies `10 Method/STATUS.md` im **aktuellen** Stand auf dem frisch
  synchronisierten `main`, zusammen mit den letzten Merges und offenen Pull
  Requests. Hat eine andere Sitzung es schon nachgezogen, mach es nicht doppelt
  — vermerk es und geh weiter.
- Nur wenn es wirklich veraltet ist: `STATUS.md` und jedes andere betroffene
  lebende Dokument aktualisieren. Das ist eine normale Änderung über einen Pull
  Request, auf ein Anliegen beschränkt.
- Ein Eintrag in `10 Method/method-log.md` nur bei einem echten methodischen
  Moment. Nicht bei Routineausführung.

## 4. Die nächste Aufgabe gegen die Wirklichkeit prüfen

Nimm den einen klarsten nächsten Schritt aus `10 Method/STATUS.md` — behandle
den Plan, den du dir vorher gemacht hast, aber als **Hypothese**:

- **Immer noch der richtige nächste Schritt?** Oder hat sich die Reihenfolge
  verschoben, oder gibt es jetzt einen Defekt, der vorgeht?
- **Schon erledigt oder hinfällig?** Lies den aktuellen Stand des Tickets.
- **Voraussetzungen erfüllt?** Steht wirklich, worauf sie aufbaut?
- **Ist eine Entscheidung offen?** Dann greift das Tor unten.

## 5. Sauber anfangen — oder anhalten

- **Bereit und entscheidungsfrei:** frischen Branch von aktuellem `main`
  abzweigen und anfangen, mit dem vollen Sitzungskontext im Rücken.
- **Das Tor hat ausgelöst:** **nicht** anfangen. Leg die konkrete Entscheidung
  oder die nötige Planung vor, empfiehl eine Voreinstellung, und warte. Die
  nächste Aufgabe zu beginnen ist es nie wert, die Review-Grenze zu untergraben.

So oder so: berichte den Übergang knapp — was geschlossen wurde, was die
Dokumente jetzt sagen, und entweder was du begonnen hast oder was eine Antwort
braucht.
