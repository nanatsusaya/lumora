---
tags:
  - meta
---
# Tags — Bedeutung & Verwendung

Diese Note erklärt die verwendeten Obsidian-Tags im Lumora-Vault und wann sie gesetzt bzw. entfernt werden.

---

## Konvention: *Tag:* und *Status:*

Jede benannte Sektion (mit eigenem Heading) kann zwei Metadaten-Zeilen direkt unter dem Titel tragen:

```
### Name der Sektion
*EN: English Name*        ← nur bei Eigenbegriffen
*Tag:* #section-id        ← genau ein Tag, Sektions-Identifier
*Status:* #wip #working-title   ← ein oder mehrere Status-Flags
```

`*Tag:*` identifiziert die Sektion eindeutig — immer genau ein Tag.
`*Status:*` beschreibt den Zustand der Sektion — kann mehrere Tags kombinieren.

---

## Tags

Im folgenden werden alle globalen Meta Tags beschrieben. Meta Tags beschreiben nicht ein spezielles Inlore Thema, sondern den Zustand eines Thema, eines Abschnitts oder einer Obsidian Notize. 

### #canon

Markiert Notes aus `01 Kern von Lumora` — das unveränderliche philosophische Fundament des Projekts. Diese Notes dürfen nicht geändert werden, um Story-Probleme zu lösen. Sie definieren, was Lumora ist und wofür es steht.

**Wann entfernen:** Nie. Canon bleibt Canon.

**Gesetzt bei:** Alle Notes in `01 Kern von Lumora`.

---

### #wip — Work in Progress

Markiert Notes oder Sektionen, die inhaltlich noch nicht abgeschlossen sind. Der Inhalt ist entweder:
- ein erster Transfer aus dem Archiv (noch nicht vollständig ausgearbeitet),
- strukturell angelegt aber inhaltlich lückenhaft, oder
- bewusst offen gelassen mit offenen TODO-Blöcken.

**Als Frontmatter-Tag:** Markiert die gesamte Note als unfertig.
**Als *Status:*-Tag einer Sektion:** Markiert genau diese Sektion als unfertig.

**Wann entfernen:** Wenn alle Sektionen einer Note `#ready` haben, wird `#wip` im Frontmatter durch `#ready` ersetzt.

**Nicht gesetzt bei:** `01 Kern von Lumora` (unveränderliches Fundament), `03.01 Noetisches System`, `03.02 Funktionsweise` (beide als stabil betrachtet).

**Suche in Obsidian:** `tag:#wip` zeigt alle unvollständigen Notes auf einen Blick.

---

### #ready

Markiert eine Sektion oder Note als inhaltlich abgeschlossen. Alle TODOs sind bearbeitet oder bewusst in offene Fragen umgewandelt, der Inhalt ist mit dem Rest des Vaults konsistent.

**Als *Status:*-Tag einer Sektion:** Diese Sektion gilt als fertig.
**Als Frontmatter-Tag:** Die gesamte Note gilt als fertig — nur setzen, wenn *alle* Sektionen `#ready` tragen.

**Wann setzen:** Wenn eine Sektion keine offenen TODOs mehr hat, inhaltlich vollständig ist und konsistent mit dem Rest des Vaults verlinkt ist.

---

### #working-title

Markiert Namen — von Göttern, Charakteren oder anderen benannten Entitäten — die noch keinen endgültigen Namen haben. Der aktuelle Name ist ein Arbeitstitel und wird im Laufe der Entwicklung ersetzt.

**Wann entfernen:** Wenn der Name final festgelegt und im Vault konsistent verwendet wird.

**Aktuell gesetzt bei:** Alle Götternamen (Ursprungsgott, Chaosgott, STG, Strippenzieher, Eldarigöttin, Wüstengott, Frosteldari-Pseudogott), alle Charakternamen (Protagonist, Der Junge).

---

### #meta

Markiert Notes, die den Vault selbst beschreiben — Konventionen, Tags, Projektstruktur. Kein Story-Inhalt.
