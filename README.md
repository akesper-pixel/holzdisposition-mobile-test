# HolzDisposition Mobile V4.4.2 – isolierte GitHub-Pages-Testversion

**Nur Test.** Die produktive V4.4.1 nicht ersetzen. Diese Dateien ausschließlich in das neue Test-Repository hochladen.

## Dateien
- `index.html` – V4.4.2 mit eigenen localStorage-Schlüsseln
- `sw.js` – Offline-Cache für statische Dateien, im Pfad des Test-Repositories
- `manifest.webmanifest` – eigene Test-PWA
- `icon-192.png`, `icon-512.png` – deutlich als TEST markierte Icons

## Bereitstellung
1. Dateien **aus diesem Paket** ins Stammverzeichnis des separaten GitHub-Test-Repositories hochladen (nicht die ZIP selbst).
2. Settings → Pages → Deploy from a branch → `main` → `/ (root)` → Save.
3. Nach Bereitstellung die angezeigte HTTPS-Adresse öffnen und die TEST-Kennzeichnung prüfen.
4. Vor jeder Testzählung eine vollständige JSON-Sicherung herunterladen. Testzählungen niemals in den produktiven PC importieren.

## Wichtige Grenzen
- Ein separates Repository unter demselben `username.github.io` teilt mit anderen Projektseiten weiterhin denselben **Origin**. Die beiden Inventur-Schlüssel wurden deshalb eindeutig umbenannt; bestehende produktive Daten werden nicht automatisch migriert.
- Die isolierten Speicherschlüssel schützen die bekannten Inventurdaten, stellen aber **keine vollständige Browser-/Origin-Sicherheitsisolierung** dar. Für strikte Trennung separate Domain oder separates Browserprofil verwenden.
- Service Worker sind pfadgebunden; der Worker ist auf den Test-Projektpfad beschränkt. Vorhandene andere Worker werden nicht deregistriert oder gelöscht.
- Nur der öffentliche Supabase-Publishable-Key ist im Client enthalten. Keine Passwörter, Service-Role-Keys oder reale Inventurdaten ins Repository hochladen.
- Supabase-Anmeldung benötigt Internet; bereits gespeicherte Artikel und Testzählungen funktionieren offline.
- Die Stück/Hub-Foto-Umrechnung verwendet weiterhin den eingebauten 64er-Holzkatalog. Packmengen gegen die aktuellen Cloud-Stammdaten prüfen, bevor diese Funktion betrieblich verwendet wird.
- Noch keine Cloud-Übertragung von Zählungen; keine automatische PC-Bestandsbuchung.
- Beim ersten Online-Aufruf sollte der Service Worker installieren; Offline-Test erst danach durchführen.
