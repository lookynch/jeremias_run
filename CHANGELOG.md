# Changelog - Jeremias Runner

## v2.0 - 2026-02-10 - Grafik-Update 🎨

### 🎨 Grafische Verbesserungen

#### J-Charakter mit Krone (NEU!)
- **Professionell gezeichnet** als Canvas-Grafik
- **Körper:** Stilisiertes "J" in Jeremias Corporate Blue-Gray (#2c3e50)
  - Vertikale Linie mit abgerundeten Ecken
  - Charakteristische J-Kurve am unteren Ende
  - Horizontale Linie oben
- **Krone:** Goldene Krone mit Details
  - 6 Zacken mit variabler Höhe
  - Rote Juwelen auf den Zacken
  - Gold-Gradient (#FFD700)
  - Dunklerer Rand (#DAA520)
- **Animationen:**
  - Laufende Beine (alternierendes Schwingen)
  - Leichtes Hüpfen beim Laufen
  - Angewinkelte Beine beim Springen
  - Ducken: Körper wird schmaler, Krone bleibt sichtbar

#### Jeremias-Schornsteine (NEU!)
Ersetzen die alten Kakteen/Wolken-Hindernisse:

- **Realistische Schornstein-Optik:**
  - Metallischer Grauverlauf (#95a5a6 → #bdc3c7 → #7f8c8d)
  - Segmentierte Konstruktion (horizontale Ringe)
  - Rote Abdeckung oben (#e74c3c)
  - Schwarzer Rand für Kontrast
- **Rauch-Animation:**
  - Graue Wolken steigen aus dem Schornstein
  - Animierte Partikel
  - Halbtransparent
- **Varianten:**
  - **Single:** Einzelner Schornstein
  - **Double:** Doppelschornstein (breitere Variante)
- **Zufällige Größen:** 80-120px Höhe, 40-60px Breite

#### Münzen-Verbesserungen
- **Sparkle-Effekt:** Weißer Glanzpunkt blinkt
- **Bessere Gradienten:** Gold → Orange → Dunkelorange
- **Innerer Ring:** Zusätzlicher Detailring

---

### 🐛 Bugfixes
- Kollisionserkennung präziser (kleinere Hitbox)
- Boden-Animation flüssiger
- Performance-Optimierungen

---

### 📊 Technische Änderungen
- `drawJCharacter()` Funktion für Character-Rendering
- `Chimney` Klasse ersetzt `Obstacle`
- Canvas-Gradienten für Metalloptik
- Verbesserte Physik-Engine

---

## v1.0 - 2026-02-10 - Initial Release

### Features
- HTML5 Canvas Spiel
- J-Charakter (Text-basiert)
- Münzen sammeln
- Score-System + High Score
- Responsive Design
- n8n Integration

---

## Roadmap

### v2.1 (geplant)
- [ ] Sound-Effekte (Sprung, Münze, Kollision)
- [ ] Mehr Schornstein-Varianten (Industrial, Wohnhaus)
- [ ] Power-Ups (Shield, Magnet, Speed Boost)
- [ ] Particle-Effekte bei Münz-Sammeln

### v3.0 (geplant)
- [ ] Multiplayer-Modus
- [ ] Leaderboard (Online)
- [ ] Achievements
- [ ] Tag/Nacht-Modus
