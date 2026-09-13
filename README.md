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

## 🎮 Jogos disponíveis

- **🐍 Snake** — coma comida, cresça, não bata em si mesmo (WASD/setas)
- **🧱 Tetris** — empilhe blocos e limpe linhas (← → ↓, espaço = girar)
- **🏓 Pong** — clássico contra a CPU (W/S)

Acesse via `dracon-gamehub` ou pelo menu do desktop → **Game Hub**.

---

## 🎨 Paletas de cores disponíveis

Alpine Red · Ocean Blue · Forest Green · Dracula · Cyberpunk · Sunset ·
Monochrome · Rose Gold · Nord · Catppuccin · Solarized · Tokyo Night

Troque com `dracon-palette` ou pelo menu → **Color Palette**.

---

## 🔐 Racazu Account

Sistema de conta integrado ao Dracon OS, usando Firebase Authentication.

```bash
dracon-account
```

- Criar conta / Login
- Dados salvos localmente em `~/.dracon/config/session.json`
- A chave pública do Firebase pode ser customizada em `~/.dracon/config/racazu.env`

> ⚠️ **Nota de segurança:** `session.json` contém seu token de sessão — nunca compartilhe ou suba esse arquivo pro GitHub (já está no `.gitignore`).

---

## 📊 Comandos novos da v1.3.0

```bash
dracon-taskbar      # Reinicia a barra de tarefas manualmente
dracon-gamehub      # Abre o Game Hub
dracon-gamestore    # Abre a Dracon Game Store
dracon-palette      # Abre o seletor de paletas de cores
dracon-taskmgr      # Abre o Task Manager
dracon-account      # Abre o Racazu Account
dracon fix          # Corrige comandos/atalhos quebrados
```

---

## 📄 Licença

Software proprietário — uso permitido, modificação e redistribuição **não permitidas**.
Veja `LICENSE` para os termos completos.

---

<div align="center">

### 🐉 Dracon OS v1.3.0 — Desktop na Palma da Sua Mão

**Made with ❤️ — All Rights Reserved © 2026**

</div>
