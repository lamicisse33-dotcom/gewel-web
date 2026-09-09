# gewel.khalam.app — page d'attente

Une seule page. Elle affiche la marque KHALAM pendant que le serveur GÉWEL se
réveille, puis bascule dessus toute seule.

## Pourquoi elle existe

Le serveur GÉWEL est hébergé chez Render sur l'offre gratuite : il s'endort
après 15 minutes sans visite et met environ une minute à revenir. Pendant ce
temps, Render affiche **sa** page à lui — fond noir, logo Render,
« APPLICATION LOADING ». Sur une démonstration, c'est la marque de
l'hébergeur qu'on montre.

Cette page-ci vit ailleurs (GitHub Pages, toujours éveillé). Elle s'affiche
tout de suite, réveille le serveur en arrière-plan, et n'ouvre GÉWEL qu'une
fois qu'il répond vraiment.

## Ce qu'il faut savoir

- Le raccourci de l'écran d'accueil doit pointer sur **gewel.khalam.app**,
  plus sur l'adresse Render.
- Le fichier `CNAME` porte le sous-domaine. Ne pas le supprimer : GitHub Pages
  s'en sert pour servir le site sous ce nom.
- Si l'adresse du serveur change un jour, une seule ligne à modifier dans
  `index.html` :

      const SERVEUR = 'https://gewel-app.khalam.app';

## Réglage DNS (fait une fois, chez Namecheap)

Un enregistrement **CNAME** : hôte `gewel`, valeur `lamicisse33-dotcom.github.io`

## L'icône

`icone.svg` est le dessin d'origine : la balance KHALAM surmontée d'une antenne.
Les fichiers `icone-32/180/192/512.png` en sont tirés — ne pas les modifier à la
main, les regénérer :

    for t in 180 192 512 32; do
      convert -background '#0B1020' -density $((t*4)) icone.svg \
              -resize ${t}x${t} -depth 8 -strip icone-${t}.png
    done

L'image reste **carrée et opaque** : iOS arrondit lui-même les coins, et une
image déjà arrondie ressort avec des coins doubles.

Le raccourci de l'écran d'accueil ne change pas d'icône tout seul : il faut le
supprimer et le recréer depuis Safari (Partager → Sur l'écran d'accueil).
