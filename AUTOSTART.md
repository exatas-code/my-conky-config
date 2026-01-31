# How to Autostart Conky on Pop!_OS

To make Conky start automatically with your system, follow these steps:

## 1. Using Startup Applications (Recommended)

1. Open your application menu and search for **"Startup Applications"**.
2. Click **"Add"**.
3. Fill in the fields:
   - **Name**: `Conky`
   - **Command**: `conky -p 10 -c ~/.config/conky/conky.conf`
   - **Comment**: `Starts the system monitor widget`
4. Click **"Add"**.

> [!TIP]
> The `-p 10` flag adds a 10-second delay. This ensures your wallpaper and desktop environment are fully loaded before Conky starts, which prevents transparency issues.

---

## 2. Using Terminal (Manual Method)

If you prefer creating the entry manually:

1. Create the autostart directory if it doesn't exist:
   ```bash
   mkdir -p ~/.config/autostart
   ```

2. Create a desktop entry file:
   ```bash
   nano ~/.config/autostart/conky.desktop
   ```

3. Paste the following:
   ```ini
   [Desktop Entry]
   Type=Application
   Exec=conky -p 10 -c /home/nome-de-usuario/.config/conky/conky.conf
   Hidden=false
   NoDisplay=false
   X-GNOME-Autostart-enabled=true
   Name=Conky
   Comment=Starts the system monitor widget
   ```

4. Save and exit (Ctrl+O, Enter, Ctrl+X).
