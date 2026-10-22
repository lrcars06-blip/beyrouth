# Beyrouth Shawarma — site one-page

## Structure
- index.html          site complet (HTML + CSS + JS)
- frames/s1..s4       séquences d'images pilotées par le scroll (WebP, 15 i/s)
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
for i in 1 2 3 4; do ffmpeg -i src/s$i.mp4 -vf "fps=15,scale=640:-2" -c:v libwebp -quality 62 frames/s$i/%04d.webp; done
Puis mettre à jour CONFIG.sequences[].count dans index.html.
