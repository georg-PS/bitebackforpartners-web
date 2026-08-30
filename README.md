# BiteBack for Partners – Web

Web-App-Deployment der Partner-App (Vite/React + Supabase), gehostet unter **bitebackforpartners.at**.

## Was ist das?
Der gebaute statische Output (`dist/`) der Partner-App als Website. Kern-Funktionen
(Login, Dashboard, Restaurants, Backs, Anfragen, Analytics) laufen im Browser.
Native-only Features (Push-Benachrichtigungen, Kamera-Scanner) sind im Web deaktiviert.

## Aktualisieren (bei neuen App-Änderungen)
```bash
cd ../biteback_partner
npm run build
cp -R dist/. ../bitebackforpartners-web/
# CNAME/404.html/.nojekyll bleiben erhalten
git -C ../bitebackforpartners-web add -A && git -C ../bitebackforpartners-web commit -m "Update web build" && git -C ../bitebackforpartners-web push
```

## Hosting (GitHub Pages)
- CNAME → bitebackforpartners.at
- 404.html = index.html (SPA-Fallback für React-Router-Deep-Links)
- DNS beim Domain-Anbieter (1&1/IONOS) auf GitHub Pages zeigen lassen.
