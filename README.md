# 🐍 Snake Deluxe

<div align="center">

![Snake Deluxe](https://img.shields.io/badge/Snake-Deluxe-00ff88?style=for-the-badge&logo=html5&logoColor=white)
![Version](https://img.shields.io/badge/Version-1.0.0-00ccff?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Browser-ffd700?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-ff6b6b?style=for-the-badge)

**Ein hochwertiges, browserbasiertes Snake-Spiel mit modernem Design, Levelsystem und Soundeffekten.**

[▶ Jetzt spielen](#-schnellstart) · [Features](#-features) · [Controls](#-steuerung) · [Technologie](#-technologie)

</div>

---

## 📸 Vorschau

Das Spiel läuft direkt im Browser – keine Installation, keine Abhängigkeiten.  
Öffne einfach `snake.html` in einem modernen Webbrowser und los geht's!

---

## ✨ Features

| Feature | Beschreibung |
|---|---|
| 🎨 **Dark-Theme UI** | Elegantes Dunkel-Design mit Neon-Akzenten und animiertem Sternenhintergrund |
| 🐍 **Animierte Schlange** | Farbverlauf vom leuchtenden Kopf zum dunklen Schwanz mit Augen-Animation |
| 🍎 **5 Nahrungstypen** | Verschiedene Früchte mit unterschiedlichen Punktwerten und Seltenheitsstufen |
| 📈 **Levelsystem** | Automatisches Level-Up alle 5 Punkte – die Geschwindigkeit steigt progressiv |
| 🔊 **Soundeffekte** | Prozedural generierte Töne via Web Audio API (kein externes Audio nötig) |
| ✨ **Partikeleffekte** | Explosionspartikel beim Essen und beim Sterben |
| 🏆 **Highscore** | Persönlicher Highscore wird dauerhaft im `localStorage` gespeichert |
| 📱 **Mobile-Support** | D-Pad für Touch-Geräte + Swipe-Gesten auf dem Spielfeld |
| ⏸ **Pause-Funktion** | Spiel jederzeit pausierbar und fortsetzbar |
| 🎭 **Idle-Animation** | Sanfte Demo-Schlange auf dem Startbildschirm |

---

## 🍽️ Nahrungstypen & Punkte

| Emoji | Name | Punkte | Wahrscheinlichkeit |
|:---:|---|:---:|:---:|
| 🍎 | Apfel | 1 | 50 % |
| 🍊 | Orange | 1 | 25 % |
| 🍇 | Trauben | 2 | 15 % |
| ⭐ | Stern | 3 | 7 % |
| 💎 | Diamant | 5 | 3 % |

---

## 🎮 Steuerung

### Tastatur

| Taste | Aktion |
|:---:|---|
| `W` / `↑` | Nach oben |
| `A` / `←` | Nach links |
| `S` / `↓` | Nach unten |
| `D` / `→` | Nach rechts |
| `P` | Pause / Fortsetzen |
| `R` | Neustart |

### Mobile / Touch

- **D-Pad**: Auf dem Touchscreen erscheint automatisch ein Steuerkreuz
- **Swipe**: Auf dem Spielfeld wischen, um die Richtung zu ändern

---

## 📈 Levelsystem

Das Spiel startet mit Level 1 und wird alle **5 gesammelten Punkte** schwieriger:

| Level | Benötigte Punkte | Tickrate |
|:---:|:---:|:---:|
| 1 | 0 | 130 ms |
| 2 | 5 | 122 ms |
| 3 | 10 | 114 ms |
| 5 | 20 | 98 ms |
| 10 | 45 | 58 ms |
| Max | – | 50 ms (Limit) |

---

## 🚀 Schnellstart

### Option 1 – Direkt öffnen

```bash
# Datei einfach im Browser öffnen
open snake.html          # macOS
start snake.html         # Windows
xdg-open snake.html      # Linux
```

### Option 2 – Lokaler Webserver (empfohlen)

```bash
# Mit Python
python3 -m http.server 8080

# Dann im Browser öffnen:
# http://localhost:8080/snake.html
```

```bash
# Mit Node.js (npx)
npx serve .
```

---

## 🛠️ Technologie

Das Spiel ist ein **Single-File HTML5-Projekt** – vollständig in einer einzigen Datei ohne externe Abhängigkeiten.

| Technologie | Verwendung |
|---|---|
| **HTML5 Canvas** | Spielfeld, Schlange, Nahrung, Partikel (3 überlagerte Canvas-Elemente) |
| **Web Audio API** | Prozedural generierte Soundeffekte (Sinuswellen, Sägezahn, etc.) |
| **CSS Custom Properties** | Konsistentes Farbsystem mit Neon-Akzenten |
| **CSS Animations** | Twinkle-Sterne, Score-Pop-Animation, Overlay-Transitions |
| **localStorage** | Persistenter Highscore-Speicher |
| **requestAnimationFrame** | Flüssige Spielschleife mit Delta-Time-Steuerung |

### Architektur

```
snake.html
├── CSS         – Styling, Animationen, responsive Layout
├── HTML        – Spielfeld, Overlays (Start / Pause / Game Over), D-Pad
└── JavaScript
    ├── Stars           – Animierter Sternenhintergrund
    ├── Canvas Setup    – 3× Canvas (Grid, Game, Particles)
    ├── Audio (sfx)     – Web Audio API Soundeffekte
    ├── Particles       – Partikeleffekt-System
    ├── Game State      – Schlange, Richtung, Nahrung, Score, Level
    ├── Game Loop       – requestAnimationFrame + Tick-Steuerung
    ├── Drawing         – Schlange, Augen, Nahrung (pulsierend)
    ├── Screens         – Overlay-Verwaltung
    └── Input           – Tastatur, D-Pad, Touch/Swipe
```

---

## 🏆 Scoring & Bewertung

Am Ende jedes Spiels erscheint eine persönliche Bewertung:

| Punkte | Nachricht |
|:---:|---|
| ≥ 20 | 🏆 Fantastisch! Du bist ein Profi! |
| ≥ 10 | 👍 Gut gemacht! Nochmal versuchen? |
| < 10 | 😅 Schade! Du schaffst das! |

Der persönliche Beststand wird automatisch lokal gespeichert und bleibt auch nach dem Schließen des Browsers erhalten.

---

## 📱 Browser-Kompatibilität

| Browser | Support |
|---|:---:|
| Chrome 80+ | ✅ |
| Firefox 75+ | ✅ |
| Safari 14+ | ✅ |
| Edge 80+ | ✅ |
| Mobile Chrome/Safari | ✅ |

> **Hinweis:** Ein moderner Browser mit Canvas- und Web Audio API-Unterstützung ist erforderlich.

---

## 📁 Dateistruktur

```
Game/
└── snake.html    # Das komplette Spiel (single-file)
```

---

## 📄 Lizenz

Dieses Projekt steht unter der [MIT-Lizenz](https://opensource.org/licenses/MIT) – frei verwendbar, veränderbar und verteilbar.

---

<div align="center">

Mit ❤️ und reinem HTML5 gebaut · Keine Frameworks · Keine Abhängigkeiten

</div>
