# LUMORA

> *No solution without foundation. No effect without cause. No power without limit.*

**Lumora** is the working title of a fantasy novel currently in development — a world built on a hard-magic system where the rules of physics are extended, not broken, and every effect has a cause.

This repository contains the Obsidian vault used for worldbuilding, lore, character development, and story architecture.

---

## Status

🚧 **Work in progress** — The world is being built. The story is taking shape.

The foundation (magic system, world physics, core philosophy) is largely defined. Characters, plot structure, and prose are next.

---

## About

**Author:** Daniel Wagner
**Contact:** herrdanielwagner@web.de

This is a personal creative project. The universe, its rules, and all ideas within are original and belong entirely to their creator.

---

## License

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This work is licensed under **[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/)**.

You are free to share and adapt this material for non-commercial purposes, as long as you give appropriate credit and distribute any derivative works under the same license. See the [LICENSE](LICENSE) file for the full terms.

© 2026 Daniel Wagner

---

```
Schau dir mal schnell den stand des Projekts an.

- Um was geht es in dem Projekt?
- Was haben wir die letzten 4 Tage gemacht?
- Welche dauerhaften Anweisungen hast du aktuell und warum hast du diese?
```

```
# LUMORA — Übergabe an nächsten Chat (Noetisches System, Behandlungsphase)

## Setup
- Projekt: Hard-Magic-Fantasy-Vault "Lumora". Lies zuerst E:\My Projects\Lumora\CLAUDE.md.
- Sprache: durchgehend Deutsch antworten.
- Aktueller Fokus: Erststand "03 Noetic System" abschließen.

## HARTE REGELN (zwingend)
- Vault-Markdown NIEMALS mit Edit-Tool oder sed bearbeiten. Immer Python mit
  explizitem UTF-8 (open(..., encoding="utf-8")).
- Nach JEDEM Schreiben im selben Codeblock verifizieren: Datei komplett zurücklesen,
  auf Null-Bytes prüfen (content.count(chr(0))==0), prüfen ob replace/Pattern wirklich
  gegriffen hat, auf Vollständigkeit/keine Duplikate prüfen. Bei Fehler sofort stoppen
  und melden.
- Daniel committet selbst. NIEMALS git commit ausführen.

## BEREITS BESCHLOSSEN DIESE SESSION (nicht umwerfen, nur konsistent halten)
1. Chronari/Tachyonen = "Zukunftsinterpretation", KEINE feststehende Zukunft.
   Tachyonen tragen Projektion gegenwärtiger Ursachen; Zukunft ist OFFEN; hohe Trefferquote
   wegen Trägheit großer Systeme. Nahbereich reflexhaft, Tage/Wochen nur im Ritual.
   Transzendierte deuten tiefer, nie Gewissheit, nie Problemlöser (kein Deus ex Machina).
   Geändert in: 03.06, 02.02. Lore-Sektion "Der Protagonist als unvorhergesehene Variable".
2. Energie-Doktrin: Die N-Kraft ist eine HEBELKRAFT. Sie liefert nicht selbst Energie,
   sondern beugt lokal die Wirkungsstärke (Kopplung) einer Fundamentalkraft; vorhandene
   Energie verrichtet die Arbeit. Kosten = Lieferkosten (eigene Energie -> Wucht, biologisch
   begrenzt) + Modulationskosten (Amplitude x Volumen x Dauer x Präzision -> Wucht/Wissen/
   Wille). Weiche Kräfte (Gravitation, EM) leicht beugbar; steife (stark/schwach Kernkraft)
   nur bei extremer Amplitude. Atomkern-Effekte erreichbar über: Quasi-Götter (kleiner
   Rahmen, Risiko), Kollektive/Engineering (Kristalltechnik, gebündelte Energie),
   Transzendierte. NICHT "nur transzendiert".
   Neue/geänderte Stellen: 03.01 (N-Kraft-Def), 03.02 (Subsektion "Modulation statt Arbeit"
   + neue Sektion "Kosten & Skalierung noetischer Effekte"), 03.03 (Sektion "Zusammenwirken
   der Dimensionen" gefüllt), 03.05 (Physikgrenze), 03.06 (Nuklear-Header "die steilste Stufe").
3. Thematische Wertung gehört NICHT ins Regelwerk (03.x), sondern in die Lore. Lore-Sektion
   "Der doppelte Auslöser der Geschichte": Eskalationsschwelle (System) + Drei Regeln (Lore)
   = warum die Story startet.

## OFFENE TODOS (mechanisch, in Reihenfolge)
1. EFFEKTLISTE 03.06 sortieren/klassifizieren nach der Hebel-Faustregel:
   "Billig = lenkt vorhandene Energie/Gradienten um. Teuer = muss Energie selbst liefern
   oder Konstante weit/großflächig/lange/scharf beugen."
   - Jeden Effekt knapp dieser Logik zuordnen (oder Tendenz markieren).
   - Frostpfeil/Körperkühlung etc.: Wärmesenke sauber formulieren (Wärme wird nicht
     vernichtet, sondern transferiert -> braucht Ziel/Gradient).
   - Konsistenz mit der Doktrin in 03.02 prüfen.
2. BUG 03.05, Abschnitt "### Hotspots": Der Fließtext beschreibt fälschlich die Ursachen
   SCHWACHER Felder ("Zwei Ursachen ... Schwaches lokales N-Feld / Schwache N-Kraft").
   Inhalt passt nicht zur Überschrift Hotspots -> korrigieren (Hotspots = starkes N-Feld,
   hohe Biomasse/Biodiversität).
3. DOPPELEINTRAG 03.06: "Aufmerksamkeitssuppression" existiert zweimal (einmal "Licht &
   Optik", einmal "Neurologie & Bewusstsein") mit abweichender Mechanik -> zusammenführen
   oder klar trennen/umbenennen.
4. GÖTTER-TERMINOLOGIE vereinheitlichen: "Pseudogott" (in 02.04, z.B. Eldarigöttin,
   Eisdrachen) vs. "Quasi-Gott" (in 03.04). Klären ob identisch; eine durchgängige Leiter
   definieren (Vorschlag: Pseudogott/Quasi-Gott = noch verkörpert -> jung transzendiert ->
   vollendet transzendiert/Hauptgott) und überall konsistent verwenden. Auch Anzahl prüfen
   (03.04 "ein bis drei Quasi-Götter").

## NOCH NICHT BEHANDELTE GRÖSSERE LÜCKEN (für später, nicht Teil dieser TODOs)
- Bewusstseins-/Todeskonzept (trägt Bewusstseinsübertragung Erde->Lumora, Wiedergeburt,
  Transzendenz, "Noetische Spuren Toter").
- Regel-Legitimität der Bewusstseinsübertragung unter Regel 2.
- Biologische Speicherstruktur (03.05 TODO) für Gläubigen-Energie/Rituale.
- Physik der Bilokation/Spaltung (Ursprungsgott=Chaosgott) schärfen: Kohärenz vs.
  Dekohärenz vs. Verschränkung.
- Chaosgott-Existenz im noetisch toten Raum (außerhalb Sonnensystem) vs. N-Feld-Abhängigkeit.
```