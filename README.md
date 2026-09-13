<div align="center">

```
██████╗ ██████╗  █████╗  ██████╗ ██████╗ ███╗   ██╗
██╔══██╗██╔══██╗██╔══██╗██╔════╝██╔═══██╗████╗  ██║
██║  ██║██████╔╝███████║██║     ██║   ██║██╔██╗ ██║
██║  ██║██╔══██╗██╔══██║██║     ██║   ██║██║╚██╗██║
██████╔╝██║  ██║██║  ██║╚██████╗╚██████╔╝██║ ╚████║
╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚═════╝ ╚═╝  ╚═══╝
                 O  S  v1.3.0
```

**Alpine-inspired Desktop OS for Termux + VNC**

![Version](https://img.shields.io/badge/version-1.3.0-red?style=flat-square)
![License](https://img.shields.io/badge/license-Proprietary-blue?style=flat-square)

</div>

---

## 🆕 What's New in v1.3.0

| Feature | Description |

|---|---|

| 🐛 **`dracon start` fixed** | Bug preventing boot has been resolved — installer rewritten |

| 📊 **Taskbar** | Real taskbar at the bottom: start button, pinned apps, open windows, clock |

| 🎨 **12 Color Palettes** | Alpine, Ocean, Dracula, Cyberpunk, Nord, Tokyo Night and more |

| 🎮 **Dracon Game Store** | Dedicated game store, separate from the Dracon Store |

| 🕹️ **3 Native Games** | Snake, Tetris and Pong — playable directly in the terminal |

| 🎯 **Game Hub** | Central hub with preview, rating and record for each game |

| 📊 **Task Manager** | View and terminate stuck processes |

| 🔐 **Racazu Account** | Integrated login/registration (Firebase) for future synchronization |

---

## 🚀 Installation (from scratch — no previous version needed)

```bash
git clone https://github.com/paulocarvalhof/Dracon-OS
cd Dracon-OS
bash install.sh
dracon start
```

Then connect to **RealVNC Viewer** → `localhost:5901`

> If `dracon start` doesn't work for some reason, run `dracon fix` and try again.

---

## 🔄 Updating from v1.2.0 → v1.3.0

```bash
cd Dracon-OS
git pull
unzip -o DraconOS-v1.3.0.zip
cd DraconOS-v1.3.0
bash tools/update-v1.3.0.sh
dracon restart
```
 
---

## 🎮 Available Games

- **🐍 Snake** — eat food, grow, don't hit yourself (WASD/arrow keys)
- **🧱 Tetris** — stack blocks and clear lines (← → ↓, space = rotate)
- **🏓 Pong** — classic against the CPU (W/S)

Access via `dracon-gamehub` or through the desktop menu → **Game Hub**.

---

## 🎨 Available Color Palettes

Alpine Red · Ocean Blue · Forest Green · Dracula · Cyberpunk · Sunset · Monochrome · Rose Gold · Nord · Catppuccin · Solarized · Tokyo Night

Switch with `dracon-palette` or through the menu → **Color Palette**.

---

## 🔐 Racazu Account

Account system integrated with Dracon OS, using Firebase Authentication.

``bash
dracon-account

```

- Create account / Login
- Data saved locally in `~/.dracon/config/session.json`
- The Firebase public key can be customized in `~/.dracon/config/racazu.env`

> ⚠️ **Security Note:** `session.json` contains your session token — never share or upload this file to GitHub (it's already in `.gitignore`).

---

## 📊 New commands in v1.3.0

```bash
dracon-taskbar # Manually resets the taskbar
dracon-gamehub # Opens the Game Hub
dracon-gamestore # Opens the Dracon Game Store
dracon-palette # Opens the color palette selector
dracon-taskmgr # Opens the Task Manager
dracon-account # Opens the Dracon Account
dracon fix # Fixes broken commands/shortcuts

```

---

## 📄 License

Proprietary software — use permitted, modification and redistribution **not permitted**.

See `LICENSE` for full terms.

---

<div align="center">

### 🐉 Dracon OS v1.3.0 — Desktop in the Palm of Your Hand

**Made with ❤️ — All Rights Reserved © 2026**

</div> 
