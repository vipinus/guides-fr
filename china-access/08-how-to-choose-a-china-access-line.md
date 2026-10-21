# 08 · Choisir une ligne vers la Chine : d'où vient l'IP chinoise et où les offres gratuites échouent

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/choose-china-vpn?utm_source=github&utm_content=china-access-08

Une ligne vers la Chine ne fait qu'une chose : faire arriver les requêtes que vous envoyez depuis l'étranger chez Tencent Video, NetEase Cloud Music ou votre banque en ligne avec une IP de **Chine continentale**. Regardez donc d'abord deux points : la sortie est-elle vraiment une IP du continent, et une partie du trafic de l'appareil passe-t-elle à côté ? Le débit, le prix et le client viennent ensuite.

## D'où vient l'IP chinoise

Le fournisseur doit avoir ses propres serveurs en Chine continentale. Les hébergeurs cloud en Chine exigent un enregistrement sous nom réel pour démarrer une machine et facturent la bande passante à l'usage : le coût est donc bien plus élevé que pour des machines à l'étranger. C'est pourquoi presque tous les services sérieux vers la Chine sont payants, et pourquoi le nombre de sorties en Chine est limité.

Un substitut courant consiste à faire passer des machines à Hong Kong, à Taïwan ou au Japon pour des lignes « vers la Chine ». Ces adresses suffisent pour certaines sections de Bilibili réservées à Hong Kong, Macao et Taïwan, mais Tencent Video, iQIYI et Youku affichent toujours une restriction de droits, et la banque en ligne comme 12306 vous considèrent aussi à l'étranger. **Comment vérifier : une fois connecté, cherchez où l'IP est enregistrée ; elle ne compte que si elle indique « Chine · telle province ».**

## Cinq points à vérifier avant de choisir

| Point | Comment vérifier | À quoi ressemble un échec |
|---|---|---|
| Région de sortie | Cherchez où l'IP est enregistrée une fois connecté | Adresses de Hong Kong, Taïwan, Japon ou Corée |
| IPv6 et DNS | Recherchez « test ipv6 » et ouvrez une page de test | Le champ IPv6 indique le pays où vous êtes → les sites vidéo vous bloqueront encore, voir [Dépannage 03](../troubleshooting/03-ipv6-and-dns-leak.md) |
| Client | S'agit-il d'un protocole standard (AnyConnect, OpenVPN, Hiddify) ? | Une seule appli propriétaire, et une fois retirée, il ne vous reste rien |
| Bande passante | Lancez une vidéo 1080p entre 20 h et 23 h, heure de Pékin | Rapide en journée, chargement sans fin le soir |
| Plusieurs appareils et routeur | Combien d'appareils par compte, et un routeur peut-il connecter tout un foyer ? | Chaque appareil doit être acheté séparément |

## Pourquoi les lignes gratuites vers la Chine décrochent sans cesse

Le problème n'est pas la gratuité mais la structure des coûts. La bande passante de sortie sur le continent se paie à l'usage, et un service gratuit ne peut choisir qu'une option sur trois : entasser plusieurs milliers de personnes sur une machine, si bien que tout le monde saccade aux heures de pointe ; plafonner le trafic et la durée, si bien qu'une invitation à payer surgit en plein milieu ; ou gagner de l'argent autrement, en injectant de la publicité, en collectant l'historique de navigation, ou en faisant de votre appareil la sortie de quelqu'un d'autre.

Les extensions de navigateur gratuites « vers la Chine » ont un angle mort de plus : elles ne font passer que les requêtes web du navigateur, alors que le lecteur vidéo, les applis et le DNS du système n'y passent pas ; d'où le symptôme si fréquent « la page s'ouvre mais la vidéo ne se lit pas ».

Pour une recherche de temps en temps, le gratuit suffit. Pour suivre des séries, écouter de la musique et utiliser la banque en ligne, le temps que fait gagner une ligne payante stable vaut bien plus que l'abonnement. Demandez d'abord l'essai de 4 heures, testez une fois à l'heure de pointe du soir, puis décidez.

## Comment s'équiper : étudiants à l'étranger, voyageurs, familles

- **Étudiants à l'étranger** : les réseaux des résidences ont souvent l'IPv6, utilisez donc un client qui bloque l'IPv6 ; pour la banque en ligne, CHSI et 12306, ne connectez la ligne vers la Chine qu'au besoin et déconnectez-vous ensuite, pour limiter le contrôle des risques sur le compte.
- **Courts séjours** : installez un client Cisco ou Hiddify sur votre téléphone et importez la configuration en scannant le QR code ; tout fonctionne dès l'atterrissage.
- **Une famille installée durablement à l'étranger** : branchez sur la ligne un routeur flashé avec le firmware, et le téléviseur, la box TV et les téléphones des proches âgés n'ont besoin d'aucun réglage ; voir [Débloquer les sites vidéo chinois avec un routeur](../router/06-unlock-chinese-video-with-router.md).

## Un auto-test en 5 minutes

1. Connectez la ligne vers la Chine ; la recherche d'IP indique une province de Chine continentale.
2. La page de test IPv6 l'indique comme indisponible, ou aussi comme une adresse du continent.
3. Ouvrez sur Tencent Video n'importe quelle série réservée à la Chine ; elle se lit.
4. Relancez une vidéo 1080p après 20 h, heure de Pékin ; elle ne recharge pas sans arrêt.
5. Passez sur une autre sortie en Chine et refaites les trois premières étapes.

## FAQ

**Y a-t-il une différence entre un VPN vers la Chine et un accélérateur vers la Chine ?** Aucune différence de fond. Un « accélérateur » est généralement une appli conçue pour un jeu ou une plateforme vidéo, qui ne couvre que certaines applications ; un VPN est un tunnel pour tout l'appareil.

**Puis-je regarder Tencent Video avec un nœud à Hong Kong ?** Non, les droits ne couvrent que la Chine continentale.

**Combien d'appareils par compte ?** Chez LeoTun, les connexions simultanées dépendent de la formule : Personnel 2 appareils, Famille 4 appareils, Entreprise 8 appareils. Un routeur compte pour un appareil, et les appareils derrière lui ne sont pas comptés à part. Si plus d'appareils sont en ligne en même temps que la limite de votre formule, vous pouvez passer temporairement à une formule supérieure (le temps restant est converti à valeur égale selon le prix) et revenir en arrière ensuite.

**Puis-je utiliser Clash ?** Oui. LeoTun fournit un abonnement sing-box, un abonnement Clash et un lien de partage hysteria2. Avec Clash Meta, Clash Verge, FlClash, Stash et consorts, cliquez sur le bouton « Abonnement Clash » et collez l'URL dans la liste d'abonnements du client ; aucun convertisseur d'abonnement n'est nécessaire, et n'utilisez pas le lien de partage. Le Clash d'origine et Clash for Windows ne fonctionnent pas, car leur cœur ne gère pas hysteria2. Par défaut, cet abonnement fait passer par le nœud tout ce qui n'est pas votre réseau local : rien à modifier pour les vidéos chinoises ; si vous ajoutez vos propres règles, ne mettez pas les domaines chinois en « direct ».

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-08) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-08) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
