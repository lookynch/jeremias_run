# 👑 Jeremias Runner

**Ein grafisch ansprechendes Browser-Spiel im Stil des Chrome Offline T-Rex Runners – aber in der Jeremias Abgastechnik Edition!**

![Jeremias Runner](https://img.shields.io/badge/Status-Playable-success)
![HTML5](https://img.shields.io/badge/HTML5-Canvas-orange)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow)
![n8n](https://img.shields.io/badge/Hosted-n8n-blue)

---

## 🎮 Features

✨ **Professioneller J-Charakter** mit detaillierter Krone und 3D-Effekten  
🏭 **Jeremias-Schornsteine** als Hindernisse (mit Rauch-Animation!)  
🪙 **Sammelbare Münzen** mit Jeremias-Logo (J-Prägung) und Sparkle-Effekt  
📊 **Progressive Schwierigkeit:** Startet einfach, wird graduell härter  
🎯 **Optimierte Hitboxen:** Faire Kollisions-Erkennung  
👑 **High Score:** Lokal gespeichert via localStorage  
📱 **Responsive:** Funktioniert auf Desktop & Mobile  
🎨 **Grafisch hochwertig:** 3D-Gradienten, Schatten, Animationen  
⚡ **Single-Page:** Komplettes Spiel in einer HTML-Datei  
🔗 **n8n-Ready:** Kann direkt in n8n gehostet werden

---

## 🆕 Version 2.1 - Optimierungen

**Neue Features:**
- ⚡ **Progressive Schwierigkeit:** Spiel startet bei Speed 4 und steigt bis 12
- 🎯 **Optimierte Münz-Platzierung:** Keine unmöglichen Münzen mehr
- 🎨 **Verbesserter Charakter:** 3D-Gradienten, Schatten, detaillierte Krone mit Juwelen
- 🔧 **Faire Hitboxen:** Kleiner als Visual für faireres Gameplay
- 🏭 **Bessere Schornsteine:** Realistischere Grafik mit Rauch-Animation

[Siehe CHANGELOG.md für Details](CHANGELOG.md)

---

## 🕹️ Steuerung

| Taste | Aktion |
|-------|--------|
| **Leertaste / ↑** | Springen |
| **↓** | Ducken |
| **R** | Neustart (nach Game Over) |
| **Touch** | Springen (Mobile) |

---

## 🚀 Installation & Verwendung

### Variante 1: Standalone (Lokal)

1. **Datei öffnen:**
   ```bash
   open index.html
   ```
   Oder doppelklicken auf `index.html`

2. **Spielen!** 🎮

---

### Variante 2: n8n Hosting (Empfohlen)

#### Voraussetzungen:
- n8n installiert (self-hosted oder cloud)
- Zugriff auf n8n Editor

#### Setup:

1. **n8n öffnen:** Navigiere zu deiner n8n-Instanz

2. **Workflow importieren:**
   - Klicke auf **"Import from File"**
   - Wähle `jeremias-runner-n8n-flow.json`
   - Flow wird importiert

3. **Workflow aktivieren:**
   - Klicke auf **"Active"** Toggle (oben rechts)
   - Workflow ist jetzt live!

4. **Spiel aufrufen:**
   - Webhook-URL kopieren (z.B. `https://your-n8n.com/webhook/jeremias-run`)
   - Im Browser öffnen
   - **Spielen!** 🎉

#### Optional: Custom Path anpassen

Im **Webhook Node:**
- Ändere `path: "jeremias-run"` zu deinem Wunsch-Path
- Z.B. `path: "spiel"` → URL: `https://your-n8n.com/webhook/spiel`

---

## 🎨 Design-Details

### J-Charakter
```
    👑  ← Jeremias-Krone (Gold)
    |
    J   ← Buchstabe J in Dunkelblau (#2c3e50)
   / \  ← Animierte Beine
```

**Animationen:**
- **Laufen:** Beine alternieren, leichtes Hüpfen
- **Springen:** Beine angewinkelt, Parabel-Physik
- **Ducken:** Körper verkürzt, Krone bleibt sichtbar

### Münzen
```
  ___
 /   \
|  J  |  ← Gold-Münze mit Jeremias-Logo
 \___/
```

**Features:**
- Rotation während des Flugs
- Gold-Gradient (FFD700 → FFA500)
- +10 Punkte pro Münze

### Hindernisse

1. **Kakteen** (Boden):
   - Grün (#27ae60)
   - Verschiedene Größen
   - Arme links & rechts

2. **Abgas-Wolken** (Luft):
   - Grau (#95a5a6)
   - Thematisch passend zu Abgastechnik!
   - Fliegen in mittlerer Höhe

### Hintergrund
- **Himmel:** Hellblau → Beige Gradient
- **Wolken:** Weiße, animierte Wolken
- **Boden:** Braune Linie mit Sand-Textur

---

## 📊 Spielmechanik

### Schwierigkeit
- Startet bei **6 pixels/frame**
- Erhöht sich alle **500 frames** um **0.5**
- Keine Obergrenze → Unendliche Challenge!

### Score-Berechnung
```
Score = Zeit (Sekunden) + (Münzen × 10)
```

**Beispiel:**
- 30 Sekunden überlebt = 30 Punkte
- 5 Münzen gesammelt = 50 Punkte
- **Total: 80 Punkte**

### High Score
- Gespeichert in `localStorage`
- Persistent zwischen Sessions
- Zeigt besten Score an

---

## 🛠️ Technische Details

### Technologie-Stack
- **HTML5 Canvas:** Rendering
- **Vanilla JavaScript:** Game Loop, Physik
- **CSS3:** Styling, Gradients, Schatten
- **localStorage:** High Score Persistenz

### Dateistruktur
```
jeremias_run/
├── index.html                      # Standalone-Version
├── jeremias-runner-n8n-flow.json  # n8n Workflow
├── README.md                       # Diese Datei
├── PLAN.md                         # Entwicklungsplan
└── screenshots/                    # (Optional) Bilder
```

### Performance
- **FPS:** 60 (via requestAnimationFrame)
- **Canvas-Größe:** 800×400px
- **Bundle-Größe:** ~19 KB (unkomprimiert)
- **Dependencies:** Keine! Pure Vanilla JS

---

## 🎯 Anpassungen

### Farben ändern

**J-Charakter:**
```javascript
ctx.fillStyle = '#2c3e50'; // Dunkelblau → Deine Farbe
```

**Münzen:**
```javascript
ctx.fillStyle = '#FFD700'; // Gold → Deine Farbe
```

### Schwierigkeit anpassen

**Start-Geschwindigkeit:**
```javascript
let gameSpeed = 6; // Niedriger = Leichter
```

**Schwierigkeits-Steigerung:**
```javascript
if (frameCount % 500 === 0) {
    gameSpeed += 0.5; // Kleinerer Wert = Langsamer
}
```

### Münz-Spawn-Rate

```javascript
if (frameCount % 150 === 0 && Math.random() > 0.3) {
    // 150 = Seltener | 0.3 = Wahrscheinlichkeit
    coinsArray.push(new Coin());
}
```

---

## 🐛 Troubleshooting

### Spiel lädt nicht in n8n

**Problem:** Workflow gibt leere Seite zurück

**Lösung:**
1. Prüfe, ob Workflow **aktiviert** ist
2. Prüfe **Content-Type** Header: `text/html; charset=utf-8`
3. Logs checken: n8n Editor → Executions → Fehler anzeigen

---

### High Score verschwindet

**Problem:** localStorage wird gelöscht

**Ursache:** Browser-Cache geleert oder Private Mode

**Lösung:** High Score ist nur lokal gespeichert. Für persistente Speicherung: Backend-Integration (z.B. n8n Datenbank)

---

### Münzen/Hindernisse erscheinen nicht

**Problem:** Nur J-Charakter sichtbar

**Lösung:** 
1. Browser-Konsole öffnen (F12)
2. Fehler prüfen
3. JavaScript aktiviert?

---

## 🚧 Roadmap / Zukunfts-Features

- [ ] **Multiplayer:** Echtzeit-Vergleich via WebSockets
- [ ] **Leaderboard:** Globale High Scores (Backend)
- [ ] **Power-Ups:** Shield, Speed Boost, Magnet
- [ ] **Themes:** Hell-/Dunkel-Modus, Jahreszeitenwechsel
- [ ] **Sounds:** Sprung, Münze, Game Over SFX
- [ ] **Achievements:** "100 Münzen gesammelt", "1000 Punkte"
- [ ] **Mobile App:** PWA oder native Wrapper

---

## 📜 Lizenz

**MIT License**

Copyright © 2026 Jeremias Abgastechnik

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED.

---

## 🙏 Credits

- **Entwicklung:** OpenClaw AI 🤖
- **Konzept:** Jakob Kaiser (@kaisjako)
- **Inspiration:** Chrome Offline T-Rex Runner
- **Firma:** Jeremias Abgastechnik

---

## 📞 Support

**Fragen? Probleme? Feedback?**

- GitHub Issues: [github.com/lookynch/jeremias_run/issues](https://github.com/lookynch/jeremias_run/issues)
- Telegram: @kaisjako

---

**Viel Spaß beim Spielen! 👑🎮**

**High Score Challenge:** Kannst du 500 Punkte erreichen? 🏆
