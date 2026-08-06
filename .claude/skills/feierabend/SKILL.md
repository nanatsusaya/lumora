---
name: feierabend
description: >-
  Am Ende einer Arbeitssitzung verwenden, um sauber herunterzufahren: den Zustand des Branches
  ordnen, angefangene Arbeit abschließen oder ehrlich parken, die lebenden Dokumente auf Stand
  bringen und eine Übergabe schreiben. Diese Prozedur ist ein Herunterfahren, KEIN Startsignal für
  neue Arbeit. Das Gegenstück zu moin.
---

# Sitzungsende — Herunterfahren

*Setzt die Regeln S1, S3, W1 und H1 um. Die Autorität ist der
Regelkatalog von **agent-project-rules** (`method/rules.md` unter
`https://github.com/nanatsusaya/agent-project-rules`), der **nicht** in diesem
Repository liegt. Diese Datei ist nur die Prozedur.*

Eine Sitzung sauber zu schließen ist eine Prozedur. Das Ziel ist, Repository und
Übergabe an einem **ehrlichen Haltepunkt** zu hinterlassen: Was wirklich fertig
ist, ist fertig; was unfertig ist, ist sichtbar geparkt und übergeben.

Arbeite die Schritte der Reihe nach ab und **berichte wahrheitsgemäß** — ein
übersprungener Schritt oder ein roter Prüflauf wird benannt, nie beschönigt. Die
nächste Sitzung hat dieses Repository und sonst nichts; was du nicht
aufschreibst, ist verloren.

**Leitplanken (nicht verletzen):**

- **Fang nichts Neues an.** Taucht eine Aufgabe auf, halte sie fest. Beginne sie
  nicht.
- **Merge nie**, und schreib nie auf `main`. Berichte, was auf Review wartet.
  Auf `main` liegt kein technischer Schutz — diese Grenze hält nur, weil du sie
  hältst.
- **Runde kein Teilergebnis zu einem fertigen auf.** Ein ehrliches „dieser Teil
  ist nicht fertig" kostet einen Satz; die Alternative kostet mit Zinsen.

## 1. Branch-Hygiene

- Prüfe auf nicht committete Arbeit. Was im Arbeitsbaum liegt, ist entweder
  **fertig** (Schritt 2), auf einem Branch **geparkt** mit einem klaren
  WIP-Commit, oder ausdrücklich in der Übergabe benannt. Lass nichts unerwähnt
  hängen.
- Wurde in dieser Sitzung etwas gemergt: `main` synchronisieren, den gemergten
  Branch löschen, `git remote prune`.
- Liste jede Änderung, die noch auf Review wartet, mit ihrem Zustand.
- Ende auf `main` mit sauberem Arbeitsbaum — es sei denn, ein Branch ist bewusst
  geparkt und in der Übergabe benannt.

## 2. Abschließen, was abschließbar ist

Die Definition von *fertig* steht nicht hier, sondern in
`.github/ISSUE_TEMPLATE/task.md` (*Ready when* / *Done when*). Eine zweite Kopie
davon wäre eine zweite Autorität. Zusätzlich gilt für dieses Projekt:

- Jede geschriebene Datei wurde **vollständig zurückgelesen** — nie `tail`, nie
  „der Editor hat nicht gemeckert" —, auf Nullbytes geprüft und darauf, dass ein
  `str.replace()` sein Muster tatsächlich gefunden hat.
- Arbeit und Dokumentation haben sich zusammen geändert. Veraltete Dokumentation
  ist ein Defekt, keine Unordnung.
- Erkläre eine Aufgabe nur dann für erledigt, wenn du sie für richtig,
  vollständig und unschädlich hältst. Wenn nicht: parken und die **konkrete**
  Unsicherheit übergeben — was genau ungeprüft ist und was es klären würde.

## 3. Die lebenden Dokumente auf Stand bringen

- **`10 Method/STATUS.md`:** Datum, *Where we stand* und *Next step*
  auffrischen, wenn die Sitzung sie verändert hat. Mach das Offene ehrlich:
  wartende Änderungen, geparkte Arbeit, der eine klarste nächste Schritt. Eine
  beantwortete Frage `O1..On` kommt hier **raus** — eine gelöste Frage, die
  stehen bleibt, wird als offen gelesen.
- **`10 Method/method-log.md`:** nur bei einem echten methodischen Moment — eine
  Korrektur samt Begründung, ein Experiment in der Arbeitsweise und sein
  Ausgang, ein Fehler, den man nicht wiederholen will. Der Test: *würde ein
  Agent ohne Erinnerung an diese Sitzung ohne diesen Eintrag schlechter
  entscheiden?* Routineausführung ist das, wofür es die Commit-Historie gibt.
- **Gedächtnis**, falls vorhanden: dauerhafte Fakten sichern. Nicht, was das
  Repository ohnehin festhält, und nicht, was nur für dieses Gespräch galt.

Beides sind Änderungen an Vault-Dateien und laufen unter denselben
Schreibregeln: Python mit `encoding='utf-8'`, Verifikation im selben Codeblock.

## 4. Den Prüfer laufen lassen

Wurde in dieser Sitzung an `method.json`, an `10 Method/` oder an `CLAUDE.md`
gearbeitet, lauf den Kohärenzprüfer, bevor du übergibst.

Der Prüfer liegt **nicht** in diesem Repository, sondern unter
`https://github.com/nanatsusaya/agent-project-rules`. Auf diesem Rechner steht ein
Clone neben dem Vault-Ordner, dann läuft aus der Vault-Wurzel:

```
node "../agent-project-rules/checks/check-method.mjs" .
```

Das ist eine Konvention, keine Zusicherung. **Findest du ihn nicht, schreib in
die Übergabe, dass die Prüfung nicht laufen konnte** — nie, dass sie grün war.

Als eigenen Befehl, nicht in eine Pipeline gehängt: eine Pipeline meldet den
Exitcode des letzten Befehls, und wer die Ausgabe kürzt, versteckt den
Fehlschlag. Berichte, was er sagt — einschließlich dessen, was er **nicht**
geprüft haben will.

## 5. Übergabe und Schluss

Gib eine knappe Zusammenfassung: was erreicht wurde, was offen ist (wartende
Änderungen, geparkte Arbeit) und der eine klarste nächste Schritt für die
nächste Sitzung.

Dann halt an. Fang nichts Neues an.
