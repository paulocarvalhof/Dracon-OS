# 📦 Dracon App Format — `.drapp` Specification
```bash
#!/data/data/com.termux/files/usr/bin/bash
# main.sh — Minimal Bash App

DRACON_HOME="$HOME/.dracon"
APP_DIR="$(dirname "$0")"

echo -e "\033[0;31m=== My App on Dracon OS ===\033[0m"
echo "Press Enter to exit"
read

```

---

## 🛠️ How to create and package

### Step 1 — Create the structure
```bash
mkdir MyApp
cd MyApp
mkdir assets
```

### Step 2 — Create the manifest
```bash
cat > manifest.json << 'EOF'
{
"name": "My App",
"id": "com.yourusername.myapp",

"version": "1.0.0",

"author": "Your Name",

"description": "Description of my app",

"entry": "main.py",

"type": "python",

"category": "Utilities",

"permissions": [],

"min_dracon": "1.2.0"

}
EOF
```

### Step 3 — Create the code
```bash
nano main.py # or nano main.sh
```

### Step 4 — Package as `.drapp`
```bash
cd ..
zip -r MyApp.drapp MyApp/
```
> ✅ Done! `MyApp.drapp` is your installable app on Dracon OS.

---

## 📲 How to install a `.drapp` on Dracon OS

```bash
# Install
drapp install MeuApp.drapp

# List installed apps
drapp list

# Remove
drapp removes com.youruser.myapp

# Run direct
drapp run MeuApp.drapp
```

---

## 🌍 How to publish on the Dracon Store

1. Create your `.drapp` file following this specification.
2. Open a **Pull Request** in the Dracon OS repository.
3. Add your app to `store/catalog.json`.
4. Wait for review.

Catalog entry format:
```json
{
  "id": "com.yourusuary.myapp",
  "name": "My App",
  "version": "1.0.0",
  "author": "Your Name",
  "category": "Utilities",
  "description": "App description",
  "url": "https://github.com/yourusername/myapp/releases/latest/MyApp.drapp",
  "icon_url": "https://github.com/yourusername/myapp/raw/main/icon.png",
  "size": "12KB"
}
```

---

## ⚠️ Good practices

- **Always** handle screen size errors in curses with `try/except`
- **Never** use absolute paths — use `APP_DIR` or `DRACON_HOME`
- Icons must be **48x48 px PNG** with a transparent background
- Test on small screens (80x24 minimum)
- Use the Dracon OS color palette:

- Background: `#0d1117`

- Text: `#c9d1d9`

- Highlight: `#f84c4c`

- Secondary: `#58a6ff`
 
---

## 📞 Support

GitHub: `github.com/RacazuGames/DraconOS`
Issues: For bugs and suggestions 
Discussions:For development questions 

 
