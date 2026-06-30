# Échéo — Site de présentation (GitHub Pages)

Site statique = vitrine + URL **marketing / support / confidentialité** demandées par App Store Connect.

```
site/
├── index.html              → landing FR
├── privacy/index.html      → confidentialité FR
├── support/index.html      → support FR (FAQ + contact)
├── en/index.html           → landing EN
├── en/privacy/index.html   → privacy EN
├── en/support/index.html   → support EN
└── assets/icon.svg         → icône (vectorielle, pas de capture requise)
```

> Le hero et les écrans sont **dessinés en CSS** (aucune image externe) → le site s'affiche
> parfaitement sans avoir à fournir de captures. Tu pourras les remplacer par de vraies captures plus tard.

## Déployer (2 min)
1. Crée un repo public **`echeo`** sur ton compte GitHub (**`omgprod`**).
2. Copie tout le contenu de ce dossier `site/` à la racine du repo.
3. Repo → **Settings → Pages** → Source : branche `main`, dossier `/ (root)` → **Save**.
4. Après 1-2 min, le site est en ligne :
   - Landing : `https://omgprod.github.io/echeo/`
   - Confidentialité : `https://omgprod.github.io/echeo/privacy/`
   - Support : `https://omgprod.github.io/echeo/support/`

### Commandes (depuis ce dossier)
```bash
cd apps/Echeo/site
git init && git add . && git commit -m "Échéo — site de présentation"
git branch -M main
git remote add origin https://github.com/omgprod/echeo.git
git push -u origin main
# puis active Pages dans Settings → Pages (branche main, /root)
```

## Brancher dans l'app & App Store Connect
- `AppConfig.swift` → `privacyPolicyURL` = `https://omgprod.github.io/echeo/privacy/` (déjà pré-rempli).
- App Store Connect : **URL marketing** = landing, **URL d'assistance** = `/support/`,
  **Politique de confidentialité** = `/privacy/`.

## À personnaliser (optionnel)
- Le contact est déjà `h.brian@la-becanerie.com` (3 + 3 fichiers).
- Dans `index.html` / `en/index.html`, mets le **lien App Store** réel à la place de `#` une fois publié.
- (Option) Ajoute de vraies captures dans `assets/` et remplace le mockup CSS par une `<img>`.

## Tester en local
```bash
cd apps/Echeo/site && python3 -m http.server 8000
# ouvre http://localhost:8000
```
