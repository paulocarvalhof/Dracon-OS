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

## 🆕 O que há de novo na v1.3.0

| Recurso | Descrição |
|---|---|
| 🐛 **`dracon start` corrigido** | Bug que impedia o boot foi resolvido — instalador reescrito |
| 📊 **Barra de Tarefas** | Taskbar real na parte inferior: botão iniciar, apps fixados, janelas abertas, relógio |
| 🎨 **12 Paletas de Cores** | Alpine, Ocean, Dracula, Cyberpunk, Nord, Tokyo Night e mais |
| 🎮 **Dracon Game Store** | Loja dedicada a jogos, separada da Dracon Store |
| 🕹️ **3 Jogos Nativos** | Snake, Tetris e Pong — jogáveis direto no terminal |
| 🎯 **Game Hub** | Central com preview, nota e recorde de cada jogo |
| 📊 **Task Manager** | Veja e finalize processos travados |
| 🔐 **Racazu Account** | Login/cadastro integrado (Firebase) para sincronizar no futuro |

---

## 🚀 Instalação (do zero — não precisa de versão anterior)

```bash
git clone https://github.com/paulocarvalhof/Dracon-OS
cd Dracon-OS
bash install.sh
dracon start
```

Depois conecte no **RealVNC Viewer** → `localhost:5901`

> Se `dracon start` não funcionar por algum motivo, rode `dracon fix` e tente de novo.

---

## 🔄 Atualizando de v1.2.0 → v1.3.0

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
