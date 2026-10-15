# 06 · Débloquer les sites vidéo chinois depuis l'étranger avec un routeur

## Pourquoi un routeur plutôt qu'un client sur chaque appareil

- Les téléviseurs, box TV, vidéoprojecteurs et consoles de jeu ne peuvent pas installer de client : le routeur est la seule solution.
- Avec beaucoup de monde à la maison, configurer chaque appareil de chaque personne n'est pas réaliste ; configurez le routeur une fois, et tout appareil qui se connecte au Wi-Fi en profite aussitôt.
- Le routage sélectif se fait sur le routeur : les sites et les appareils locaux continuent de se connecter directement, seuls les domaines des vidéos chinoises passent par la ligne vers la Chine, et le débit n'en souffre pas.

## Ce qu'il vous faut

| Élément | Remarques |
|---|---|
| Un routeur compatible | Un routeur préinstallé fonctionne dès la sortie du carton ; si vous le flashez vous-même, voir [Comment flasher le firmware](02-flash-firmware-yourself.md) |
| Un compte | Les comptes Personnel, Famille et Entreprise prennent tous en charge la fonction routeur. Après l'inscription, demandez d'abord l'essai gratuit pour valider toute la procédure : un nouveau compte est en formule Personnel, avec un essai de 24 heures |
| Un réseau en amont | La box ou le routeur que vous avez déjà à la maison ; le nouveau routeur se branche derrière |

## C'est fait en cinq étapes

1. Reliez le port WAN du nouveau routeur au réseau en amont, branchez l'alimentation et attendez une minute.
2. Connectez votre téléphone au Wi-Fi du nouveau routeur, ouvrez l'adresse d'administration `http://192.168.11.1` et connectez-vous à votre compte.
3. Choisissez le mode **Split routing** (routage sélectif). Les domaines des vidéos chinoises sont dans la liste et passeront automatiquement par la ligne vers la Chine.
4. Passez le téléviseur et la box TV sur ce Wi-Fi, ou reliez-les par câble à un port LAN du nouveau routeur.
5. Ouvrez iQIYI, Tencent Video ou Yangshipin (CCTV) ; si la lecture est normale, c'est terminé.

## La liste est publique

Les domaines vidéo de la liste de routage sélectif sont tenus à jour dans un dépôt public : <https://github.com/vipinus/openwrt-2026-video-domains>. Si une plateforme refuse de lire, vous pouvez vérifier si son domaine figure dans la liste, et proposer un ajout s'il n'y est pas.

## Qualité d'image et bande passante

Le 1080p demande 5 Mbit/s stables, et la 4K 25 Mbit/s ou plus. Si la lecture saccade aux heures de pointe du soir, choisissez une région au vert ; si cela saccade encore, la cause habituelle est l'accès Internet local. Pour la région d'entrée, choisissez-en une proche de vous et bien reliée à la Chine continentale ; essayez-en deux ou trois et jugez d'après les saccades.

## FAQ

- **Ça marche sur le téléphone mais pas sur la télévision** : la télévision est encore connectée à l'ancien Wi-Fi, ou l'appli de la télévision est l'édition internationale.
- **Certaines plateformes marchent et d'autres non** : le domaine de cette plateforme n'est pas dans la liste de routage sélectif. Passez temporairement en « Global » (tout par la ligne) pour vérifier, puis proposez-le au dépôt de la liste.
- **Tout le foyer ralentit avec un vieux routeur** : le processeur ne suit pas le trafic chiffré ; passez à un modèle plus performant, voir [Premiers pas avec un routeur préinstallé](01-plug-and-play-router.md).

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-06) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-06) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
