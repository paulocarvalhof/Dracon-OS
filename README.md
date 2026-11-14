<div align="center">

```
██████╗ ██████╗  █████╗  ██████╗ ██████╗ ███╗   ██╗
██╔══██╗██╔══██╗██╔══██╗██╔════╝██╔═══██╗████╗  ██║
██║  ██║██████╔╝███████║██║     ██║   ██║██╔██╗ ██║
██║  ██║██╔══██╗██╔══██║██║     ██║   ██║██║╚██╗██║
██████╔╝██║  ██║██║  ██║╚██████╗╚██████╔╝██║ ╚████║
╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚═════╝ ╚═╝  ╚═══╝
                 O  S  v2.2.0
```

**Sistema visual para Termux — VNC ou Termux:X11**

![Version](https://img.shields.io/badge/version-2.2.0-red?style=flat-square)
![License](https://img.shields.io/badge/license-Proprietary-blue?style=flat-square)

</div>

---

## 🔧 v2.2.0 — janelas que fecham, apps na barra de tarefas, visual novo

**Corrigido — botões de fechar/minimizar dos navegadores (e do terminal):**
o Openbox desenhava os botões, mas o `openbox.xml` não tinha as ações de
mouse para eles — por isso o clique não fazia nada. Agora o arquivo tem todas
as regras de mouse, e os botões foram testados num Openbox de verdade:
minimizar, maximizar e fechar funcionam.

**Novo — apps abertos aparecem na barra de tarefas.** Cada janela ganha um
botão (com o ícone do app); clicar traz para frente, clicar de novo minimiza,
clique direito abre o menu (Restaurar / Minimizar / Fechar). Os apps fixados
mostram um indicador quando estão abertos. Para isso, os apps do Dracon
passaram a ser janelas gerenciadas pelo Openbox (antes eram janelas "sem
dono" que nenhuma barra consegue listar).

**Novo — visual:** ícones desenhados (sem emoji, que o Termux não tem fonte
para mostrar), barra de título única, cartões, abas, trocar a paleta muda
**tudo** na hora (apps + moldura das janelas + fundo de tela), tela de
bloqueio nova e Configurações com diagnóstico visual.

**Mudou — Racazu Account:** a chave do Firebase **não vem mais no código**
(veja "Por que o GitHub recusou o envio?" abaixo). Ela fica em
`~/.dracon/config/racazu.env`.

**Mudou — atualização:** Configurações > Atualizações baixa a *Release* do
GitHub, em vez de depender do `git` e de uma pasta fixa.

> ⚠️ **Sobre a tela de bloqueio:** é uma tela de entrada do Dracon OS, **não**
> uma proteção de dados. Ela tem "Continuar sem conta" de propósito (para você
> nunca ficar trancado para fora do próprio celular), e quem abrir o Termux
> continua acessando seus arquivos.

---

## ⚠️ O que foi testado de verdade (e o que não foi)

✅ **Testado rodando** num Linux com Xvfb + **Openbox real** + Python 3.12/Tk 9:
- Botões minimizar / maximizar / fechar das janelas (clique de mouse simulado)
- Janelas dos apps Dracon: abrir, minimizar, restaurar, fechar, arrastar
- Barra de tarefas: apps fixados, janelas abertas, destaque da ativa, menu de
  clique direito, religar sozinha se cair (`session.sh`)
- Trocar paleta (tema do Openbox + app reabrindo com a cor nova)
- Tela de bloqueio no início e com o desktop aberto (teclado funcionando),
  login/erro/sessão com um servidor de autenticação **falso**
- Racazu Account (entrar, erro de senha, sair) contra o servidor falso
- Atualização (baixar, extrair com proteção contra `../`, rodar script, erros)
  contra um servidor falso; `install.sh` e `update-v2.2.0.sh` com `pkg` simulado
- Calculadora (avaliador seguro, sem `eval`), gerenciador de arquivos

❌ **NÃO consegui testar** (preciso do seu retorno no celular):
- Termux / Android reais, Termux:X11, RealVNC Viewer
- Instalação real de pacotes via `pkg` (nomes conferidos na documentação)
- Conexão real com o Firebase e com a API do GitHub (o ambiente de testes não alcança)
- Jogos curses dentro do xterm (Game Hub, Editor), Cubo 3D (OpenGL)
- Navegadores (Firefox/Chromium) — só a tela de detecção/instalação

Se algo da segunda lista falhar, mande print e o conteúdo de
`~/.dracon/logs/` — a lógica principal já foi exercitada, então o provável é
algo específico do aparelho.

---

## 🚀 Instalação (do zero)

```bash
git clone https://github.com/paulocarvalhof/Dracon-OS
cd Dracon-OS
bash install.sh
```

Depois da instalação, ative a Racazu Account (opcional):

```bash
cp ~/.dracon/config/racazu.env.example ~/.dracon/config/racazu.env
nano ~/.dracon/config/racazu.env      # cole a FIREBASE_API_KEY do projeto
```

```bash
dracon start        # via VNC (RealVNC Viewer → localhost:5901)
# ou
dracon start-x11    # via Termux:X11 (precisa do app Termux:X11 separado)
```

## 🔄 Atualizando

**Pelo visual:** Configurações > Atualizações > *Verificar atualizações*.
(Precisa de uma *Release* publicada no GitHub com o `.zip` anexado.)

**Pelo Termux** (de v1.3.0 / v2.0.0 / v2.1.0):

```bash
unzip -o DraconOS-v2.2.0.zip
cd DraconOS-v2.2.0
bash tools/update-v2.2.0.sh
dracon restart
```

---

## 🩺 `dracon status` e `dracon fix`

```bash
dracon status   # o que está rodando e o que falta (tkinter, python-xlib, fonte, conta...)
dracon fix      # instala o que falta, regenera o tema das janelas, limpa sessões travadas
```

---

## 🐙 Por que o GitHub recusou o envio das versões 1.3 a 2.1?

Três causas possíveis — a mais provável é a primeira:

1. **Chave de API dentro do código.** As versões 1.3.0, 2.0.0 e 2.1.0 tinham a
   `apiKey` do Firebase escrita em arquivos. O GitHub procura chaves do Google
   (`AIza...`) em todo envio e **bloqueia** ("push protection", erro `GH013`).
   A chave do Firebase para web é pública por design, mas o GitHub não sabe
   disso. **Na v2.2.0 a chave não está em nenhum arquivo do pacote.**
2. **Arquivos demais.** O envio pelo site aceita até 100 arquivos por vez.
3. **Várias versões na mesma pasta.** Suba só a versão mais nova na raiz do
   repositório; as antigas vão como *Releases* (zip anexado).

Antes de enviar, rode: `bash tools/check-repo.sh` — ele avisa de chaves,
quantidade de arquivos e arquivos que não devem ir.

---

## 🌐 Dracon Browser

```bash
dracon-browser
```
Detecta se você já tem Firefox, Chromium, NetSurf ou Surf instalado.
Se não tiver nenhum, mostra uma tela visual para instalar — sem digitar
comando nenhum.

## 🏪 Racazu Store

Abre [racazustore.netlify.app](https://racazustore.netlify.app/) pelo
navegador. Usa a **mesma conta** do Racazu Account (Firebase compartilhado).

```bash
dracon-racazustore
```

## 🖥️ Termux:X11 (alternativa ao VNC)

```bash
dracon start-x11
```
Mais rápido que VNC, mas precisa do app **Termux:X11** (não está na Play
Store nem F-Droid — baixe o `.apk` em
`github.com/termux/termux-x11/releases`).

## 🎲 Jogos 3D (Beta)

```bash
pip install pygame PyOpenGL PyOpenGL_accelerate --break-system-packages
pkg install mesa
```
Depois abra pela Dracon Store → aba Jogos → **Cubo 3D (Beta)**.
Isso é o primeiro passo para jogos 3D no Dracon OS — ainda experimental.

---

## 🖼️ Fundo de tela

Coloque sua imagem em `~/.dracon/assets/images/wallpapers/<tema>.png`
(`alpine`, `dark`, `ocean`, `forest`, `sunset`...). Sem imagem sua, o Dracon
gera um fundo com as cores da paleta (Configurações > Aparência).

---

## 📦 Comandos

```bash
dracon start | stop | restart | status | fix | start-x11
dracon-launcher      # Menu de apps (grade de ícones)
dracon-store         # Dracon Store (Apps + Jogos + Racazu Store)
dracon-settings      # Aparência, Tela, Segurança, Atualizações, Sobre
dracon-calc          # Calculadora
dracon-taskmgr       # Task Manager (lê /proc, sem psutil)
dracon-monitor       # System Monitor
dracon-account       # Racazu Account
dracon-browser       # Dracon Browser
dracon-racazustore   # Racazu Store
dracon-gamehub       # Game Hub (Snake, Tetris, Pong)
dracon-files         # Gerenciador de Arquivos
dracon-lock          # Bloquear a tela agora (ou Super+L)
dracon-screenshot    # Captura de tela (ou tecla Print) -> ~/screenshots
```

Atalhos: **Super** = launcher · **Super+L** = bloquear · **Alt+F4** = fechar
janela · **Alt+Tab** = alternar · **Print** = captura.

---

## 📄 Licença

Software proprietário — uso permitido, modificação e redistribuição
**não permitidas**. Veja `LICENSE`.

`config/racazu.env` (sua chave do Firebase) e `config/session.json` (seu token
de login) são **só do seu aparelho** e estão no `.gitignore` — não envie.

---

<div align="center">

### 🐉 Dracon OS — Desktop Visual na Palma da Sua Mão

**Made with ❤️ — All Rights Reserved © 2026**

</div>
