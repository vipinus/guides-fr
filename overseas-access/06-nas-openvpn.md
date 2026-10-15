# 06 · Faire passer un NAS Synology ou QNAP par la ligne

Le NAS est l'appareil de la maison qui a le plus besoin de la ligne et auquel on pense le moins : le gestionnaire de téléchargement doit atteindre des sources à l'étranger, Docker doit récupérer des images, Cloud Sync doit synchroniser des stockages en ligne étrangers, et Plex doit récupérer des métadonnées. Un NAS ne peut pas faire tourner Hiddify, mais Synology comme QNAP intègrent un client OpenVPN : téléchargez un .ovpn depuis la page OpenVPN de ce site, importez-le, il se connecte, et il se reconnecte automatiquement au démarrage. Cet article montre où se trouve l'import chez Synology et chez QNAP, l'option clé « Utiliser la passerelle par défaut », que faire après un changement de mot de passe, et pourquoi « accéder au NAS depuis l'extérieur » est une autre affaire, qui relève de Privé.

## D'abord, distinguer deux choses

Faire passer le NAS lui-même par la ligne (téléchargements, récupération d'images, synchronisation de stockages en ligne étrangers) : utilisez OpenVPN, c'est l'objet de cet article.

Accéder au NAS depuis l'extérieur (ouvrir les partages en déplacement, regarder les caméras) : utilisez Privé (Tailscale), qui met le NAS et votre téléphone dans le même réseau privé ; voir « Voir ses caméras et son NAS en Chine depuis l'étranger ». Laissez ce rôle à Privé : OpenVPN relie le NAS à notre ligne, Privé vous relie à votre domicile.

## Synology

1. Connectez-vous à ce site et, sur la page OpenVPN, cliquez sur le drapeau d'une région pour télécharger le fichier .ovpn de cette région.
2. Panneau de configuration → Réseau → Interface réseau → Créer → Créer un profil VPN → OpenVPN (via l'importation d'un fichier .ovpn), puis saisissez l'e-mail et le mot de passe de votre compte de ce site.
3. « Utiliser la passerelle par défaut sur le réseau distant » (Use default gateway on remote network) : cochée, tout le trafic sortant du NAS passe par la ligne (téléchargements, Docker et Cloud Sync en profitent) ; décochée, seul le tunnel est établi et le trafic sortant reste local. Dans la très grande majorité des cas, il faut la cocher.
4. Cochez « Reconnecter lorsque la connexion VPN est perdue » (Reconnect when the VPN connection is lost) pour que la connexion se rétablisse toute seule après un redémarrage du NAS ou une instabilité de la ligne. Connectez-vous, puis faites un essai de téléchargement dans un paquet.

## QNAP

1. Téléchargez le .ovpn de la même manière.
2. QVPN Service → VPN Client → Add (ajouter) → OpenVPN, importez le fichier, puis saisissez l'identifiant et le mot de passe.
3. Dans les réglages de la connexion, cochez « Use VPN as the default gateway of the NAS » (utiliser le VPN comme passerelle par défaut du NAS) ainsi que la reconnexion automatique, puis connectez-vous.

## Quel trafic passe par la ligne, et lequel non

- Passe par la ligne : les tâches BT et HTTP de Download Station / Download Station, la récupération d'images Docker, la synchronisation Google Drive / Dropbox / OneDrive de Cloud Sync, la récupération de métadonnées de Plex et Emby, et les mises à jour du Centre de paquets.
- Ne passe pas : le trafic quand vous accédez au NAS depuis le réseau local ; il reste dans le réseau local et n'est pas affecté.
- Vous êtes en Chine et voulez que les sites chinois restent en direct : le NAS n'a pas de script de routage sélectif, et une fois OpenVPN connecté, tout le trafic sortant du NAS passe par la ligne. Si les sources de téléchargement chinoises sont lentes, utilisez des adresses de miroirs chinois dans les tâches, ou ne connectez la ligne que lorsque vous en avez besoin.

## À savoir

- Le fichier de configuration contient votre compte, et le mot de passe enregistré sur le NAS cesse de fonctionner après un changement de mot de passe : téléchargez à nouveau le .ovpn et remplacez-le, ou changez seulement le mot de passe dans le profil VPN.
- Quand le compte expire, le NAS est déconnecté ; après le renouvellement, il se reconnecte automatiquement, sans changer la configuration.
- Le NAS compte pour un appareil et partage le quota d'appareils en ligne en même temps avec vos autres appareils (Personnel 2, Famille 4, Entreprise 8).
- La ligne passe par l'UDP ; un NAS sur un accès Internet domestique ne rencontre presque jamais de restriction UDP.

## FAQ

**Avec « Utiliser la passerelle par défaut » cochée, le NAS reste-t-il accessible sur le réseau local ?** Oui. Le trafic local ne passe pas par la passerelle ; les partages, la lecture Plex et la page d'administration ne sont pas affectés.

**La lecture Plex à distance est plus lente depuis que le NAS passe par la ligne ?** La lecture Plex à distance utilise le trafic sortant du NAS ; une fois la passerelle par défaut cochée, elle fait un détour par la ligne. Pour la lecture à distance, accéder au NAS par Privé est plus direct ; ou ne connectez OpenVPN que lorsque vous devez télécharger.

**Peut-on ne faire passer que Download Station par la ligne ?** Synology et QNAP n'ont pas de routage sélectif par appli. Pour un contrôle fin, faites tourner dans Docker un conteneur de téléchargement avec OpenVPN (par exemple qbittorrent + gluetun) et ne faites passer que lui par la ligne.

**Et un NAS sous un système Linux (TrueNAS, Unraid) ?** Procédez comme sous Linux : le paquet openvpn plus un fichier de configuration placé dans /etc/openvpn/client/ ; voir « Faire passer un serveur Linux et les outils en ligne de commande par la ligne ».

## Pour aller plus loin

- [Page OpenVPN : téléchargement des clients et fichiers de configuration](https://www.leotun.com/fr/openvpn?utm_source=github&utm_content=overseas-access-06)
- [OpenVPN : comment l'utiliser et quand le choisir](https://www.leotun.com/fr/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-06)
- [Voir ses caméras et son NAS en Chine depuis l'étranger](https://www.leotun.com/fr/guides/home-camera?utm_source=github&utm_content=overseas-access-06)
- [Faire passer un serveur Linux et les outils en ligne de commande par la ligne](https://www.leotun.com/fr/guides/linux-server?utm_source=github&utm_content=overseas-access-06)

Version de cet article sur le site : https://www.leotun.com/fr/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-06

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=overseas-access-06) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=overseas-access-06) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
