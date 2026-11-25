# Bloom — private cycle tracker

## Install on Android
1. Extract this ZIP on a computer. Keep all files together.
2. Publish the folder on a static HTTPS host (for example GitHub Pages: create a repository, upload the files at its root, then enable Pages from the main branch in Settings > Pages). The code is public if you choose a public repository; your logs are not uploaded. Never upload your backups.
3. Open the published HTTPS address in Chrome on Android. Open the three-dot menu and choose Install app or Add to Home screen. Launch once while online to cache the app.
4. Open Calendar and log previous periods, then Settings to enable a PIN and set initial cycle lengths.

For local development: run `python -m http.server 8000` in this folder and open http://localhost:8000 on the same computer. Opening index.html directly is not a supported installation method.

## Privacy and limitations
No server, analytics, external scripts, or account. Browser localStorage holds logs. Optional PIN uses PBKDF2-SHA256 (600,000 iterations) and AES-GCM encryption. Manual lock; no biometric or automatic timeout. A short PIN is susceptible to guessing if an attacker obtains the encrypted data. Clearing site data or changing hosting origin can lose access to logs. Export backups regularly. JSON/CSV exports are unencrypted. Calendar reminders are optional ICS exports and may sync to your calendar provider; calendar apps may ignore alarm settings. No background push. Re-export reminders when predictions change. Hosting is not included and provider terms can change.

Predictions use consecutive logged flow days, recent cycle averages and an assumed 14-day luteal phase. They are estimates only, not contraception or medical diagnosis. Missing flow days can split periods. Tracking modes change the displayed goal, not the prediction algorithm. No dedicated pregnancy or postpartum mode. Source code syntax checked; not tested on an actual Android device.
