# 11 · Fibre à 1 ou 2 Gbit/s avec un routeur : qu'est-ce qui détermine le débit

Les accès Internet domestiques sont de plus en plus rapides, d'où une question fréquente : ma ligne est en gigabit, voire en 2 Gbit/s, qu'est-ce que j'obtiendrai à travers un routeur VPN ?

## La réponse courte

Pour le trafic qui passe par le tunnel, le débit est déterminé par le tronçon qui sort de Chine. **Le goulot d'étranglement n'est pas votre ligne, c'est le tronçon qui sort de Chine.** Nous garantissons une lecture fluide de YouTube. Le débit exact dépend des points ci-dessous.

Le trafic vers les services chinois n'emprunte pas le tunnel et garde toute la vitesse de votre accès. Voir [10 · Le NAS, l'imprimante et les caméras seront-ils affectés ?](10-nas-printer-camera-behind-router.md)

## Quatre facteurs qui déterminent le débit

**1. Le tronçon transfrontalier**
La capacité internationale est partagée par tout le monde et n'a rien à voir avec la vitesse de votre abonnement. De 20 h à 23 h, heure de Pékin, c'est l'heure de pointe nationale ; sur cette plage, choisissez une région au voyant vert. Si c'est toujours lent, la cause habituelle est l'accès Internet local (haut débit partagé de résidence, ou opérateur et région mal assortis ; voir le point suivant). Voir [Pourquoi c'est parfois rapide, parfois lent](../network/06-why-sometimes-fast-sometimes-slow.md).

**2. Votre opérateur et la région choisie**
Chaque opérateur sort de Chine par un chemin différent, et choisir la bonne région compte plus que tout :
- China Unicom dans le nord : essayez d'abord le Japon et la Corée
- China Telecom dans le sud : essayez d'abord l'Asie du Sud-Est
- Autres opérateurs : essayez d'abord les régions de relais en Chine

**3. Le routeur lui-même**
Le trafic doit être chiffré avant d'entrer dans le tunnel, et c'est le processeur du routeur qui s'en charge. Les modèles diffèrent beaucoup :
- GL-MT300N-V2 (mini) : ports 100 Mbit/s. Suffisant pour du 1080p sur un téléphone ou un portable, pas à la hauteur d'une ligne rapide
- GL-MT3000 (portable) : tient la charge d'un petit foyer. Le premier routeur pour la plupart des gens
- GL-MT6000 (de bureau) : port 2,5G. Pour beaucoup d'appareils, la 4K et les consoles de jeu

Avec une ligne rapide et un foyer chargé, choisissez le MT3000 ou le MT6000, pas le mini.

**4. Les derniers mètres à la maison**
Câblez le téléviseur et l'ordinateur de bureau dès que possible. Le Wi-Fi dans un immeuble dense subit de fortes interférences, et bien des « la ligne est lente » se révèlent venir de l'intérieur du logement.

## Quand ça semble lent, essayez dans cet ordre

1. Changez de région. Essayez-en deux ou trois et trouvez celle qui tient à cette heure-ci.
2. Activez « Automatically pick the fastest line » (choisir automatiquement la ligne la plus rapide) dans la page d'administration. Il choisit la ligne avec la latence et les pertes les plus faibles, et bascule quand cela change. Notez que le pays de sortie peut alors différer de la région choisie.
3. Branchez par câble l'appareil sur lequel vous regardez les vidéos.
4. Vérifiez si c'est seulement ce site-là. Si les autres sites sont rapides au même moment, la lenteur vient de l'autre bout.

## Comment savoir avant d'acheter

Inscrivez-vous et prenez l'essai gratuit de 4 heures, sans carte bancaire. Connectez-vous à l'heure où vous l'utilisez le plus, le soir par exemple, et regardez une vidéo YouTube en HD. Ce que vous voyez sur un téléphone ou un portable est proche de ce que vous donnera le routeur. Décidez pour le routeur ensuite.

## FAQ

**Pourquoi ne pas me donner simplement un nombre de mégabits ?** Parce que ce nombre change pour chaque personne et à chaque heure. Nous garantissons une lecture fluide de YouTube, même à l'heure de pointe du soir, à condition que votre accès Internet soit bon : China Unicom dans le nord ou China Telecom dans le sud. Le haut débit partagé des résidences (accès mutualisé fourni par l'immeuble, très répandu en Chine) fait exception. Prendre l'essai gratuit de 4 heures et tester vous-même reste le test le plus fiable.

**Le site de test de débit affiche un chiffre bas, mais la vidéo se lit bien ?** C'est normal. Les serveurs de test ont eux-mêmes leurs moments chargés et calmes, et deux tests à une minute d'écart peuvent varier du simple au double. Jugez sur ce que vous voulez réellement faire.

**Un routeur plus cher ira-t-il plus vite ?** Seulement si le routeur est le goulot d'étranglement, par exemple un modèle mini sur une ligne rapide. Quand le goulot est le tronçon transfrontalier, un nouveau routeur n'y change rien, et une autre région, si.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-11) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-11) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
