🕌 Islamic Prayer Times Reminder
A beautiful local website + Python scheduler that automatically opens your browser at each of the 5 daily prayers.

Files
FilePurposeindex.htmlThe prayer times website (open manually or auto-opened)prayer_reminder.pyPython script that runs in background and opens the browser at each prayer

Quick Start
1. Open the website manually
Just double-click index.html — it works fully in your browser with a live clock, countdown, and in-browser popup at prayer times (no Python needed for this).
2. Auto-open at prayer times (Python scheduler)
Requirements: Python 3.6+ (already installed on most systems)
bashpython prayer_reminder.py
Keep this terminal window open (or run it at startup — see below).

Configuration
Edit the top of prayer_reminder.py:
pythonLATITUDE   = 29.0769   # Your city latitude
LONGITUDE  = 31.0991   # Your city longitude
TIMEZONE   = 2         # UTC offset (Egypt = +2)
ALERT_BEFORE_MINUTES = 0  # Set to 5 to alert 5 min early
Common Egyptian cities:
CityLatitudeLongitudeBeni Suef29.076931.0991Cairo30.044431.2357Alexandria31.200129.9187Luxor25.687232.6396Aswan24.088932.8998

Run at System Startup
Windows

Press Win + R, type shell:startup, press Enter
Create a shortcut to: pythonw prayer_reminder.py
Set "Start in" folder to the folder containing these files

macOS
Create a Launch Agent — add this to ~/Library/LaunchAgents/prayer.plist:
xml<?xml version="1.0" encoding="UTF-8"?>
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
Then: launchctl load ~/Library/LaunchAgents/prayer.plist
Linux
Add to crontab (crontab -e):
@reboot cd /path/to/folder && python3 prayer_reminder.py &

Features

✅ Accurate prayer times using Al-Azhar / Egyptian General Authority calculation method
✅ Live clock and countdown to next prayer
✅ Beautiful dark Islamic-themed design with Arabic calligraphy
✅ In-browser popup notification at each prayer time
✅ OS desktop notifications (Windows/macOS/Linux)
✅ Auto-saves your location in browser localStorage
✅ Works offline — no internet required after first load (fonts load from Google)
✅ Mobile-friendly responsive design


بارك الله فيكم — May Allah bless you
