# 10 · Que faire quand Dropbox ou un autre logiciel demande un proxy HTTP / SOCKS

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/app-proxy?utm_source=github&utm_content=client-10

**D'abord, le constat : un proxy doit être chiffré.** Les proxys non chiffrés (HTTP simple, SOCKS4, SOCKS5) sont repérés et perturbés sur les réseaux en Chine ; au bout de peu de temps, la connexion ralentit ou tombe, et l'identifiant comme le mot de passe circulent en clair. Seules les connexions chiffrées restent utilisables sur la durée : le proxy web de ce site utilise donc exclusivement des connexions chiffrées. **Pour un logiciel qui n'accepte que HTTP / SOCKS5, laissez Hiddify prendre en charge toute la machine** (voir plus bas).

Les logiciels autonomes comme Dropbox, Telegram Desktop, Steam, les clients de stockage en ligne et les outils de développement ne lisent pas les réglages du navigateur, et leurs propres réglages de proxy n'acceptent que du HTTP / SOCKS5 non chiffré. Les deux ne correspondent pas : saisir un proxy ne suffit donc pas à se connecter. La solution est de **ne pas saisir de proxy** : faites passer tout l'ordinateur par la ligne avec Hiddify, et réglez le proxy du logiciel sur « aucun proxy ».

## Pourquoi ça ne se connecte toujours pas après avoir saisi un proxy

| Cause | Explication |
|---|---|
| Type incompatible | Le logiciel ne propose que HTTP, SOCKS4 et SOCKS5, tous non chiffrés ; le proxy de ce site est forcément chiffré et ne peut pas y être saisi |
| Un proxy non chiffré trouvé en ligne | Il fonctionne un moment, puis se fait perturber et ne marche plus que par intermittence |
| Ne couvre qu'une partie du trafic | Dans beaucoup de logiciels, seules la connexion au compte et la synchronisation passent par le proxy, tandis que les mises à jour, les appels et la synchronisation sur le réseau local restent en direct ; un proxy HTTP ne transmet pas du tout le trafic UDP des jeux et des appels |
| À maintenir séparément dans chaque programme | Changer de région ou de mot de passe oblige à tout modifier un par un, et celui que vous oubliez cesse de fonctionner |

## Méthode recommandée : laisser Hiddify prendre en charge toute la machine

1. Installez Hiddify en suivant [09 · Installer Hiddify sur toutes les plateformes](09-hiddify-install-all-platforms.md), puis importez un profil en suivant [02](02-singbox-subscription-links.md).
2. Connectez-vous en mode « VPN » (par défaut). Sous Windows, la première connexion demande les droits d'administrateur.
3. Remettez le proxy du logiciel sur « aucun proxy » : dans Dropbox, choisissez « Pas de proxy » ou « Détection automatique » sous « Préférences → Réseau → Proxys » ; dans Telegram Desktop, choisissez « Désactiver le proxy » sous « Paramètres → Avancé → Type de connexion ». Dans tout autre logiciel qui a une option de proxy, désactivez-la. (Si votre logiciel est en anglais : No proxy, Auto-detect, Disable proxy.)
4. Vérifiez : l'icône Dropbox de la zone de notification indique que tout est à jour et la synchronisation démarre ; ouvrez dans le navigateur une page qui affiche votre IP : la sortie est dans la région choisie.

Avec le « routage automatique » activé, les services étrangers comme Dropbox passent par la ligne, tandis que WeChat, la banque en ligne et les sites chinois restent en direct comme d'habitude.

## Logiciels courants

| Logiciel | Réglage |
|---|---|
| Dropbox | Proxy sur « Pas de proxy » ou « Détection automatique » ; si vous le laissez en « Manuel » avec une autre adresse, il reste hors ligne dès que Hiddify est coupé |
| Telegram Desktop | Type de connexion « Désactiver le proxy » ; le MTProto / SOCKS5 intégré, ajouté par-dessus le tunnel, ne fait que ralentir |
| OneDrive, Google Drive, iCloud pour ordinateur | Suivent le réseau du système ; rien à régler |
| Steam, Epic, Battle.net | Pas besoin de proxy ; si les téléchargements sont lents, passez à une région plus proche |
| Zoom, Teams, Slack, Discord | La voix et la vidéo passent en UDP, que seule une méthode couvrant toute la machine transporte |
| VS Code, JetBrains, Cursor | Suivent le réseau du système ; effacez tout proxy réglé à part dans l'outil |

## Quand vous ne pouvez pas installer de client (ordinateur professionnel)

- Utilisez la version web de Dropbox et des stockages en ligne : ouvrez dropbox.com dans un navigateur avec le [proxy web](03-web-proxy-extension.md) ; vous pouvez envoyer et télécharger des fichiers, mais sans synchronisation automatique.
- Les outils en ligne de commande (git, pip, npm, curl) acceptent un proxy chiffré : mettez l'adresse du proxy web dans `https_proxy` ; voir [Accéder aux services étrangers depuis la Chine 05 · Linux et la ligne de commande](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/05-linux-server.md) (en chinois).
- Les autres logiciels de bureau qui n'acceptent que HTTP / SOCKS5 sont à utiliser plutôt sur votre ordinateur ou téléphone personnel ; n'installez pas de VPN couvrant toute la machine sur un ordinateur professionnel pour cela : il déclencherait les alertes de sécurité de l'entreprise.

## FAQ

**Pouvez-vous me donner une adresse de proxy SOCKS5 ou HTTP ?** Le proxy de ce site utilise exclusivement des connexions chiffrées ; un proxy non chiffré se met vite à ne marcher que par intermittence. Laisser Hiddify prendre en charge toute la machine est plus stable et couvre tous les logiciels d'un coup.

**Avec Hiddify allumé, faut-il encore saisir un proxy dans le logiciel ?** Non. En saisir un fait faire au trafic un double détour : au mieux c'est plus lent, au pire ça ne se connecte pas.

**Et Dropbox sur téléphone ?** Les apps mobiles n'ont pas de réglage de proxy. Installez Hiddify ou utilisez Cisco (AnyConnect) ; une fois connecté, toutes les apps passent par la ligne.

**Peut-on se passer de Hiddify ?** Oui. Cisco, Privé et OpenVPN prennent aussi en charge toute la machine, et le logiciel se règle de même sur « aucun proxy ». L'avantage de Hiddify : le routage intégré et un meilleur débit sur les réseaux à fortes pertes de paquets.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-10) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-10) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre permanente
