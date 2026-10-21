# 01 · Quels services exigent une IP chinoise

Il n'y a qu'un seul critère : quand le service voit que votre IP d'origine n'est pas en Chine continentale, il vous refuse ou vous offre un service réduit. Le tableau ci-dessous va du blocage le plus strict au moins strict.

| Catégorie | Exemples | Sans IP chinoise | Ce qui est vérifié en plus de l'IP |
|---|---|---|---|
| Vidéo | iQIYI, Tencent Video, Youku, Mango TV, certaines séries d'animation sur Bilibili | Message indiquant que c'est réservé à la Chine continentale, ou seulement les contenus gratuits | Région de la boutique d'apps, lieu d'inscription du compte |
| Musique | NetEase Cloud Music, QQ Music, Kugou | Un grand nombre de morceaux sont grisés et illisibles | Rien |
| Services administratifs | Plateforme nationale des services publics, sites de services publics des provinces, impôts, sécurité sociale, fonds de prévoyance logement | La page ne s'ouvre pas, ou le code de vérification n'arrive jamais | Numéro de téléphone, reconnaissance faciale |
| Éducation | CHSI, site des diplômes universitaires, systèmes de gestion de la scolarité des universités | Ne s'ouvre pas, ou extrêmement lent | Rien |
| Voyage | 12306, sites des compagnies aériennes | Ne s'ouvre pas, le paiement échoue | Numéro de téléphone, paiement |
| Finance | Banque en ligne, banque mobile, Alipay, WeChat Pay | Connexion bloquée par le contrôle des risques, virements en échec | Carte SIM, empreinte de l'appareil, visage |
| Jeux | Jeux PC et mobiles sur serveurs chinois | Connexion possible, mais forte latence et déconnexions | Vérification d'identité réelle |
| Vie quotidienne | Meituan, Ele.me, DiDi, certaines fonctions de Taobao | Erreurs de localisation, commandes en échec | Localisation, numéro de téléphone |
| Diffusion en direct | Douyin, Kuaishou, Douyu | Inaccessible dans certaines régions | Rien |

## Une distinction importante

**« Avoir besoin d'une IP chinoise » et « avoir besoin d'un numéro de téléphone chinois » sont deux choses différentes.** La vidéo et la musique ne regardent que l'IP : changer d'IP suffit. Les services administratifs, la banque et la réservation de billets exigent en plus de l'IP de recevoir un code de vérification par SMS et de passer une reconnaissance faciale. L'IP résout la question « est-ce que ça s'ouvre » ; la vérification qui suit dépend de votre propre numéro de téléphone chinois et de vos pièces d'identité.

## Comment résoudre la question de l'IP

Envoyer d'abord le trafic vers un serveur en Chine continentale, qui accède ensuite à la destination. Il y a trois façons de procéder : un client, le proxy web ou un routeur. Pour choisir, voir [Quelle méthode de connexion pour quelle situation](../network/02-choose-your-connection-method.md) dans le dossier voisin.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-01) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-01) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
