# TankBack : page de préinscription (aperçu Convtek)

Aperçu de travail de la page de préinscription TankBack, partagé avec le client pendant la construction.
Page en `noindex`, robots.txt bloquant, tracker coupé, formulaire simulé (aucune adresse enregistrée).
Pas de bandeau en haut de page (retiré le 2026-11-13 à la demande du consultant) : seule une mention après l'envoi du formulaire signale l'aperçu.

URL : https://convtek.github.io/lp-tankback-preinscription/

## Republier après une modification

Depuis `05-Exports/tankback-lead-foyer` :

```
VITE_PREVIEW=true npx vite build --base ./ --outDir dist-preview --emptyOutDir
```

puis copier le contenu de `dist-preview/` ici (sans écraser `README.md`, `.nojekyll` ni `robots.txt`),
et dans `index.html` :
- ajouter `<meta name="robots" content="noindex, nofollow" />`
- remplacer le commentaire « Canonical » par `<link rel="canonical" href="https://convtek.github.io/lp-tankback-preinscription/" />`
- ajouter `<meta property="og:url" content="https://convtek.github.io/lp-tankback-preinscription/" />`

Ensuite commit et push sur `main` avec le compte GitHub Convtek.

Ne jamais publier ici un build sans `VITE_PREVIEW=true` : le formulaire de production refuse les envois tant que
l'outil d'emailing n'est pas branché, et le tracker enverrait des événements vers une API absente.
