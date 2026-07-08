# Braise — Minuteur Pomodoro

Application web installable (PWA) : grand chiffre sur fond noir, sonnerie de fin synthétisée (aucun fichier audio externe), préréglages + temps personnalisés, fonctionne hors-ligne, installable sur ordinateur, téléphone et tablette.

## Fichiers
- `index.html` — l'application complète (HTML + CSS + JS, un seul fichier)
- `manifest.json` — permet l'installation comme une vraie app (icône, écran d'accueil)
- `sw.js` — service worker, rend l'app utilisable hors connexion
- `icon-192.png`, `icon-512.png` — icônes de l'app

## Tester en local
```
python3 -m http.server 8000
```
puis ouvrir `http://localhost:8000` dans le navigateur.

## Publier gratuitement (3 options, aucune carte bancaire requise)

### Option A — GitHub Pages (recommandé, le plus pérenne)
1. Crée un compte gratuit sur https://github.com si tu n'en as pas.
2. Crée un nouveau dépôt (repository), par exemple `pomodoro-braise`. Public.
3. Mets les 5 fichiers de ce dossier dedans (glisser-déposer via l'interface web GitHub, ou `git push`).
4. Dans le dépôt : **Settings → Pages → Source : "Deploy from a branch"**, choisis la branche `main` et le dossier `/ (root)`. Sauvegarde.
5. Après 1-2 minutes, ton app est en ligne à une adresse du type :
   `https://ton-pseudo.github.io/pomodoro-braise/`
6. C'est public, gratuit, et ça reste en ligne indéfiniment.

### Option B — Netlify (le plus rapide, glisser-déposer)
1. Va sur https://app.netlify.com/drop
2. Glisse le dossier entier `pomodoro` dans la zone de dépôt.
3. Netlify te donne immédiatement une URL publique (ex : `https://braise-123abc.netlify.app`).
4. Tu peux créer un compte gratuit ensuite pour garder ce site et changer le nom.

### Option C — Vercel
1. Compte gratuit sur https://vercel.com
2. "Add New Project" → importer un dossier ou un dépôt GitHub → Deploy.
3. URL publique fournie automatiquement.

Les trois sont 100% gratuits pour ce type de site statique, sans limite de temps.

## Installer l'app sur téléphone / tablette / ordinateur
Une fois le site en ligne (n'importe laquelle des 3 options) :

- **Android (Chrome)** : ouvrir le lien → menu (⋮) → "Ajouter à l'écran d'accueil" / "Installer l'application".
- **iPhone/iPad (Safari)** : ouvrir le lien → bouton Partager (carré avec flèche) → "Sur l'écran d'accueil".
- **Ordinateur (Chrome/Edge)** : ouvrir le lien → une icône d'installation apparaît dans la barre d'adresse (à droite) → cliquer → "Installer".

Une fois installée, l'app s'ouvre en plein écran comme une app native, avec sa propre icône, et fonctionne même sans connexion internet grâce au service worker.

## Fonctionnalités
- Temps affiché en très grand, fond noir
- Anneau de progression autour du chiffre
- Préréglages : 5, 15, 25, 50 min (modifiables)
- Clic sur le chiffre (ou bouton "+ créer") pour taper n'importe quel temps personnalisé, qui devient un nouveau préréglage réutilisable et supprimable
- Sonnerie douce (carillon à 3 notes) générée directement par le navigateur — pas de fichier audio à héberger
- Vibration sur mobile en plus du son
- Notification système si l'onglet est en arrière-plan (après autorisation)
- Préférences sauvegardées localement (temps choisi, préréglages, son activé/désactivé)
- Raccourci clavier : barre d'espace pour démarrer/mettre en pause

## Personnaliser
Tout est dans `index.html`. Les couleurs sont regroupées en haut du `<style>` dans `:root` (variables `--bg`, `--ember`, etc.) si tu veux changer la palette.
