# Hyprpaper Wallpaper Rotator

Automated wallpaper rotation script for Hyprland with dynamic config generation. Changes wallpapers randomly every 30 minutes from a user-defined directory.

## ✨ Features
- Random wallpaper selection from specified directory
- Safe filename handling (supports spaces/special characters)
- Automatic hyprpaper instance management
- Configurable monitor output and paths
- Temporary config fallback for read-only systems
- POSIX-compliant interval timing

## ⚙️ Installation
1. Save script to Hypr config directory:
   ```bash
   chmod +x ~/.config/hypr/wallpaper-rotator.sh
   ```
2. Add to `hyprland.conf` for autostart:
   ```ini
   exec-once = ~/.config/hypr/wallpaper-rotator.sh
   ```

## 🔧 Configuration
1. Set your monitor name in the script:
   ```bash
   MONITOR="HDMI-A-2" # Use your actual output name
   ```
2. Ensure wallpapers exist in:
   ```bash
   ~/wallpaper/ # Default directory (create if needed)
   ```

## 🚀 Usage
```bash
# Manual single rotation
~/.config/hypr/wallpaper-rotator.sh once

# Continuous mode (default)
~/.config/hypr/wallpaper-rotator.sh
```

## 📂 File Structure
```
~/.config/hypr/
├── hyprland.conf
├── hyprpaper.conf (auto-generated)
└── wallpaper-rotator.sh (this script)
~/wallpaper/ # Your wallpaper collection
   ├── wallpaper1.jpg
   └── wallpaper2.png
```

## ⚠️ Requirements
- [hyprpaper](https://github.com/hyprwm/hyprpaper) installed
- Supported image formats: JPG/JPEG/PNG

## 🔄 Technical Process
1. Validates wallpaper directory
2. Generates fresh hyprpaper config
3. Safely terminates existing instances
4. Starts new hyprpaper process
5. Repeats every 30 minutes (1800s)
