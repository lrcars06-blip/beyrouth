# Beyrouth Shawarma — site one-page

## Structure
- index.html          site complet (HTML + CSS + JS)
- sprites/            feuilles de sprites (20 images par feuille) pilotées par le scroll
- src/                clips MP4 d'origine + images clés (pour régénérer les frames)
- img/                logo.svg, devanture.jpg, shawarma-boeuf.jpg, shawarma-poulet.jpg, falafel.jpg
- video/intro.mp4     intro autoplay (façade) — à générer dès réception de la vidéo du client

## À fournir par le client
- img/logo.svg (ou logo.png)
- img/devanture.jpg (photo HD de la façade)
- img/shawarma-poulet.jpg, img/falafel.jpg
- video/intro.mp4 (généré à partir de la vidéo façade)

Sans ces fichiers le site fonctionne : le logo texte s'affiche, l'intro se saute.

## Tester
npx serve .        (ne pas ouvrir en file://)

## Régénérer les frames
voir README : extraire à 10 i/s en 560px puis regrouper par 20 en feuilles 4 colonnes (sprites/s{n}_{k}.webp)
Puis mettre à jour CONFIG.sequences[].count dans index.html.
