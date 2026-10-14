# Ma Farde de Stage — HEFF AIP3

Farde numérique pour l’École Clair-Soleil, Monsieur Mottry, du 2 au 20 novembre 2026.

## Site
- `index.html` : site statique, à publier à la racine sur GitHub Pages.
- `app.js`, `styles.css` : logique et styles.
- `documents/` : 6 PDF accessibles dans la farde, dont le nouveau planning A/B. ATTENTION : ces documents deviennent accessibles publiquement si GitHub Pages est public. Ne pas publier de documents ou données personnelles d’élèves.
- `CNAME` : domaine personnalisé souhaité `farde.lucasdevers.be` ; nécessite la configuration DNS et GitHub Pages.

## Fonctionnalités
- 9 intercalaires, vue farde classique + mode livre.
- Fichiers ajoutés conservés automatiquement avec **IndexedDB** sur le navigateur/appareil utilisé ; notes et classement des PDF intégrés conservés avec **localStorage**.
- Le bouton « ↔ Déplacer » fonctionne pour les fichiers personnels ainsi que les documents initiaux, vers un autre intercalaire ou une journée. Le PDF source initial n'est pas modifié.
- Bouton « Sauvegarder » : export JSON comprenant les documents ajoutés, notes, paramètres et déplacements. « Restaurer une sauvegarde » : import sur un autre navigateur.
- **Aucune sauvegarde cloud synchronisée** : GitHub Pages héberge les fichiers du site mais ne conserve pas les nouveaux téléversements des visiteurs sur GitHub. Il faut un backend avec authentification pour synchroniser automatiquement entre appareils.
- Avant de changer d’adresse ou de navigateur, télécharger une sauvegarde JSON et la restaurer sur le nouveau site.

## Publication (action requise sur GitHub)
1. Créer un dépôt GitHub (ex. `farde-stage-heff`) et y importer le dossier.
2. GitHub → dépôt → Settings → Pages → Deploy from a branch → `main` / `/(root)` ; sauvegarder.
3. Configurer le sous-domaine dans la zone DNS OVH avec les valeurs GitHub Pages, puis valider le domaine personnalisé dans GitHub Pages.
4. Activer « Enforce HTTPS » dès que disponible.

⚠ GitHub Pages public : ne stocker dans le dépôt que les fichiers que l'on souhaite rendre accessibles. Les fichiers téléversés *via le site* restent uniquement dans le navigateur qui les a ajoutés.

## Code demandé avant chaque ajout
- Le site demande le code choisi à chaque nouvel ajout de document (bouton « Ajouter », bouton dans un intercalaire, ou glisser-déposer sur une feuille).
- Le code est également demandé avant une restauration de sauvegarde qui importe des documents.
- La validation n'est pas conservée après l'ajout : la boîte de dialogue se rouvre à l'opération suivante.
- **Important** : ce code est une confirmation locale dans le navigateur, **pas une authentification sécurisée**. Le code et les fichiers sources d'un site statique peuvent être consultés par quelqu'un qui accède au code du site. Un véritable accès privé nécessite une authentification côté serveur et un stockage privé. Ne pas confier des données d'élèves confidentielles à un dépôt public.

## Planning (mise à jour)
Le PDF `documents/planning-stage-mottry-semaines-A-et-B.pdf` remplace les deux anciens horaires. Il réunit la semaine A et la semaine B du planning transmis par l’étudiant. Le document Word d’origine est conservé dans la version téléchargeable, pas publié sur GitHub.
