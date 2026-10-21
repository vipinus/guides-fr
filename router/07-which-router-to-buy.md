# 07 · Faut-il un routeur, et comment choisir parmi les quatre modèles

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/router?utm_source=github&utm_content=router-07

Le routeur résout le problème du « trop d'appareils, dont certains ne peuvent pas installer de client » : le VPN est configuré une fois sur le routeur, et le téléviseur, la console de jeu, l'enceinte connectée et le téléphone du parent âgé passent tous automatiquement par lui, sans rien installer. Il suffit d'un routeur qu'on peut flasher et de dix minutes de flashage. **Les comptes Personnel, Famille et Entreprise peuvent tous utiliser un routeur.**

## Quand en prendre un, et quand s'en passer

| En prendre un | S'en passer |
|---|---|
| Vous avez à la maison des appareils qui ne peuvent pas installer de client : box TV, console de jeu, Apple TV, enceinte connectée | Vous n'avez qu'un téléphone et un ordinateur et vous êtes surtout en déplacement professionnel : installer un client est plus léger |
| La famille est nombreuse et vous ne voulez pas tout expliquer appareil par appareil | Vous vivez en résidence ou en colocation et ne maîtrisez pas le réseau |
| Vous avez des appareils qui doivent rester connectés 24 h/24 (NAS, envoi des caméras) | Votre routeur principal est une box verrouillée par l'opérateur et vous ne pouvez pas brancher un second routeur : un routeur de voyage fait un compromis |
| Un bureau en Chine ou toute une famille qui accède en permanence aux services étrangers depuis la Chine, avec le routage sélectif sur le routeur et rien à faire sur les appareils | |

## Flasher le firmware ou acheter un modèle prêt à l'emploi

Les deux voies aboutissent au même firmware. La différence, c'est qui fait le flashage et qui est responsable en cas de problème.

- **Le flasher vous-même** : vous avez déjà un routeur pris en charge par OpenWrt (plus de 1000 modèles). Le firmware est compilé en ligne sur le site et vous recevez le lien par e-mail en 3 à 5 minutes ; suivez ensuite pas à pas [02 · Flasher le firmware vous-même](02-flash-firmware-yourself.md) (avec vidéo). Pour ceux qui sont à l'aise avec les réglages techniques et veulent économiser le prix d'un appareil.
- **Acheter un modèle prêt à l'emploi** : nous expédions un GL.iNet déjà flashé ; pour les trois étapes au déballage, voir [01](01-plug-and-play-router.md). Pour ceux qui ne veulent pas bricoler, ou pour équiper des proches peu à l'aise avec la technique.

Dans les deux cas, le firmware met à jour ses composants tout seul, sans reflasher ; et quand les adresses de la ligne changent, vous n'avez pas non plus à toucher à la configuration.

## Quatre routeurs, selon l'usage

| Modèle | Type | Prix | Inclus | Ce que c'est | Idéal pour |
|---|---|---|---|---|---|
| GL-MT300N-V2 | Mini | 200 $ | 12 mois de service | Tient dans la main, alimenté en USB (une batterie externe suffit) ; Wi‑Fi 2,4 GHz uniquement, ports 100 Mbit/s | Une personne en voyage : Ethernet ou Wi‑Fi de l'hôtel, un téléphone et un portable pour naviguer et regarder du 1080p. Pas fait pour être le routeur principal de la maison |
| **GL-MT3000** | Portable | 300 $ | 24 mois de service | Wi‑Fi 6 bibande avec un port 2,5G, à peine plus grand que la paume | Le routeur principal d'un petit foyer (téléviseur, box de streaming, plusieurs téléphones et ordinateurs), et assez petit pour un sac à dos |
| GL-MT6000 | De bureau | 400 $ | 24 mois de service | Deux ports 2,5G plus quatre ports gigabit, antennes externes, la plus grande puissance de calcul | Grands logements, beaucoup d'appareils (une douzaine ou plus), accès Internet au-delà du gigabit, 4K et jeux sur console, ou petit bureau. Reste à poste fixe comme unique routeur |
| GL-XE3000 | Mobile | 400 $ | 24 mois de service | 5G/4G et batterie intégrées ; avec une carte SIM, c'est un réseau autonome, et il accepte aussi l'Ethernet | Lieux sans accès fixe : camping-cars, chantiers, salons professionnels, locations courtes ; ou secours pour la ligne de la maison |

Les mois inclus s'entendent en formule Personnel ; Famille en reçoit la moitié et Entreprise le quart, pour la même valeur. Livraison gratuite dans le monde entier, en général sous 3 à 14 jours, retour possible sous 30 jours.

### Choix rapide selon la situation

- Seul en voyage, à l'hôtel, avec un petit budget → GL-MT300N-V2
- Un appartement ou un petit foyer où le téléviseur et la box de streaming doivent lire des vidéos chinoises ou étrangères → GL-MT3000
- Surtout à la maison, mais vous voulez l'emporter en voyage de temps en temps → GL-MT3000
- Un grand logement, beaucoup d'appareils, un accès au-delà du gigabit, ou un bureau partagé → GL-MT6000
- Pas d'accès fixe, ou vous êtes la plupart du temps sur la route → GL-XE3000
- Pour équiper des parents peu à l'aise avec la technique → GL-MT3000, acheté préinstallé : on le branche et ça marche

## Pourquoi le GL-MT3000 est notre premier choix

- **Un appareil, deux rôles.** Assez puissant pour être le routeur principal d'un petit foyer, assez petit pour voyager. C'est le seul des quatre à faire les deux.
- **Il ne vieillira pas vite.** Le Wi‑Fi 6 et le port 2,5G laissent de la marge par rapport à la plupart des accès Internet domestiques. Le mini n'a que du Wi‑Fi 2,4 GHz et des ports 100 Mbit/s, qui deviennent le goulot d'étranglement à la maison.
- **Le prix se tient.** 300 $ avec 24 mois de service en formule Personnel, contre 200 $ avec 12 mois pour le mini. Service inclus compris, les 100 $ de plus vous offrent un appareil nettement meilleur plus une année supplémentaire.
- **C'est celui que nous connaissons le mieux.** Notre propre appareil de test est ce modèle, les nouveaux firmwares y sont vérifiés en premier, et le [tutoriel vidéo de flashage](02-flash-firmware-yourself.md) l'utilise. En cas de problème, nous avons le même appareil sur le bureau pour comparer.

Quand ne pas le choisir : pour un grand logement, beaucoup d'appareils ou un accès au-delà du gigabit, prenez directement le GL-MT6000 ; sans accès fixe, le GL-XE3000 ; si c'est pour une seule personne en voyage et que le prix prime, le GL-MT300N-V2 suffit.

## Les trois problèmes les plus fréquents au démarrage

- **Signal Wi‑Fi faible, seulement 20 dBm** : le firmware règle automatiquement la puissance d'émission selon la réglementation du pays où vous êtes, et ne passe au niveau de votre pays qu'une fois le routeur passé en ligne. Juste après le flashage, branchez d'abord un câble réseau.
- **Les sites chinois deviennent lents** (quand vous êtes en Chine) : le routage sélectif est désactivé et tout passe par la ligne. Repassez en mode routage sélectif : pour accéder aux services étrangers depuis la Chine, seuls les sites bloqués passent par défaut par la ligne, tandis que les sites chinois et les sites étrangers qui s'ouvrent déjà normalement depuis la Chine restent en direct.
- **En Chine, un site étranger ne s'ouvre pas** : dans « VPN settings » (réglages VPN), partie routage sélectif intelligent, décochez « Blocked sites only » (sites bloqués uniquement), ou passez temporairement en « Global », et réessayez ; s'il s'ouvre alors, le site est bloqué mais pas encore dans la liste : envoyez l'adresse au service client.
- **À l'étranger, vous voulez des contenus chinois** : choisissez « Reverse Split » (routage sélectif inversé). Il inverse le sens : seules les IP de Chine continentale passent par la ligne vers la Chine, et tous les autres sites utilisent directement votre accès Internet local. Les vidéos, la musique et les applis chinoises voient une adresse chinoise, tandis que les sites et le streaming locaux ne font aucun détour. Le firmware choisit le sens selon l'endroit où se trouve le routeur, si bien que vous aurez rarement à le changer. Voir [03 · Routage sélectif sur le routeur](03-router-split-routing.md).
- **Un appareil ne passe pas par le VPN, ou les sites bloqués ne s'ouvrent pas alors que tout le reste fonctionne** : cet appareil a son propre DNS privé configuré (« DNS privé » d'Android, DNS sécurisé du navigateur), si bien que le routeur ne voit pas quel site il cherche ; désactivez-le.

## FAQ

**Le routeur compte-t-il pour un appareil ?** Il occupe une place sur le compte (selon la formule : Personnel 2, Famille 4, Entreprise 8 appareils en ligne en même temps), et les appareils derrière lui ne sont pas comptés séparément.

**Peut-il servir à regarder des vidéos chinoises depuis l'étranger ?** Oui, choisissez la région Chine pour la ligne. Le routeur fait entrer tout le réseau local dans le VPN, et l'IPv6 et le DNS des appareils ne peuvent pas sortir à côté, si bien que les messages de « restriction de droits » apparaissent moins souvent que lorsqu'un téléphone se connecte seul. Voir [06](06-unlock-chinese-video-with-router.md).

**Le firmware contient-il une porte dérobée ?** Il est compilé à partir d'OpenWrt, en y ajoutant seulement le composant qui se connecte au VPN et les règles de routage sélectif ; le VPN n'enregistre que la durée de connexion et le trafic total pour la facturation, et n'enregistre pas ce que vous consultez.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-07) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-07) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
