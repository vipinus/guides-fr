# 02 · Quelle méthode de connexion pour quelle situation

Un compte LeoTun offre six méthodes de connexion : Privé (Tailscale), Cisco (AnyConnect), OpenVPN, Proxy Web, Hiddify et Routeur. Chacune a les situations où elle excelle, et cet article répond situation par situation : d'abord selon l'appareil utilisé, puis selon le réseau où vous êtes, et enfin selon ce que vous voulez faire. Chaque situation reçoit une recommandation, la raison et une solution de rechange. Retenez une chose : six méthodes sur un même compte, il y en a toujours une qui convient à votre réseau.

## Selon l'appareil : avec quoi vous allez en ligne

- Un seul téléphone, voyages d'affaires et séjours : Cisco ou Hiddify. Cisco se connecte dès que vous saisissez l'adresse dans l'appli officielle et c'est le plus stable ; Hiddify s'importe en scannant un QR code et va plus vite quand les pertes de paquets sont élevées. Rechange : Privé.
- Votre propre ordinateur (Windows, Mac) : Hiddify ou Privé. Hiddify est rapide et intègre un interrupteur de routage sélectif ; Privé reste en ligne après une seule connexion. Rechange : Cisco.
- Un ordinateur fourni par l'entreprise, sans droits administrateur : Proxy Web. Vous n'installez qu'une extension de navigateur, aucun droit administrateur n'est nécessaire, et les réglages réseau de l'entreprise ne sont pas touchés.
- iPhone, appareils anciens : Cisco. Il se connecte avec le VPN intégré du système ou le client officiel, sans importer de configuration, et c'est la meilleure compatibilité.
- NAS (Synology, QNAP), serveurs Linux : OpenVPN. Importez un fichier .ovpn et il se connecte automatiquement au démarrage ; la plupart de ces appareils ont un client intégré.
- Téléviseurs, box TV, consoles de jeu, téléphone d'un proche âgé : Routeur. Tout ce qui est connecté au Wi‑Fi passe par la ligne, sans rien installer sur l'appareil. Les trois formules permettent de l'utiliser.
- Beaucoup d'appareils pour toute une famille ou un bureau : Routeur, configuré une fois et valable pour tous ; si vous voulez aussi joindre le NAS de la maison depuis l'extérieur, ajoutez Privé.

## Selon le réseau : sur quel réseau vous êtes

- Réseaux de résidence universitaire ou de campus, réseaux d'entreprise qui restreignent l'UDP : Cisco. Il passe par TLS, comme l'ouverture d'un site HTTPS, et c'est le plus stable sur les réseaux restreints ; Hiddify, Privé et OpenVPN passent tous par l'UDP et seront lents ou couperont.
- Connexion Internet qui coupe souvent, signal Wi‑Fi faible : Proxy Web. Il fonctionne requête par requête sans connexion permanente : par conception, il n'y a pas de connexion qui puisse tomber.
- Haut débit de vieil immeuble, données mobiles, pertes de paquets élevées : Hiddify. Son protocole est conçu pour résister aux pertes de paquets et donne le meilleur débit sur ces réseaux.
- L'ordinateur est déjà connecté au VPN de l'entreprise : Proxy Web. Deux VPN pour toute la machine qui tournent ensemble se disputent les réglages réseau ; le proxy web ne s'occupe que du navigateur, ils ne se gênent donc pas.
- China Mobile, Great Wall Broadband et autres fournisseurs, ou liaisons internationales toujours instables : n'importe quelle méthode, avec un point d'entrée de la région Chine. C'est généralement le choix le plus stable sur ces réseaux.

## Selon l'usage : ce que vous voulez faire

- Vous êtes à l'étranger et voulez regarder des vidéos chinoises : n'importe quelle méthode pour toute la machine (Cisco, Hiddify, Privé, OpenVPN, Routeur) avec la région Chine ; pour la télévision de la maison, utilisez Routeur. N'utilisez pas le proxy web pour la vidéo : il n'atteint pas le canal réseau propre de l'appareil, et le site vidéo peut encore vous voir à l'étranger.
- Jeux, appels vocaux et vidéo : Hiddify, Privé ou Routeur, avec la région à la plus faible latence. Le proxy web ne s'occupe que du navigateur ; les jeux et les applis d'appel n'y passent pas.
- Travail de bureau et recherches, navigateur uniquement : le proxy web est le plus simple ; si vous devez vous connecter aux systèmes internes de l'entreprise, vérifiez d'abord si le VPN de l'entreprise peut tourner en même temps que le nôtre, et sinon, utilisez le proxy web.
- Serveurs, scripts, ligne de commande : OpenVPN ; sur un poste Linux, vous pouvez aussi utiliser Privé ou Hiddify.
- Joindre depuis l'extérieur le NAS ou les caméras de la maison : Privé. Les appareils d'un même compte peuvent se joindre entre eux, sans ouvrir de ports sur le routeur.

## Les six méthodes en un coup d'œil : idéal pour / peu adapté à

- Privé (Tailscale) — idéal pour : plusieurs appareils, se connecter une fois et ne plus y penser, joindre les appareils de la maison depuis l'extérieur. Peu adapté à : les réseaux qui restreignent l'UDP (il ne peut alors passer que par des relais, ce qui est lent), la cohabitation avec un autre VPN.
- Cisco AnyConnect — idéal pour : réseaux restreints, ordinateurs d'entreprise, iPhone, appareils anciens ; la meilleure compatibilité. Peu adapté à : les personnes en Chine qui ne veulent pas que tout le trafic passe par la ligne (il faut lancer à part un script de routage sélectif).
- OpenVPN — idéal pour : NAS, serveurs Linux, routeurs OpenWrt ; importez un fichier et il se connecte automatiquement au démarrage. Peu adapté à : l'usage quotidien sur téléphone et ordinateur, où il est moins pratique que Cisco et Hiddify ; les réseaux qui restreignent l'UDP.
- Proxy Web — idéal pour : pas de droits administrateur, déjà connecté au VPN de l'entreprise, connexion qui coupe souvent. Peu adapté à : applis vidéo, jeux, appels ; il ne s'occupe que du navigateur.
- Hiddify — idéal pour : ceux qui veulent de la vitesse, les réseaux à fortes pertes de paquets ; import par QR code, la même appli sur cinq plateformes, routage sélectif intégré. Peu adapté à : les réseaux qui restreignent l'UDP.
- Routeur — idéal pour : toute une famille, un bureau, les appareils incapables d'installer un client ; le firmware intègre le routage sélectif et se met à jour automatiquement. Peu adapté à : ceux qui n'ont qu'un appareil et sont souvent dehors (il faut quand même installer un client pour sortir).

## Choisir la région selon votre connexion Internet

Une même méthode peut voir son débit varier du simple au quintuple d'une région à l'autre ; la raison tient à la ligne de sortie de votre opérateur vers cette région, pas au serveur. China Unicom dans le nord : essayez d'abord le Japon et la Corée. China Telecom dans le sud : essayez d'abord l'Asie du Sud-Est (Singapour, Malaisie, Thaïlande, Philippines, Indonésie) ou l'Australie. Autres fournisseurs (China Mobile, Great Wall Broadband, etc.) : essayez d'abord le point d'entrée de la région Chine.

Les voyants rouge, jaune et vert de la liste des régions indiquent la charge de chaque région en temps réel ; parmi plusieurs entrées Japon, prenez celle au vert. De 20 h à 23 h, c'est l'heure de pointe dans tout le pays ; pendant cette période, choisissez une région au vert ou changez de méthode de connexion. Si c'est toujours lent, la cause habituelle est l'accès Internet local (haut débit partagé de résidence, ou opérateur et région mal assortis).

## Routage sélectif : direct en Chine, par la ligne pour l'étranger

Seuls les utilisateurs en Chine continentale ont besoin du routage sélectif ; hors de Chine, on utilise le mode global, et activer le routage sélectif ferait au contraire faire un détour à certains sites. Dans Hiddify, passez sur « Auto split routing » (routage sélectif automatique) dans le client ; pour le proxy web, passez sur « Split routing » (routage sélectif) dans l'extension ; le routeur fait le routage sélectif pour tous les appareils du réseau, et son firmware l'active par défaut ; avec Cisco et OpenVPN, tout le trafic passe par la ligne une fois connecté, et le script de routage sélectif de la rubrique « Cisco » est disponible ; Privé fait passer toute la machine par la ligne.

Si un site ne s'ouvre pas en routage sélectif, passez d'abord temporairement en « Global » pour vérifier : s'il s'ouvre en global, c'est qu'il n'est pas dans la liste ; s'il ne s'ouvre pas non plus en global, le problème vient du site lui-même.

## Comment basculer quand ça ne marche pas

1. Changez d'abord de région. Si une autre région se connecte, ce serveur est simplement injoignable pour le moment.
2. Puis changez de réseau. Si le haut débit ne marche pas, passez aux données mobiles, et inversement ; les perturbations ne touchent pas les différents opérateurs en même temps.
3. Puis changez de méthode. Si celles qui passent par l'UDP (Hiddify, Privé, OpenVPN) ne marchent pas, passez à Cisco, qui passe par TLS ; si les méthodes pour toute la machine coupent sans cesse, passez au proxy web. Le blocage des différents protocoles est indépendant.
4. Si ça ne marche toujours pas, consultez le guide de dépannage, ou demandez dans le groupe d'assistance en indiquant la méthode de connexion, la région, le texte exact de l'erreur et l'heure.

## FAQ

**Laquelle des six méthodes est la plus rapide ?** Sur les réseaux à fortes pertes de paquets, Hiddify ; sur les réseaux propres, la différence est faible, et le goulot d'étranglement est la région et l'heure, pas la méthode.

**Laquelle pour les jeux et les appels vocaux ?** Hiddify, Privé ou Routeur, avec la région à la plus faible latence. Le proxy web ne s'occupe que du navigateur ; les jeux et les applis d'appel n'y passent pas.

**Peut-on utiliser les six méthodes en même temps ?** Sur des appareils différents, oui ; toutes les méthodes d'un même compte partagent le quota d'appareils en ligne simultanément (Personnel 2 appareils, Famille 4 appareils, Entreprise 8 appareils). Ne faites pas tourner deux méthodes pour toute la machine en même temps sur le même appareil (par exemple Privé et Cisco) : elles se disputeraient les réglages réseau.

**Faut-il choisir entre routeur et client ?** Non. Utilisez le routeur à la maison et activez le client sur votre téléphone quand vous sortez ; chacun compte pour un appareil.

**Laquelle pour Linux ?** Privé, OpenVPN et Hiddify ont tous un client Linux ; Cisco sous Linux utilise OpenConnect, open source ; OpenVPN sous Linux demande l'identifiant et le mot de passe à la première connexion. Pour les serveurs et les NAS, OpenVPN est le plus simple.

## Pour aller plus loin

- [Ce qui nous distingue des autres VPN](https://www.leotun.com/fr/guides/why-us?utm_source=github&utm_content=network-02)
- [Ce qu'est la méthode Privé (Tailscale)](https://www.leotun.com/fr/guides/tailscale-mesh?utm_source=github&utm_content=network-02)
- [Comment utiliser OpenVPN et quand le choisir](https://www.leotun.com/fr/guides/openvpn-setup?utm_source=github&utm_content=network-02)
- [Ce qu'est le proxy web et quand l'utiliser](https://www.leotun.com/fr/guides/web-proxy?utm_source=github&utm_content=network-02)

Version de cet article sur le site : https://www.leotun.com/fr/guides/choose-connection?utm_source=github&utm_content=network-02

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=network-02) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=network-02) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
