# gewel.khalam.app — page d'attente

Une seule page. Elle affiche la marque KHALAM pendant que le serveur GEWEL se
réveille, puis bascule dessus toute seule.

## Pourquoi elle existe

Le serveur GEWEL est hébergé chez Render sur l'offre gratuite : il s'endort
après 15 minutes sans visite et met environ une minute à revenir. Pendant ce
temps, Render affiche **sa** page à lui — fond noir, logo Render,
« APPLICATION LOADING ». Sur une démonstration, c'est la marque de
l'hébergeur qu'on montre.

Cette page-ci vit ailleurs (GitHub Pages, toujours éveillé). Elle s'affiche
tout de suite, réveille le serveur en arrière-plan, et n'ouvre GEWEL qu'une
fois qu'il répond vraiment.

## Ce qu'il faut savoir

- Le raccourci de l'écran d'accueil doit pointer sur **gewel.khalam.app**,
  plus sur l'adresse Render.
- Le fichier `CNAME` porte le sous-domaine. Ne pas le supprimer : GitHub Pages
  s'en sert pour servir le site sous ce nom.
- Si l'adresse du serveur change un jour, une seule ligne à modifier dans
  `index.html` :

      const SERVEUR = 'https://gewel-backend.onrender.com';

## Réglage DNS (fait une fois, chez Namecheap)

Un enregistrement **CNAME** : hôte `gewel`, valeur `lamicisse33-dotcom.github.io`
