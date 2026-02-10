# Jeremias Runner - Entwicklungsplan

**Projekt:** Offline T-Rex Runner in Jeremias-Version  
**Repository:** https://github.com/lookynch/jeremias_run  
**Datum:** 2026-02-10

---

## 🎯 Ziel

Erstelle ein grafisch ansprechendes Browser-Spiel im Stil des Chrome Offline T-Rex Runners, aber mit:
- **Charakter:** Buchstabe "J" mit Jeremias-Krone als Punkt
- **Münzen:** Sammelbare Münzen mit Jeremias-Prägung
- **Hosting:** In n8n via Webhook
- **Steuerung:** Springen (Leertaste/Pfeil hoch), Ducken (Pfeil runter)

---

## 📋 Entwicklungsschritte

### Phase 1: Konzept & Design ✅
- [x] Anforderungen analysieren
- [x] Spielmechanik planen
- [ ] Assets-Konzept (J-Charakter, Krone, Münzen, Hindernisse)

### Phase 2: Game Development
- [ ] HTML5 Canvas Setup
- [ ] Spiellogik: Laufen, Springen, Ducken, Kollision
- [ ] Physik-Engine (Schwerkraft, Sprung-Parabel)
- [ ] Münzen-System (Spawning, Sammeln, Score)
- [ ] Hindernisse (Kakteen/Vögel → Jeremias-thematisiert)
- [ ] Grafik: Sprites zeichnen/generieren
- [ ] Sound-Effekte (optional)

### Phase 3: Grafik & Styling
- [ ] J-Charakter mit Krone (Canvas-Drawing oder SVG)
- [ ] Münzen mit Jeremias-Logo
- [ ] Hintergrund (Wüsten-Stil oder Jeremias-Corporate)
- [ ] Animationen (Laufen, Springen, Ducken)
- [ ] Partikel-Effekte (Münz-Sammeln, Kollision)

### Phase 4: n8n Integration
- [ ] n8n Workflow mit Webhook Node
- [ ] HTML Response (komplettes Spiel als Single-Page)
- [ ] MIME-Type korrekt setzen
- [ ] Testen: Spiel via n8n Webhook URL spielbar

### Phase 5: GitHub & Deployment
- [ ] Code in GitHub Repo pushen
- [ ] README.md mit Anleitung
- [ ] n8n Flow als JSON exportieren
- [ ] Screenshots/GIFs für Dokumentation

---

## 🎮 Spielmechanik

### Steuerung
- **Leertaste / Pfeil hoch:** Springen
- **Pfeil runter:** Ducken (während Sprung oder Laufen)
- **Neustart:** R-Taste oder Klick nach Game Over

### Spielablauf
1. J-Charakter läuft automatisch von links nach rechts (Hintergrund bewegt sich)
2. Hindernisse kommen von rechts (Kakteen, Vögel, etc.)
3. Münzen erscheinen zufällig (oben oder unten)
4. Score erhöht sich über Zeit + gesammelte Münzen
5. Kollision mit Hindernis → Game Over
6. Geschwindigkeit steigt graduell

### Score-System
- **Zeit:** +1 Punkt pro Sekunde
- **Münze:** +10 Punkte
- **High Score:** Lokal gespeichert (localStorage)

---

## 🎨 Design-Konzept

### J-Charakter
```
    👑  ← Krone (Jeremias-Style)
    |
    J   ← Großbuchstabe J in Jeremias-Schriftart
   / \  ← Lauf-Animation (Beine)
```

**Farben:**
- J: Jeremias Corporate Color (Blau/Grau?)
- Krone: Gold/Gelb
- Outline: Schwarz für Kontrast

**Animationen:**
- Laufen: Beine alternierend bewegen
- Springen: Beine angewinkelt
- Ducken: J-Körper verkürzt, Krone bleibt sichtbar

### Münzen
```
  ___
 /   \
|  J  |  ← Jeremias-Logo in Münze
 \___/
```

**Farben:**
- Gold/Gelb
- J-Logo: Dunkelblau
- Glanz-Effekt (Rotation?)

### Hindernisse
- **Kakteen:** Stilisiert, evtl. mit Jeremias-Branding
- **Vögel:** Abstrakt oder Jeremias-Maskottchen?
- **Abgas-Wolken:** Thematisch passend zu Abgastechnik!

### Hintergrund
- **Wüste:** Sand, Berge im Hintergrund
- **Himmel:** Gradient (Hell → Dunkel bei höherem Score)
- **Boden:** Linie mit Bodentextur
- **Optional:** Jeremias-Fabrik im Hintergrund

---

## 🛠️ Technische Stack

### Frontend
- **HTML5 Canvas:** Für Rendering
- **Vanilla JavaScript:** Game Loop, Physik, Logik
- **CSS:** Styling (Minimal, da Canvas)
- **localStorage:** High Score speichern

### Assets
- **Canvas Drawing:** J, Krone, Münzen, Hindernisse als Code gezeichnet
- **Alternativ:** SVG-Sprites in Canvas laden
- **Fonts:** Google Fonts oder System-Fonts

### n8n Workflow
```
[Webhook Trigger]
    ↓
[Function Node: HTML Response]
    ↓
[Respond to Webhook]
```

**Webhook Settings:**
- Method: GET
- Path: `/jeremias-run` (oder benutzerdefiniert)
- Response: HTML (Content-Type: text/html)

---

## 📦 Deliverables

1. **GitHub Repo:**
   - `index.html` - Standalone-Version
   - `game.js` - Spiellogik
   - `style.css` - Styling
   - `README.md` - Anleitung
   - `screenshots/` - Bilder/GIFs

2. **n8n Flow:**
   - `jeremias-runner-n8n.json` - Importierbar
   - Enthält komplettes HTML inline

3. **Dokumentation:**
   - Installations-Anleitung
   - Anpassungs-Guide (Farben, Logo)
   - n8n-Setup-Schritte

---

## ✅ Acceptance Criteria

- [ ] Spiel ist spielbar im Browser (Chrome, Firefox, Safari)
- [ ] J-Charakter hat Jeremias-Krone als i-Punkt
- [ ] Münzen sind sammelbar und erhöhen Score
- [ ] Kollision mit Hindernissen führt zu Game Over
- [ ] Grafik ist ansprechend und thematisch passend
- [ ] High Score wird gespeichert
- [ ] Spiel läuft in n8n über Webhook
- [ ] n8n Flow ist importierbar
- [ ] Code ist auf GitHub

---

## 🚀 Nächste Schritte

1. ✅ Plan erstellen
2. → HTML/JS Grundgerüst bauen
3. → J-Charakter mit Krone zeichnen
4. → Spielmechanik implementieren
5. → Münzen & Score-System
6. → Grafik polieren
7. → n8n Flow erstellen
8. → GitHub pushen

**Los geht's!** 🎮👑
