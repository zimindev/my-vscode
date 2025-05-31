✅ Install **VSCode** on **Arch Linux**
🔧 Set up the `Mod+C` shortcut in **i3wm**
🔌 Install essential **VSCode extensions** quickly

---

## 🧩 Step 1: Install VSCode (Official or Open Source)

### ▶️ A) Microsoft’s VSCode (with telemetry)

```bash
sudo pacman -S code
```

### ▶️ B) VSCodium (open source, no telemetry – optional)

```bash
yay -S visual-studio-code-bin
```

> Requires an AUR helper like `yay`. Use this if you prefer a completely open-source version.

---

## ⌨️ Step 2: Add `Mod+C` Shortcut in i3wm

### 1. Open your i3 config file:

```bash
nano ~/.config/i3/config
```

(or `~/.i3/config` depending on setup)

### 2. Add this line to bind `Mod+C` to open VSCode:

```i3
# Launch VSCode with Mod+C
bindsym $mod+c exec code
```

### 3. Reload i3 configuration:

Press: `Mod + Shift + R`

✅ Now pressing `Mod + C` will launch VSCode.

---

## 🧪 Step 3: Make sure the `code` command works

Run in terminal:

```bash
code
```

If it doesn't launch VSCode, fix it with:

```bash
sudo ln -s /usr/bin/code /usr/local/bin/code
```

---

## 🔌 Step 4: Install All Useful Extensions in One Command

### 1. Create an install script:

```bash
nano vscode-extensions.sh
```

### 2. Paste this:

```bash
#!/bin/bash

EXTENSIONS=(
aaron-bond.better-comments
alefragnani.project-manager
anteprimorac.html-end-tag-labels
box-of-hats.bemhelper
bradgashler.htmltagwrap
cipchk.cssrem
dzhavat.css-flexbox-cheatsheet
eamodio.gitlens
esbenp.prettier-vscode
formulahendry.auto-close-tag
formulahendry.auto-complete-tag
formulahendry.auto-rename-tag
github.copilot
github.copilot-chat
glenn2223.live-sass
kisstkondoros.vscode-gutter-preview
lior-chamla.google-fonts
mrmlnc.vscode-scss
ms-vscode.live-server
oderwat.indent-rainbow
pucelle.vscode-css-navigation
ritwickdey.liveserver
sainoba.px-to-rem
sibiraj-s.vscode-scss-formatter
slevesque.vscode-zipexplorer
solnurkarim.html-to-css-autocompletion
vscode-icons-team.vscode-icons
)

for EXT in "${EXTENSIONS[@]}"; do
  code --install-extension "$EXT"
done
```

### 3. Make the script executable and run it:

```bash
chmod +x vscode-extensions.sh
./vscode-extensions.sh
```

---

## 🛠️ Optional VSCode Config (Formatting, Autosave)

Open VSCode, then open settings JSON (`Ctrl+Shift+P` → **Preferences: Open Settings (JSON)**), and paste:

```json
{
  "editor.formatOnSave": true,
  "editor.tabSize": 2,
  "files.autoSave": "onFocusChange",
  "editor.minimap.enabled": false
}
```
