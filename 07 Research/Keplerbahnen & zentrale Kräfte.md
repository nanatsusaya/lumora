---
tags:
  - wip
---
# Keplerbahnen & zentrale Kräfte — Physikalische Grundlage

*Externe Referenz.* Diese Notiz sammelt die **reale Physik der Bahnbewegung**, auf der Lumoras Umlauf um [[Sonnensystem#Orthyros — der Gasriese|Orthyros]] beruht: die Keplerschen Gesetze, die Geometrie elliptischer Bahnen und — als Sonderfall — das „Gummiband"-Kraftgesetz, das einen Zentralkörper ins **Zentrum** der Bahnellipse rückt statt in einen Brennpunkt. Reale Wissenschaft, bewusst von der Lore getrennt; die in-world-Anwendung lebt in [[Orthyros-Lumora-System]].

> *Warum diese Notiz existiert:* Lumora umkreist Orthyros so, dass Orthyros fast in der **Mitte** der Bahnellipse steht — nicht, wie bei gewöhnlichen Planeten, in einem **Brennpunkt**. Das ist kein Fehler, sondern ein bekannter physikalischer Sonderfall. Die Notiz erklärt erst die normale Keplerbewegung und dann, unter welcher Bedingung der Sonderfall auftritt.

---

## Wie diese Notiz zu lesen ist

Jeder Block kommt zweimal: **Einfach** — das Bild in Alltagssprache. **Genauer** — die physikalisch saubere Fassung. Wo es hilft, eine *Anmerkung*.

---

## 1. Die Keplerschen Gesetze

**Einfach:** Johannes Kepler fand drei Regeln, nach denen sich ein kleiner Körper (Planet, Mond) um einen großen (Stern, Planet) bewegt:

1. Die Bahn ist eine **Ellipse** — ein „gestauchter Kreis" —, und der große Körper sitzt nicht in der Mitte, sondern etwas **seitlich versetzt** (in einem der beiden Brennpunkte).
2. Der kleine Körper ist **schneller, wenn er nah** am großen ist, und **langsamer, wenn er fern** ist.
3. Je weiter draußen eine Bahn liegt, desto **länger** dauert ein Umlauf.

**Genauer:**

1. *Ellipsensatz:* Jede gebundene Bahn ist eine Ellipse, in deren einem **Brennpunkt** der Zentralkörper steht. (Der Kreis ist ein Sonderfall der Ellipse.)
2. *Flächensatz:* Die Verbindungslinie Zentralkörper–Trabant überstreicht in gleichen Zeiten gleiche Flächen. Daraus folgt: in **Bahnnähe (Periapsis) maximale, in Bahnferne (Apoapsis) minimale Geschwindigkeit**. Physikalisch ist das die Erhaltung des **Drehimpulses**.
3. *Harmonischer Satz:* Das Quadrat der Umlaufzeit ist proportional zur dritten Potenz der großen Halbachse (T² ∝ a³). Mehr Abstand → überproportional längeres Jahr.

> *Anmerkung:* Die Keplergesetze gelten exakt für das **Zweikörperproblem** mit einem Kraftgesetz, das mit dem Quadrat des Abstands abnimmt (Gravitation, ∝ 1/r²). Genau dieses 1/r² ist der Grund, warum der Zentralkörper im **Brennpunkt** sitzt — und nicht in der Mitte.

---

## 2. Die Ellipse genauer

**Einfach:** Eine Ellipse hat eine lange und eine kurze Achse. Sie besitzt **zwei** ausgezeichnete innere Punkte, die Brennpunkte; sie liegen auf der langen Achse, symmetrisch zur Mitte. Je „länglicher" die Ellipse, desto weiter rücken die Brennpunkte von der Mitte weg.

**Genauer:** Kenngrößen sind die **große Halbachse** a (halbe lange Achse), die **kleine Halbachse** b (halbe kurze Achse) und die **Exzentrizität** e (0 = Kreis, nahe 1 = sehr langgestreckt). Der Brennpunktabstand von der Mitte ist c = a·e. Wichtig für das Folgende ist der Unterschied, **wo** der Zentralkörper sitzt:

- Im **Brennpunkt**: Der Abstand schwankt unsymmetrisch zwischen nah (a−c) und fern (a+c) — eine Seite der Bahn ist deutlich enger als die andere. Ein Umlauf hat **eine** Periapsis und **eine** Apoapsis.
- Im **Mittelpunkt** (siehe Abschnitt 4): Die Bahn ist **punktsymmetrisch**. Der Abstand schwankt zwischen b (an den Enden der kurzen Achse) und a (an den Enden der langen Achse), und beide Extreme treten **zweimal pro Umlauf** auf.

> *Anmerkung:* Der Unterschied „Brennpunkt vs. Mitte" ist direkt beobachtbar: im Brennpunkt-Fall ein naher und ein ferner Punkt pro Runde, im Mittelpunkt-Fall je zwei.

---

## 3. Zentrale Kräfte und das Bertrand-Theorem

**Einfach:** Warum sitzt der Stern überhaupt im Brennpunkt und nicht in der Mitte? Weil die Schwerkraft eine bestimmte „Form" hat: Sie zieht sehr stark aus der Nähe und wird mit dem Abstand rasch schwächer. Es gibt aber genau **eine** andere Kraft-Form, die ebenfalls saubere, sich schließende Bahnen erzeugt — und die rückt den Zentralkörper in die **Mitte**.

**Genauer:** Für Kräfte, die immer zum selben Zentrum zeigen (Zentralkräfte), besagt das **Bertrand-Theorem**: Nur **zwei** Kraftgesetze liefern für alle gebundenen Bahnen geschlossene (nicht langsam „auswandernde") Ellipsen:

- die **1/r²-Kraft** (Gravitation, Coulomb) → Zentrum im **Brennpunkt**;
- die **lineare Kraft** F ∝ r (Hookesches Gesetz, „Feder") → Zentrum im **Mittelpunkt**.

Jedes andere Kraftgesetz ergibt rosettenförmig **präzedierende** Bahnen, die sich nicht schließen.

> *Anmerkung:* Für Lumora ist die zweite Möglichkeit der Schlüssel — die lineare „Feder-Kraft".

---

## 4. Das „Gummiband"-Kraftgesetz (harmonischer Fall)

**Einfach:** Stell dir vor, der Mond hängt an einem **Gummiband**, das im Zentrum befestigt ist. Ein Gummiband zieht **stärker, je weiter** man es dehnt, und schwächer, je näher man der Mitte kommt — genau umgekehrt zur Schwerkraft. Unter so einer Kraft schwingt der Mond gleichmäßig **um die Mitte herum**; das Zentrum ist dann der Mittelpunkt der Bahn.

Ein anschauliches reales Beispiel: Fiele man in einen Tunnel mitten durch einen Planeten, bliebe man nicht im Zentrum hängen, sondern **schwänge hindurch und ewig hin und her** — dieselbe „Gummiband"-Bewegung.

**Genauer:** Eine lineare Rückstellkraft F = −k·r erzeugt einen **harmonischen Oszillator**. In drei Dimensionen ist die Bahn eine Ellipse, deren **Mittelpunkt** das Kraftzentrum ist. Charakteristisch:

- Die Umlaufzeit T = 2π·√(m/k) ist **unabhängig von der Bahngröße** (Amplitude) — eine enge und eine weite Bahn brauchen gleich lange.
- Der Trabant durchläuft den **kleinsten Abstand (b) und den größten (a) je zweimal pro Umlauf**; er ist am schnellsten beim kleinsten Abstand.

**Woher kommt eine solche Kraft physikalisch?** Aus dem **Schalentheorem**: *Innerhalb* einer gleichmäßig dichten Massenverteilung wächst die nach innen ziehende Masse mit dem Würfel des Radius (M ∝ r³), die resultierende Kraft also **linear mit r**. Ein Körper, der sich innerhalb einer ausgedehnten, annähernd gleichförmigen Massenwolke bewegt, erfährt damit exakt die „Gummiband"-Kraft — vorausgesetzt, diese verteilte Masse überwiegt im Bahnbereich eine etwaige zentrale Punktmasse.

> *Anmerkung (Mischfall):* Wirken Punktmasse (1/r²) und gleichförmige Wolke (∝ r) gemeinsam, liegt der Körper *zwischen* „Brennpunkt" und „Mitte", und die Bahn präzediert langsam. „Nahe der Mitte" heißt: Die lineare Komponente dominiert im Bahnbereich.

---

## 5. Anwendung in Lumora (Verweis)

Wie dieses „Gummiband" konkret zustande kommt — eine ausgedehnte, dunkle Massenwolke um [[Sonnensystem#Orthyros — der Gasriese|Orthyros]] —, welche Folgen es für Jahreszeiten, Belichtung und den Dunkeltag hat und welche quantitativen Fragen offen sind, steht in [[Orthyros-Lumora-System]]. Diese Notiz liefert dafür nur die reale physikalische Grundlage.

---

## Referenzen

- Keplersche Gesetze — https://de.wikipedia.org/wiki/Keplersche_Gesetze
- Zweikörperproblem — https://de.wikipedia.org/wiki/Zweikörperproblem
- Zentralkraft — https://de.wikipedia.org/wiki/Zentralkraft
- Harmonischer Oszillator — https://de.wikipedia.org/wiki/Harmonischer_Oszillator
- Bertrand's theorem (geschlossene Bahnen nur bei 1/r² und ∝ r) — https://en.wikipedia.org/wiki/Bertrand%27s_theorem
- Shell theorem (Kraft im Inneren einer homogenen Kugel ∝ r) — https://en.wikipedia.org/wiki/Shell_theorem
- W. Demtröder, *Experimentalphysik 1: Mechanik und Wärme* — Zentralkräfte, Keplerbahnen.
- W. Nolting, *Grundkurs Theoretische Physik 1: Klassische Mechanik* — harmonischer Oszillator, Zentralkraftproblem.
- H. Goldstein, *Klassische Mechanik* — Bertrand-Theorem, Bahnmechanik (vertiefend).
