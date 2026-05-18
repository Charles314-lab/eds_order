# GuideHub EDS — Commande de Guides École du Sabbat

Page web statique pour faciliter la commande des guides de l'**École du Sabbat** (Église Adventiste du 7ème Jour), 2ᵉ trimestre 2026.

## Fonctionnalités

- **Identité visuelle officielle** : véritables logos téléchargés depuis les CDN officiels :
  - Logo SDA français centré blanc — `cdn.adventist.org/adventist-logo/2/fr/adventist-fr-centered--white.svg`
  - Logo Sabbath School & Personal Ministries blanc — `sspmadventist.org/_next/static/media/sspmwhitelogo.0edbe94b.png`
  - Couleurs officielles : denim blue PMS 302 `#2F557F` + or `#F2A900`.
- **N° de commande automatique** au format `YYYYMMDD-HHMMSS` (non modifiable).
- **Sélection souple** : 1 guide unique (adulte OU moniteur) ou répartition libre entre adulte/moniteur si plusieurs guides.
- **Calcul automatique du total** : Adulte 2 000 FCFA · Moniteur 4 000 FCFA.
- **3 modes de paiement** : Wave, Orange Money (avec avertissement frais retrait + 10 % soutien), Espèces.
- **Envoi WhatsApp formaté** au `+223 74 13 00 84` via lien `wa.me` pré-rempli.
- **100 % statique** — aucun backend nécessaire, déployable sur GitHub Pages gratuitement.

## Aperçu du message WhatsApp

```
🌟 *NOUVELLE COMMANDE GUIDE EDS*
━━━━━━━━━━━━━━━━━━

📌 *N° Commande* : 20260518-143752
📅 *Trimestre* : T2 2026 — Croître dans une relation avec Dieu
👤 *Nom & Prénom* : Diarra Aïssata

📖 *DÉTAIL COMMANDE*
• Guides Adulte : 2 × 2 000 = 4 000 FCFA
• Guides Moniteur : 1 × 4 000 = 4 000 FCFA
• Langue : Français
• Total guides : 3

💰 *TOTAL À PAYER : 8 000 FCFA*

💳 *Mode de paiement* : Orange Money
⚠️ _Frais de retrait + 10% frais de soutien à ajouter_
📱 N° OM : +223 74 13 00 84

📸 _Capture d'écran du paiement à envoyer juste après ce message._

━━━━━━━━━━━━━━━━━━
_Commande envoyée via GuideHub EDS_
```

## Déploiement sur GitHub Pages

### Option 1 — Via l'interface GitHub (la plus simple)

1. Créer un nouveau repo GitHub public, ex : `guidehub-eds`.
2. Glisser-déposer le fichier `index.html` dans le repo via l'interface web.
3. Aller dans **Settings → Pages**.
4. Sous **Source**, choisir **Deploy from a branch**, branche `main`, dossier `/ (root)`.
5. Cliquer **Save**. L'URL sera `https://<ton-username>.github.io/guidehub-eds/`.

### Option 2 — En ligne de commande

```bash
cd C:\Users\SAMKO\Desktop\guidehub-eds
git init
git add .
git commit -m "init: formulaire commande guides EDS T2 2026"
git branch -M main
git remote add origin https://github.com/<ton-username>/guidehub-eds.git
git push -u origin main
```

Puis activer GitHub Pages dans **Settings → Pages**.

## Personnalisation rapide

Tout est configurable en haut du `<script>` dans `index.html` :

```js
const PRIX = { adulte: 2000, moniteur: 4000 };
const WHATSAPP_NUM = "22374130084";  // format E.164 sans le +
const TITRE_QUARTER = "T2 2026 — Croître dans une relation avec Dieu";
```

## Test local

Double-cliquer sur `index.html` pour l'ouvrir dans le navigateur, ou lancer un mini-serveur :

```powershell
cd C:\Users\SAMKO\Desktop\guidehub-eds
python -m http.server 8000
```

Puis ouvrir [http://localhost:8000](http://localhost:8000).

## Structure

```
guidehub-eds/
├── index.html      # Page complète : HTML + CSS + JS
├── README.md       # Ce fichier
└── assets/         # Logos officiels téléchargés depuis les CDN adventistes
    ├── adventist-fr-centered--white.svg   # Logo SDA FR (utilisé dans le header)
    ├── adventist-fr-centered--denim.svg   # Variante bleu denim
    ├── adventist-symbol--white.svg        # Symbole seul, blanc
    ├── adventist-symbol--denim.svg        # Symbole seul, denim
    ├── adventist-symbol--black.svg        # Symbole seul, noir
    ├── sspmwhitelogo.0edbe94b.png         # Logo SSPM blanc (utilisé dans le header)
    ├── sspm.png                           # Logo SSPM bleu (variante)
    └── sabbathschool-400x356-1.jpg        # Symbole École du Sabbat seul (variante)
```

**Important** : lors du push GitHub, conserver le dossier `assets/` à côté de `index.html`.

---

> « Ta parole est une lampe à mes pieds, et une lumière sur mon sentier. » — Ps 119:105
