# 03 · Proxy web : configurer l'extension ZeroOmega en deux étapes

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/web-proxy?utm_source=github&utm_content=client-03

Le proxy web ne fait passer par la ligne que **ce navigateur** ; les autres programmes du système ne sont pas concernés. Aucun client à installer, aucun droit administrateur nécessaire, et pas d'état « connecté » : par conception, il n'y a donc pas de connexion qui puisse tomber. Il convient à un ordinateur professionnel, à une machine déjà connectée au VPN de l'entreprise, ou quand vous voulez qu'un seul navigateur utilise la ligne. Pour savoir quand l'utiliser et quand un VPN est indispensable, voir le [Guide réseau 02](../network/02-choose-your-connection-method.md).

## Deux étapes

1. **Installez l'extension** : installez ZeroOmega (la suite de SwitchyOmega) dans Chrome / Edge / Firefox. [La page Proxy du site](https://www.leotun.com/fr/httpproxy?utm_source=github&utm_content=client-03) donne le lien d'installation pour chaque navigateur.
2. **Importez** : connectez-vous au site et, sur la page Proxy, cliquez sur le drapeau de la région voulue (ou sur « Copier le lien d'import pour toutes les régions » pour importer toutes les régions d'un coup) : le lien de configuration est copié. Ouvrez « Import/Export » dans l'extension, collez-le dans « Restore from online » (restaurer depuis une adresse en ligne) et cliquez sur « Restore » (restaurer). Régions, adresses et méthode de chiffrement sont importées d'un coup, sans rien saisir à la main.

Ensuite, cliquez sur l'icône de l'extension, choisissez une région, puis saisissez l'identifiant et le mot de passe de votre compte du site dans la fenêtre de connexion qu'affiche le navigateur. Pour changer de région, cliquez sur une autre dans le menu de l'icône ; pour revenir à une connexion locale directe, choisissez « Direct ».

## Dans ces cas, utilisez une méthode pour toute la machine

- Applis et lecteurs de vidéo et de musique : la plupart n'utilisent pas le proxy du navigateur, d'où le symptôme « les pages web s'ouvrent, mais les vidéos ne se lisent pas ».
- Applis de téléphone, jeux et logiciels de bureau. Les réglages de proxy de logiciels comme Dropbox n'acceptent que du HTTP / SOCKS5 non chiffré, alors qu'en pratique un proxy doit être chiffré : le proxy web de ce site ne peut donc pas y être saisi. Utilisez plutôt Hiddify pour prendre en charge toute la machine ; voir [10](10-app-proxy.md).
- Regarder Tencent Video ou iQIYI depuis l'étranger : les sites vidéo vérifient aussi l'IPv6 et le DNS, que le proxy web ne couvre pas ; utilisez un VPN pour toute la machine.

## FAQ

| Symptôme | Cause |
|---|---|
| La fenêtre de connexion revient sans cesse | Le compte a expiré ou le mot de passe est erroné |
| Certains sites ne s'ouvrent pas alors que d'autres fonctionnent | Les règles de « auto switch » (bascule automatique) de l'extension les envoient en direct ; essayez une fois le mode proxy global |
| En Chine, seuls les sites HTTPS s'ouvrent | Le HTTP simple est réécrit en chemin et seules les connexions chiffrées passent ; presque tous les sites sont en HTTPS aujourd'hui |
| Lent | Changez de région ; le proxy et le VPN utilisent les mêmes serveurs |

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-03) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-03) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
