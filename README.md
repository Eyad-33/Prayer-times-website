# 🕌 Islamic Prayer Times Reminder
 
A beautiful local website + Python scheduler that automatically opens your browser at each of the 5 daily prayers.
 
---
 
## Files
 
| File | Purpose |
|---|---|
| `index.html` | The prayer times website (open manually or auto-opened) |
| `prayer_reminder.py` | Python script that runs in background and opens the browser at each prayer |
 
---
 
## Quick Start
 
### 1. Open the website manually
Just double-click `index.html` — it works fully in your browser with a live clock, countdown, and in-browser popup at prayer times (no Python needed for this).
 
### 2. Auto-open at prayer times (Python scheduler)
 
**Requirements:** Python 3.6+ (already installed on most systems)
 
```bash
python prayer_reminder.py
```
 
Keep this terminal window open (or run it at startup — see below).
 
---
 
## Configuration
 
Edit the top of `prayer_reminder.py`:
 
```python
LATITUDE   = 29.0769   # Your city latitude
LONGITUDE  = 31.0991   # Your city longitude
TIMEZONE   = 2         # UTC offset (Egypt = +2)
ALERT_BEFORE_MINUTES = 0  # Set to 5 to alert 5 min early
```
 
**Common Egyptian cities:**
| City | Latitude | Longitude |
|---|---|---|
| Beni Suef | 29.0769 | 31.0991 |
| Cairo | 30.0444 | 31.2357 |
| Alexandria | 31.2001 | 29.9187 |
| Luxor | 25.6872 | 32.6396 |
| Aswan | 24.0889 | 32.8998 |
 
---
 
## Run at System Startup
 
### Windows
1. Press `Win + R`, type `shell:startup`, press Enter
2. Create a shortcut to: `pythonw prayer_reminder.py`
3. Set "Start in" folder to the folder containing these files
### macOS
Create a Launch Agent — add this to `~/Library/LaunchAgents/prayer.plist`:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "...">
<plist version="1.0">
<dict>
  <key>Label</key><string>com.prayer.reminder</string>
  <key>ProgramArguments</key>
  <array>
    <string>/usr/bin/python3</string>
    <string>/path/to/prayer_reminder.py</string>
  </array>
  <key>RunAtLoad</key><true/>
</dict>
</plist>
```
Then: `launchctl load ~/Library/LaunchAgents/prayer.plist`
 
### Linux
Add to crontab (`crontab -e`):
```
@reboot cd /path/to/folder && python3 prayer_reminder.py &
```
 
---
 
## Features
 
- ✅ Accurate prayer times using Al-Azhar / Egyptian General Authority calculation method
- ✅ Live clock and countdown to next prayer
- ✅ Beautiful dark Islamic-themed design with Arabic calligraphy
- ✅ In-browser popup notification at each prayer time
- ✅ OS desktop notifications (Windows/macOS/Linux)
- ✅ Auto-saves your location in browser localStorage
- ✅ Works offline — no internet required after first load (fonts load from Google)
- ✅ Mobile-friendly responsive design
---
 
*بارك الله فيكم — May Allah bless you*

بارك الله فيكم — May Allah bless you
