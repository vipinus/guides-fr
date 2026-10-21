# 08 · Configurer tous vos appareils une fois, et changer de téléphone sans tout recommencer

Quand on a beaucoup d'appareils, le plus pénible est de les configurer un par un, de tout refaire après un changement de téléphone, et de toucher « Connecter » sur chacun dès qu'on sort. La méthode Privé supprime tout cela : chaque appareil se connecte une fois avec votre compte de ce site puis reste en ligne, sans rien à refaire après un redémarrage ou un changement de Wi‑Fi ; chaque appareil choisit sa propre région de sortie, si bien que le portable peut sortir par le Japon et le téléphone par la région Chine sans se gêner ; les appareils d'un même compte peuvent se joindre entre eux, si bien qu'un portable en déplacement ouvre directement les partages du NAS de la maison. Un nouveau téléphone n'a qu'à se connecter. Cet article explique comment y mettre tous les appareils du foyer, comment le quota est compté, et comment gérer l'expiration et le changement d'appareil.

## Ce que vous ne faites qu'une fois par appareil

1. Installez le client Tailscale (Android, Windows, macOS et Linux depuis la zone de téléchargement de la page Privé de ce site ; iPhone / iPad depuis l'App Store, ce qui exige un identifiant Apple d'une région autre que la Chine).
2. Si vous vous êtes déjà connecté à un compte Tailscale officiel, déconnectez-vous d'abord, puis faites pointer la connexion vers le serveur de contrôle de ce site (téléphone : « ⋯ » sur l'écran de connexion → Use custom server ; ordinateur : copiez la commande depuis la page ; macOS : Account Settings → Accounts → la flèche à côté de « Add Account… » → Add Account Using Alternate Server).
3. Confirmez dans le navigateur avec votre compte de ce site. Dès lors, l'appareil fait partie du réseau privé et ne demande plus aucune attention.
4. Choisissez une sortie : chaque appareil choisit dans son propre menu, indépendamment des autres. Pour ne pas utiliser de sortie, choisissez None (aucune) : seul l'accès entre appareils est conservé.

## Comment sont comptés les appareils simultanés

Un compte peut être installé sur autant d'appareils que vous voulez ; la seule limite est le nombre d'appareils en ligne en même temps : Personnel 2, Famille 4, Entreprise 8, avec un quota commun à Cisco, Hiddify et aux autres méthodes. Si vous dépassez la limite de votre formule, vous pouvez passer temporairement à une formule supérieure (le temps restant est converti à valeur égale selon le prix) et revenir en arrière ensuite.

Un routeur compte pour un appareil, et les appareils derrière lui ne sont pas comptés. Un routeur ou un NAS à la maison, plus le téléphone et le portable que vous emportez, suffit généralement.

## Les appareils peuvent se joindre entre eux

- Chaque appareil d'un même compte a une adresse sur le réseau privé et peut aussi être joint par son nom, sans adresse IP publique ni redirection de ports.
- Ouvrir un dossier partagé du NAS de la maison depuis un portable en déplacement, regarder l'enregistreur vidéo de la maison depuis un téléphone, ou prendre la main à distance sur un ordinateur de la maison : tout cela se connecte directement par les adresses du réseau privé.
- Un routeur domestique sous le firmware de ce site peut partager tout le réseau local dans le réseau privé, si bien que les appareils incapables de faire tourner un client, comme les imprimantes et les téléviseurs, sont aussi joignables de l'extérieur.
- Les appareils des autres clients n'apparaissent pas du tout dans votre réseau privé ; ce n'est pas seulement que vous ne les voyez pas.

## Expiration, changement d'appareil, désinstallation

- Expiration du compte : tous les appareils passent hors ligne en quelques minutes ; après le renouvellement, reconnectez-vous une fois sur chacun, et les réglages de sortie sont conservés.
- Changement de téléphone : connectez le nouveau téléphone en suivant les étapes ci-dessus ; s'il indique que la limite est atteinte, déconnectez-vous sur l'ancien, ou passez temporairement à une formule supérieure et revenez ensuite.
- Si vous ne voulez plus qu'un appareil reste dans le réseau privé : déconnectez-vous dans le client ; pour forcer un appareil hors ligne, contactez l'assistance.
- Ne faites pas tourner un autre VPN en même temps sur le même appareil (client Cisco de l'entreprise, autre logiciel de réseau maillé) : ils se disputeraient le DNS et les routes.

## FAQ

**Chaque appareil peut-il choisir une région de sortie différente ?** Oui, chaque appareil choisit sa propre sortie. Le portable peut sortir par le Japon pour la vidéo pendant que le téléphone utilise la région Chine pour la banque en ligne, sans se gêner.

**Laisser le réseau privé allumé en permanence vide-t-il la batterie ?** Sans sortie choisie, il n'y a presque aucun trafic ; il ne sert que pour communiquer avec les appareils du réseau privé. La consommation est comparable à celle du VPN du système.

**Comment l'installer sur un NAS à la maison ?** Synology et QNAP proposent un paquet Tailscale, et les systèmes Linux utilisent le script d'installation officiel ; à la connexion, faites pointer de la même manière vers le serveur de contrôle de ce site. Un routeur sous le firmware de ce site n'a pas besoin de l'installer : connectez votre compte et il fait partie du réseau privé.

**Pourquoi ne pas installer Cisco sur tous les appareils ?** C'est possible, mais avec Cisco il faut toucher « Connecter » à chaque fois, se reconnecter après une coupure, et changer d'adresse pour changer de sortie ; avec beaucoup d'appareils, la méthode Privé demande bien moins d'efforts. Exception : un appareil sur un réseau de campus qui restreint l'UDP ; utilisez Cisco sur celui-là.

## Pour aller plus loin

- [Page Privé : téléchargement et étapes de connexion](https://www.leotun.com/fr/mesh?utm_source=github&utm_content=client-08)
- [Ce qu'est la méthode Privé (Tailscale)](https://www.leotun.com/fr/guides/tailscale-mesh?utm_source=github&utm_content=client-08)
- [Voir depuis l'étranger vos caméras et votre NAS en Chine](https://www.leotun.com/fr/guides/home-camera?utm_source=github&utm_content=client-08)
- [Ce que peut faire le firmware du routeur](https://www.leotun.com/fr/guides/router-firmware?utm_source=github&utm_content=client-08)

Version de cet article sur le site : https://www.leotun.com/fr/guides/multi-device?utm_source=github&utm_content=client-08

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-08) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-08) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre permanente
