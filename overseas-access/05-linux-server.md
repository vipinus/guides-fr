# 05 · Faire passer un serveur Linux et les outils en ligne de commande par la ligne

Sous Linux, il existe deux façons de passer par la ligne ; choisissez selon le besoin. Pour faire passer toute la machine (récupérer des images Docker, faire tourner des services qui ont besoin d'un réseau à l'étranger, fonctionnement sans surveillance), utilisez OpenVPN : un fichier de configuration placé dans /etc/openvpn/client/ et lancé au démarrage. Pour ne faire passer que quelques commandes (git, pip, npm, curl), utilisez le proxy web : mettez l'adresse du proxy dans la variable d'environnement http_proxy, et le reste du trafic n'est pas touché. Sur un Linux de bureau, vous pouvez aussi importer la configuration dans NetworkManager. Cet article présente les trois, avec la façon d'écrire le fichier de mot de passe et les commandes de vérification.

## Voie n° 1 : toute la machine par la ligne (OpenVPN)

1. Installez le client : Debian / Ubuntu sudo apt install openvpn, Fedora sudo dnf install openvpn, Arch sudo pacman -S openvpn.
2. Connectez-vous à ce site et, sur la page OpenVPN, cliquez sur le drapeau d'une région pour télécharger le .ovpn. La configuration fournie pour Linux ne contient pas l'identifiant et le mot de passe (NetworkManager refuse les fichiers qui les embarquent) : créez donc un fichier de mot de passe à part, de deux lignes, la première avec votre e-mail sur ce site, la seconde avec votre mot de passe, en chmod 600.
3. Copiez le .ovpn vers /etc/openvpn/client/<region>.conf, et ajoutez le chemin du fichier de mot de passe après auth-user-pass dans le fichier.
4. sudo systemctl enable --now openvpn-client@<region>. Vérifiez l'état avec systemctl status openvpn-client@<region>, et contrôlez que curl -s https://ipinfo.io/country affiche bien la région choisie.
5. Pour changer de région, téléchargez une autre configuration et activez une autre unité ; n'en faites tourner qu'une à la fois.

## Voie n° 2 : seulement les outils en ligne de commande (proxy web)

L'adresse du proxy indiquée sur la page Proxy Web de ce site, avec votre identifiant et votre mot de passe, se met directement dans les variables d'environnement : export https_proxy=https://username:password@proxy-address export http_proxy=$https_proxy. Les caractères spéciaux du mot de passe doivent être encodés pour URL. Ensuite, curl, wget, git, pip et npm passent tous par la ligne dans ce terminal, et les autres programmes ne sont pas concernés.

Le démon Docker ne lit pas les variables d'environnement du shell ; écrivez-les dans Environment= de /etc/systemd/system/docker.service.d/proxy.conf puis redémarrez docker. Pour apt, écrivez Acquire::https::Proxy dans /etc/apt/apt.conf.d/proxy.conf.

Avec cette voie, il n'y a par principe aucune connexion qui puisse tomber ; elle ne demande pas les droits root et ne modifie pas les routes. Elle convient aux serveurs d'entreprise et aux cas où vous voulez seulement accélérer des téléchargements ; elle ne s'applique qu'aux programmes qui respectent les variables de proxy, et le reste du trafic n'est pas touché.

## Voie n° 3 : NetworkManager sur un Linux de bureau

1. Installez network-manager-openvpn-gnome (sur la page OpenVPN de ce site, un clic peut ouvrir la logithèque).
2. Paramètres → Réseau → VPN → « + » → Importer depuis un fichier, choisissez le .ovpn, saisissez votre e-mail et votre mot de passe pour ce site, puis enregistrez.
3. Activez et désactivez le VPN depuis la barre supérieure ou la zone de notification. Pour une connexion automatique au démarrage, cochez « Se connecter automatiquement au VPN » dans les paramètres de la connexion filaire ou sans fil.

## Vérification et dépannage

- Contrôler la sortie : le pays indiqué par curl -s https://ipinfo.io doit être la région choisie.
- Contrôler le DNS : dans resolvectl status, le DNS de l'interface VPN doit être celui fourni par la ligne ; en cas de fuite, ajoutez dhcp-option DNS à la configuration ou utilisez le script update-systemd-resolved.
- AUTH_FAILED : le fichier de mot de passe est faux ou le compte a expiré ; si vous avez changé de mot de passe, mettez à jour le fichier.
- Délai dépassé lors de la négociation TLS : l'UDP vers le serveur ne passe pas ; changez de région ou de réseau. Sur un serveur cloud, le groupe de sécurité doit autoriser l'UDP sortant.
- Le serveur est en Chine et les sources chinoises doivent rester en accès direct : une fois OpenVPN connecté, tout le trafic sortant passe par la ligne. Basculez les sources apt / pip / npm sur des miroirs chinois, ou utilisez plutôt la voie n° 2 pour ne faire passer que certaines commandes.

## À savoir

- Une machine Linux compte pour un appareil et partage le quota d'appareils simultanés avec vos autres appareils (Personnel 2 appareils, Famille 4, Entreprise 8) ; le proxy web de la voie n° 2 est compté par connexion et entre aussi dans ce quota.
- Le fichier de configuration et le fichier de mot de passe valent votre compte : ne les envoyez pas dans un dépôt git et ne les intégrez pas à une image.
- Dès que vous changez de mot de passe, l'ancienne configuration cesse de fonctionner : c'est le mécanisme de révocation prévu. Il suffit de mettre à jour le fichier de mot de passe.
- Si vous utilisez la ligne sur un serveur cloud, respectez les conditions d'utilisation de l'hébergeur ; la ligne n'enregistre que la durée de connexion et le volume total de trafic.

## FAQ

**Pourquoi la configuration Linux ne contient-elle pas l'identifiant et le mot de passe ?** NetworkManager refuse à l'import un fichier qui embarque les identifiants et signale un échec ; la version fournie pour Linux vous les fait donc saisir vous-même. Avec la méthode systemd, écrivez-les dans le fichier de mot de passe.

**Peut-on ne faire passer que Docker par la ligne ?** Oui : définissez les variables de proxy pour le seul démon Docker (voie n° 2) ; ou faites tourner un conteneur avec OpenVPN intégré (gluetun) pour que certains conteneurs précis passent par la ligne.

**Et la méthode Privé (Tailscale) sous Linux ?** Le script officiel l'installe en une ligne, et tailscale up --login-server=<serveur de contrôle de ce site> permet de se connecter. Elle convient si vous devez joindre cette machine depuis l'extérieur, ou si vous voulez la configurer une fois et la laisser toujours en ligne ; pour simplement accélérer des téléchargements, OpenVPN ou le proxy sont plus simples.

**Est-ce pareil pour OpenWrt sur un routeur ?** Sous OpenWrt, installez luci-app-openvpn et envoyez le .ovpn : tout le réseau local passe alors par la ligne. Un routeur équipé du firmware de ce site n'en a pas besoin : connectez simplement votre compte.

## Pour aller plus loin

- [Page OpenVPN : téléchargement des clients et des fichiers de configuration](https://www.leotun.com/fr/openvpn?utm_source=github&utm_content=overseas-access-05)
- [Utiliser OpenVPN et savoir quand le choisir](https://www.leotun.com/fr/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-05)
- [Faire passer un NAS Synology ou QNAP par la ligne](https://www.leotun.com/fr/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-05)
- [Le proxy web : ce que c'est et quand l'utiliser](https://www.leotun.com/fr/guides/web-proxy?utm_source=github&utm_content=overseas-access-05)

Version de cet article sur le site : https://www.leotun.com/fr/guides/linux-server?utm_source=github&utm_content=overseas-access-05

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=overseas-access-05) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=overseas-access-05) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
