# 08 · Une fois le firmware installé : ce qu'il fait tout seul, et les quelques réglages à connaître

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/router-firmware?utm_source=github&utm_content=router-08

Après avoir flashé le firmware de ce site ou acheté un routeur préinstallé, il vous suffit de connecter votre compte dans la page d'administration. Cet article présente ce que le firmware **fait tout seul** et les quelques réglages que vous pourriez avoir à toucher ; pour la prise en main, voir [01](01-plug-and-play-router.md) ; pour le routage sélectif, voir [03](03-router-split-routing.md) ; pour la liaison et le remplacement d'un routeur, voir [05](05-mac-binding-and-replacing.md).

## Ce qu'il fait tout seul

| Quoi | Comment | Ce que vous avez à faire |
|---|---|---|
| Mise à jour des composants et de la liste de routage sélectif | Vérifie au démarrage et télécharge les mises à jour, qui **s'appliquent au démarrage suivant** ; la liste des sites bloqués servant à joindre les services étrangers depuis la Chine se met aussi à jour automatiquement chaque jour | Rien ; les changements d'adresse des lignes et les sites ajoutés à la liste sont pris en compte automatiquement |
| Code pays du Wi‑Fi | Détecte le pays où il se trouve une fois connecté et règle automatiquement la puissance d'émission et les canaux | Juste après le flash, **branchez d'abord un câble réseau** pour qu'il se connecte une fois ; un signal plus faible avant cela est normal |
| Gestion de l'expiration | À l'expiration du compte, il cesse de passer par le VPN ; le réseau local continue de fonctionner normalement | Il reprend automatiquement après le renouvellement, sans avoir à se reconnecter |
| Liaison du routeur | La première connexion enregistre ce routeur sur le compte | Déliez-le sur le site avant de changer de routeur |

Seule une mise à jour majeure de tout le firmware demande de flasher le fichier sysupgrade. Cela n'arrive que quelques fois par an, et le site vous prévient.

## Ce que vous pourriez avoir à toucher

- **Mode de routage** : Split routing (routage sélectif, par défaut) / Global (tout par la ligne) / Direct (sans la ligne). Si un site ne s'ouvre pas, passez d'abord en Global pour vérifier : s'il s'ouvre en Global, c'est qu'il manque à la liste ; donnez l'adresse au service client pour qu'il l'ajoute. S'il ne s'ouvre pas non plus en Global, le problème vient du site lui-même.
- **Région** : à choisir dans la page d'administration. Choisissez la région Chine pour regarder des contenus chinois depuis l'étranger, et une région hors de Chine pour joindre les services étrangers quand vous êtes en Chine.
- **Blocked sites only (sites bloqués uniquement)** : une case dans « VPN settings » (réglages VPN), partie routage sélectif, cochée par défaut. Elle ne concerne que le sens « joindre les services étrangers depuis la Chine » (vous êtes en Chine et avez choisi une région hors de Chine). Cochée, seuls les sites et services bloqués passent par le VPN (d'après une liste de sites bloqués mise à jour automatiquement chaque jour, plus des services comme Telegram qui se connectent à des adresses fixes) ; les sites chinois et les sites étrangers qui s'ouvrent de toute façon depuis la Chine (sites d'entreprises étrangères, téléchargements Apple et Microsoft, plateformes de jeu, etc.) passent en direct, sans détour. Décochez-la pour revenir à l'ancien comportement : sites chinois en direct, tout le reste par le VPN. Si un site étranger ne s'ouvre pas pendant que vous êtes en Chine, décochez-la (ou passez temporairement en Global) et réessayez ; s'il s'ouvre alors, le site est bloqué mais pas encore dans la liste : envoyez l'adresse au service client. Les firmwares flashés avant octobre 2026 n'affichent pas encore cette case (le nouveau comportement par défaut s'applique déjà via les mises à jour automatiques) ; pour la modifier, contactez le service client, qui peut le faire à distance. Le sens « joindre la Chine depuis l'étranger » n'est pas concerné par ce réglage.
- **Sélection automatique de la ligne la plus rapide** : sous la région, désactivée par défaut, conseillée quand la qualité du réseau est mauvaise.

  | | Désactivée (par défaut) | Activée |
  |---|---|---|
  | Ligne utilisée | Toujours la région choisie | Choisit automatiquement, parmi les lignes disponibles, celle qui a la plus faible latence et peu de pertes de paquets, puis refait le test régulièrement et bascule toute seule si la qualité se dégrade |
  | Pays de sortie | La région choisie | Région Chine choisie : ne choisit que parmi les lignes en Chine, la sortie reste en Chine ; région hors de Chine choisie : choisit parmi toutes les lignes hors de Chine, et **le pays de sortie peut différer de la région choisie** (par exemple, vous avez choisi le Japon mais sortez en réalité par Singapour) |
  | Pour quel usage | Les situations qui exigent un pays fixe : regarder le service de streaming d'un pays précis, banques et comptes sensibles à la région | Un réseau domestique instable ou une région qui saccade souvent, quand seule la vitesse compte et peu importe le pays de sortie |

  Quand vous basculez ce réglage, la page d'administration affiche un message de basculement de la sélection automatique et bloque la page jusqu'à la fin. Le réseau coupe brièvement pendant ce temps, c'est normal. La ligne « Current exit » (sortie actuelle) de la page d'administration indique la ligne réellement utilisée.
- **Mot de passe d'administration et mot de passe Wi‑Fi** : les valeurs d'usine sont des valeurs par défaut publiques ; changez-les dès votre première connexion.

## Téléviseurs, box TV et appareils des parents âgés

- Il suffit de les relier au Wi‑Fi de ce routeur ou par câble, et la version chinoise continentale d'une app se lit immédiatement ; les versions internationales (iQIYI, WeTV) ont un catalogue différent, installez donc la version chinoise continentale.
- Un appareil est connecté mais ne passe pas par le VPN, ou les sites bloqués ne s'ouvrent pas alors que tout le reste fonctionne : le plus probable est qu'il utilise son propre DNS privé (« DNS privé » d'Android, DNS sécurisé du navigateur), si bien que le routeur ne voit pas quel site il cherche ; désactivez-le.
- Vous voulez qu'un appareil reste toujours en direct (un ordinateur professionnel qui doit se connecter au VPN de l'entreprise) : connectez-le au Wi‑Fi du routeur amont ou de la box.

## FAQ

**La formule Personnel permet-elle d'utiliser un routeur ?** Oui. Personnel, Famille et Entreprise prennent toutes en charge un routeur, sans changer de formule.

**Combien de places le routeur occupe-t-il ?** Une seule ; les appareils derrière lui ne sont pas comptés.

**Le firmware contient-il une porte dérobée ?** Il est compilé à partir d'OpenWrt, avec seulement le composant de connexion au VPN et les règles de routage sélectif en plus ; le VPN n'enregistre que la durée de connexion et le volume total de trafic, pour la facturation.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-08) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-08) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
