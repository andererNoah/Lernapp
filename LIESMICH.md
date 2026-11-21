# Chipdorf – Lernspiel

Läuft unter https://lernapp-2.nosio.workers.dev (Cloudflare Worker mit statischen Dateien).

- Die Seite besteht aus den Dateien im Hauptordner; `index.html` lädt sie der Reihe nach.
- Lernstoff: `aufbau.js` (Module und Themen), je Thema eine Datei (`hw.js`, `mkt.js`, …),
  `neues.js` (Fenster „Neues“). Alles ist mit dem Kurs-Passwort verschlüsselt
  (PBKDF2 + AES-GCM, siehe `zugang.js`). Neue Pakete immer mit demselben Salz verschlüsseln,
  sonst müssen alle das Passwort neu eingeben.
- Kennungen von Kapiteln und Themen nie ändern: Sterne und Lernstand hängen daran.
- Veröffentlichen: Übernahme in `main` → GitHub Action „Veröffentlichen“ lädt hoch.
  Dafür braucht das Repo die Secrets `CLOUDFLARE_API_TOKEN` und `CLOUDFLARE_ACCOUNT_ID`.
