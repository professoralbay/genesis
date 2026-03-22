# GENESIS — Real-Time Universe Simulator

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Canvas API](https://img.shields.io/badge/Canvas_API-FF6B35?style=flat&logo=html5&logoColor=white)
![Claude AI](https://img.shields.io/badge/Claude_AI-D97757?style=flat&logo=anthropic&logoColor=white)

> A real-time physics-based universe simulator. Create stars, black holes, nebulas and comets — watch them attract, collide, and merge. An AI Oracle powered by Claude observes your universe and comments philosophically.

---

## 🔴 Live Demo

**[👉 View Live Demo](https://professoralbay.github.io/genesis)**

---

## 🎬 Demo

![Demo](screenshot.gif)

---

## ✨ Features

- ⭐ **4 creation modes** — Star, Black Hole, Nebula, Comet
- 🌌 **Real physics** — gravitational attraction between all bodies (inverse-square law)
- 🕳️ **Black holes** — rotating accretion disk with glow effect, absorbs nearby bodies
- 💥 **Supernovas** — stars age and explode, sometimes spawning new stars
- ☄️ **Auto comets** — appear from screen edges every 8 seconds with trail effect
- 🔁 **Merge on collision** — bodies combine mass when close enough
- 🤖 **Oracle AI** — Claude watches your universe and speaks philosophically
- 💥 **Big Bang** — creates 30 stars from center with explosion
- 📊 **Live stats** — body count, collisions, elapsed time

---

## 🎮 Controls

| Key | Action |
|---|---|
| `Click` | Create body (selected mode) |
| `1` | Star mode |
| `2` | Black Hole mode |
| `3` | Nebula mode |
| `4` | Comet mode |
| `B` | Big Bang |
| `S` | Supernova (nearest star) |
| `Space` | Ask Oracle AI |

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| HTML5 Canvas | 2D physics rendering, particle system |
| CSS3 | Dark space UI, animations |
| Vanilla JS | Physics engine, game loop |
| Claude API | Oracle AI commentary |

---

## 📁 Project Structure

```
genesis/
├── index.html
├── screenshot.gif
└── README.md
```

---

## 🚀 Getting Started

```bash
git clone https://github.com/professoralbay/genesis.git
open index.html
```

---

## 🧩 Challenges & How I Solved Them

**1. N-body gravitational simulation at 60fps**
Every body attracts every other — O(n²) complexity. Optimized by skipping pairs with distance > 500px, and merging bodies that collide rather than simulating their sub-interactions.

**2. Black hole accretion disk**
Drawn as 3 rotating ellipses at different angles using `ctx.ellipse()` with the `rotation` parameter incremented each frame. Opacity decreases with each ring for depth.

**3. Star aging and supernova**
Each star gets a `maxAge` (800-1200 frames). When `age > maxAge`, it triggers a particle burst and sometimes spawns 2 child stars nearby — simulating stellar evolution.

**4. Oracle context**
Before each Claude API call, the current universe state is serialized into the prompt. Claude receives body counts and collision data, enabling relevant philosophical observations.

---

## 📄 License

MIT

*Made by [Akın Üner](https://github.com/professoralbay)*
