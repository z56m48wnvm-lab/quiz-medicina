# Quiz Medicina - Versione PWA (installabile come app)

Questa cartella contiene tutti i file necessari per far funzionare il quiz come app installabile
su iPhone, Android e computer.

## File inclusi
- `index.html` — l'app vera e propria
- `manifest.webmanifest` — descrive l'app ai sistemi operativi
- `sw.js` — service worker, permette il funzionamento offline
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` — icone dell'app
- `favicon.png` — icona per la tab del browser

## ⚠️ Importante
I file NON funzionano se li apri direttamente con doppio clic sul telefono.
Le PWA richiedono di essere servite via HTTPS da un server web.

Ci sono due modi semplici e gratuiti per pubblicarli:

---

## Opzione A — Netlify Drop (il più veloce, zero registrazioni obbligatorie)

1. Vai su https://app.netlify.com/drop
2. Trascina l'intera cartella `pwa` nella zona di drop
3. In pochi secondi Netlify ti darà un link del tipo `https://nome-casuale-123.netlify.app`
4. Apri quel link sul telefono — il quiz parte
5. Per installarlo come app sull'iPhone:
   - Apri il link in **Safari** (non Chrome!)
   - Tocca il pulsante "Condividi" (quadrato con la freccia in alto)
   - Scorri e scegli **"Aggiungi a Home"**
   - L'app apparirà come icona sulla schermata principale
6. Su Android/Chrome apparirà un banner "Installa app" automaticamente

Per mantenere lo stesso link nel tempo e poter aggiornare i file, crea un account gratuito
su Netlify e "claim" del sito dopo la pubblicazione.

---

## Opzione B — GitHub Pages (link stabile e personalizzabile)

1. Crea un account gratuito su https://github.com se non ce l'hai
2. Crea un nuovo repository pubblico, chiamalo per esempio `quiz-medicina`
3. Carica tutti i file di questa cartella dentro al repository (bottone "Add file" → "Upload files")
4. Vai in **Settings** → **Pages**
5. Alla voce "Source" scegli **main branch** e cartella `/ (root)`
6. Salva. Dopo 1-2 minuti il tuo link sarà `https://TUONOMEUTENTE.github.io/quiz-medicina/`
7. Condividi quel link con i colleghi e installatelo come app (vedi passo 5 dell'Opzione A)

---

## Come si installa sull'iPhone (da ricordare)

1. Apri il link del sito in **Safari** (deve essere Safari, non Chrome)
2. Tocca l'icona "Condividi" in basso (quadrato con freccia verso l'alto)
3. Scorri il menu e tocca **"Aggiungi a Home"**
4. Tocca "Aggiungi" in alto a destra
5. L'icona del quiz apparirà sulla home, come una vera app
6. Da quel momento funzionerà anche senza connessione internet
7. I dati (sessioni salvate) restano solo sul tuo telefono

## Come si installa su Android
1. Apri il link in **Chrome**
2. Apparirà un banner "Aggiungi Quiz Medicina a Home" — tocca "Installa"
3. In alternativa: menu tre puntini → "Installa app"

---

## Se devi aggiornare il quiz in futuro
Quando modifichi i file e li ripubblichi, apri `sw.js` e cambia la riga
`const CACHE_NAME = 'quiz-medicina-v1';` in `'quiz-medicina-v2'`, poi `v3`, ecc.
Questo forza i dispositivi a scaricare la nuova versione invece di mostrare quella vecchia in cache.
