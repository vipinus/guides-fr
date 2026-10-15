# 04 · OpenVPN : télécharger le profil .ovpn, l'importer et se connecter ; fonctionne sur routeurs, NAS et Linux

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/openvpn-setup?utm_source=github&utm_content=client-04

OpenVPN est un protocole open source de longue date, et presque tous les systèmes d'exploitation, firmwares de routeur et NAS ont un client pour lui. Les fichiers de profil LeoTun contiennent déjà votre identifiant, votre mot de passe et les éléments de chiffrement : vous pouvez vous connecter dès l'import. Pour un usage quotidien sur téléphone et ordinateur, AnyConnect ou Hiddify demandent moins d'efforts ; l'intérêt d'OpenVPN est ailleurs : **là où seul OpenVPN est accepté**, c'est-à-dire routeurs OpenWrt, NAS Synology / QNAP, serveurs Linux et appareils anciens.

## Trois étapes

1. Depuis le tableau de [la page OpenVPN du site](https://www.leotun.com/fr/openvpn?utm_source=github&utm_content=client-04), installez le client de votre système (toutes les plateformes ont l'OpenVPN Connect officiel ; sous Windows, vous pouvez aussi utiliser OpenVPN GUI, et sous macOS Tunnelblick).
2. Une fois connecté au site, **cliquez sur le drapeau d'une région** pour télécharger le .ovpn de cette région. Un fichier par région.
3. Ouvrez le fichier dans le client et connectez-vous.

| Plateforme | Remarques |
|---|---|
| Windows / macOS / Android / iOS | Le profil contient l'identifiant et le mot de passe ; importez et connectez-vous |
| Linux | Paramètres VPN du système → importer depuis un fichier, puis saisissez l'e-mail et le mot de passe de votre compte sur le site à la première connexion ; en ligne de commande `openvpn --config file` ; pour un lancement au démarrage, placez-le dans `/etc/openvpn/client/` |
| Routeur OpenWrt | Installez luci-app-openvpn, envoyez le .ovpn et activez-le ; inutile si le firmware de ce site est préinstallé |
| NAS Synology | Panneau de configuration → Réseau → Interface réseau → Créer → VPN → OpenVPN (importez le .ovpn) ; pour faire passer le trafic sortant du NAS par la ligne, cochez « Utiliser la passerelle par défaut sur le réseau distant » (Use default gateway on remote network) |
| NAS QNAP | QVPN → VPN Client → Add → OpenVPN, importez |

## Utilisateurs en Chine : accès direct aux sites chinois

Une fois connecté, le trafic vers les sites chinois fait un détour. Le site propose un « outil de routage direct » pour la Chine : double-cliquez pour le lancer, et les IP chinoises passent en direct tandis que tout le reste passe par la ligne. Il fonctionne avec Cisco comme avec OpenVPN. Les utilisateurs à l'étranger ne doivent pas l'utiliser.

## Si la connexion échoue, vérifiez dans cet ordre

| Mot-clé du journal / symptôme | Cause | Que faire |
|---|---|---|
| AUTH_FAILED | Identifiant ou mot de passe erroné, ou compte expiré | Connectez-vous au site et vérifiez la date d'expiration ; si vous avez changé de mot de passe, téléchargez à nouveau le profil |
| L'UDP expire d'abord, puis la connexion se fait en TCP | Le réseau actuel restreint l'UDP, et le client est passé automatiquement en TCP | Utilisable mais plus lent ; si c'est trop lent, changez de réseau ou utilisez plutôt AnyConnect |
| UDP et TCP signalent tous deux TLS handshake failed / key negotiation failed | Le chemin réseau vers le serveur est coupé | Changez de région ou de réseau |
| Erreur à l'import | Client trop ancien (antérieur à OpenVPN 2.5) | Mettez le client à jour |
| Coupure soudaine en cours de connexion | Le compte a expiré et le serveur vous a déconnecté | Renouvelez et reconnectez-vous ; inutile de remplacer le profil |

## UDP ou TCP

Les deux sont disponibles et vous n'avez pas à choisir. L'UDP vient en premier dans le profil, donc le client essaie d'abord l'UDP ; si l'UDP est restreint ou ne se connecte pas, il bascule automatiquement en TCP au bout de quelques secondes. L'UDP a une latence plus faible et va plus vite ; le TCP n'est qu'une solution de repli, nettement plus lente entre pays. Sur les réseaux qui restreignent l'UDP en permanence (certains réseaux de campus et d'entreprise), nous conseillons d'utiliser directement AnyConnect.

> Les profils téléchargés avant le 15 septembre 2026 ne contiennent que l'UDP ; téléchargez-les à nouveau si vous voulez la bascule automatique.

## Sécurité

Le fichier de profil contient votre identifiant et votre mot de passe, ce qui en fait l'équivalent du compte lui-même : ne le transmettez pas. S'il fuite, changez votre mot de passe sur le site et l'ancien fichier cesse aussitôt de fonctionner. La négociation de connexion est elle-même chiffrée : sans la clé contenue dans le profil, impossible même de l'entamer, et le serveur reste invisible aux scanners.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-04) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-04) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
