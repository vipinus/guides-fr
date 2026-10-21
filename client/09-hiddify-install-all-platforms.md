# 09 · Installer Hiddify sur toutes les plateformes : Windows, macOS, Linux, Android, iOS

Le client utilisé par la méthode Hiddify de ce site est l'application open source Hiddify, qui intègre le moteur sing-box : une fois installée, il n'y a rien d'autre à configurer. Les cinq plateformes utilisent la même application, mais les obstacles au premier lancement diffèrent : sous Windows, elle peut être bloquée ou supprimée par l'antivirus ; sur Mac, le système peut affirmer qu'elle « est endommagée » et il faut en plus autoriser une extension réseau ; sous Linux, une commande d'autorisation est nécessaire avant que le mode VPN fonctionne ; sur iPhone, elle est introuvable dans l'App Store chinois. Cet article indique, plateforme par plateforme, où la télécharger, comment l'installer et quoi faire au premier lancement, puis termine par la marche à suivre la plus courte pour importer un abonnement et se connecter.

## Où la télécharger

| Plateforme | Fichier d'installation | Où le trouver |
|---|---|---|
| Windows | Programme d'installation (.exe), x64 uniquement | Zone de téléchargement de la page Hiddify |
| macOS | .dmg, un seul paquet pour puces Apple et Intel | Zone de téléchargement de la page Hiddify |
| Linux | .deb (famille Debian / Ubuntu), x64 uniquement | Zone de téléchargement de la page Hiddify |
| Android | .apk, en deux versions : ARM64 et x86-64 | Zone de téléchargement de la page Hiddify, ou Google Play |
| iPhone / iPad | Hiddify Proxy & VPN sur l'App Store | App Store ; nécessite un identifiant Apple d'une région autre que la Chine |

La zone de téléchargement de la page Hiddify recommande automatiquement le paquet adapté à votre système, et les paquets des autres systèmes sont listés en dessous. Chaque ligne comporte aussi une icône « Site officiel » qui mène à la page de publication officielle de Hiddify, pour comparer les versions. Les trois systèmes de bureau (Windows, macOS, Linux) ont également des tutoriels vidéo.

Les programmes d'installation pour ordinateur sont des copies conformes des paquets officiels de Hiddify, ni modifiés ni réempaquetés. Avant de les autoriser, vous pouvez vérifier vous-même : envoyez le fichier sur VirusTotal et regardez le résultat ; la méthode est détaillée dans [Dépannage 06](../troubleshooting/06-antivirus-false-positive.md).

## Windows

1. Téléchargez le programme d'installation depuis la zone de téléchargement de la page Hiddify et double-cliquez pour l'installer. (Dans nos tests actuels, la Sécurité Windows ne le signale pas ; si votre antivirus le fait, consultez la FAQ à la fin de [Dépannage 06](../troubleshooting/06-antivirus-false-positive.md).)

## macOS

1. Téléchargez le .dmg depuis la zone de téléchargement de la page Hiddify, ouvrez-le et faites glisser Hiddify dans « Applications ».
2. Dans « Finder » → « Applications », cliquez sur l'icône Hiddify en maintenant la touche Contrôle, choisissez « Ouvrir », puis cliquez à nouveau sur « Ouvrir » dans la fenêtre qui s'affiche.
3. Si elle refuse toujours de s'ouvrir : « Réglages Système » → « Confidentialité et sécurité », cliquez sur « Ouvrir quand même » dans la section « Sécurité » et saisissez votre mot de passe pour confirmer.
4. Si le système indique qu'elle « est endommagée et ne peut pas être ouverte » : le fichier n'est pas abîmé, c'est Gatekeeper qui le bloque. Ouvrez « Terminal », lancez la commande ci-dessous, appuyez sur Entrée et saisissez votre mot de passe de session, puis rouvrez Hiddify :

```bash
sudo xattr -dr com.apple.quarantine /Applications/Hiddify.app
```

Cette commande retire seulement le marqueur de quarantaine qui signale un fichier téléchargé, et ne concerne que cette application. **N'utilisez pas** `sudo spctl --master-disable` pour désactiver Gatekeeper sur toute la machine.

À la première tentative de connexion après l'installation, le système vous demande aussi d'autoriser une « extension réseau ». Si vous sautez cette étape, l'icône tourne sans fin et la connexion n'aboutit jamais :

- **macOS 15 Sequoia et versions ultérieures** : « Réglages Système » → « Général » → « Ouverture et extensions », descendez jusqu'à « Extensions » en bas, passez la vue sur « Par catégorie », cliquez sur le ⓘ à côté de « Extensions réseau », activez l'interrupteur de Hiddify, puis saisissez votre mot de passe ou utilisez votre empreinte quand le système le demande.
- **macOS 13 Ventura / 14 Sonoma** : lancez d'abord Hiddify et cliquez une fois sur Connecter : l'alerte « Extension système bloquée » apparaît ; allez ensuite dans « Réglages Système » → « Confidentialité et sécurité », descendez jusqu'au message indiquant que le chargement d'un logiciel système du développeur … a été bloqué, cliquez sur « Autoriser » et saisissez votre mot de passe.

Sur un Mac fourni par l'entreprise, si ces boutons sont grisés, c'est qu'une politique de gestion des appareils les verrouille ; adressez-vous au service informatique, ou utilisez plutôt les clients Cisco, OpenVPN ou Privé.

## Linux

1. Téléchargez le .deb depuis la zone de téléchargement de la page Hiddify et double-cliquez dessus pour l'installer avec la logithèque, ou ouvrez un terminal dans le dossier de téléchargement et lancez (Debian, Ubuntu et dérivées) :

```bash
sudo apt install ./downloaded-file-name.deb
```

2. Une connexion juste après l'installation affiche « operation not permitted » et le mode VPN ne démarre pas, car le deb officiel n'obtient pas cette permission à l'installation. Ouvrez un terminal et lancez la commande ci-dessous pour autoriser Hiddify, puis rouvrez Hiddify :

```bash
echo /usr/share/hiddify/lib | sudo tee /etc/ld.so.conf.d/hiddify.conf && sudo ldconfig && sudo setcap cap_net_admin,cap_net_raw+ep /usr/share/hiddify/hiddify
```

3. **Relancez-la après chaque mise à jour de Hiddify** : l'autorisation est attachée au fichier du programme, et une mise à jour remplace ce fichier, donc l'autorisation disparaît.

Le paquet deb est en x64 ; sur les appareils Linux ARM, utilisez OpenVPN, avec le même compte.

## Android

1. Téléchargez le .apk depuis la zone de téléchargement de la page Hiddify. La page recommande automatiquement l'architecture de votre téléphone ; l'immense majorité des téléphones sont en ARM64. Si vous avez accès à Google Play, vous pouvez aussi l'installer directement depuis la boutique.
2. Si un message sur les « sources inconnues » ou un avertissement d'un logiciel de sécurité apparaît pendant l'installation, autorisez-la.
3. La première fois que vous touchez Connecter, le système demande l'autorisation VPN ; acceptez.

## iPhone / iPad

1. Cherchez « Hiddify » dans l'App Store et installez-la ; elle est gratuite.
2. Si vous ne la trouvez pas, ou si le message « Cette app n'est actuellement pas disponible dans votre pays ou région » s'affiche : sur iOS, installez-la avec un identifiant Apple d'une région autre que la Chine (Hiddify est présente dans les App Store des États-Unis, de Hong Kong, de Taïwan, du Japon et de Singapour). Nous conseillons d'en créer un nouveau : dans l'App Store, touchez « Obtenir » sur n'importe quelle app gratuite → « Créer un identifiant Apple », choisissez une région comme Hong Kong ou les États-Unis, et « Aucun » comme moyen de paiement. Vous ne changez de compte que dans l'App Store, iCloud n'est pas touché. Pour la marche à suivre complète, voir [06 · Quand iOS refuse d'installer une app](06-ios-app-store.md).
3. La première fois que vous touchez Connecter, le système demande l'autorisation VPN ; acceptez.

**N'utilisez pas** un identifiant Apple prêté par quelqu'un d'autre : son propriétaire peut verrouiller votre appareil à distance.

## Après l'installation : importer un abonnement et se connecter

1. Connectez-vous au site et ouvrez la page Hiddify.
2. Cliquez sur le drapeau de la région voulue pour afficher un QR code ; ou cliquez sur « Importer toutes les régions · sélection auto » en haut de la page pour importer d'un coup toutes les régions hors Chine et laisser le client choisir automatiquement. **La région Chine s'importe à part** : pour regarder des vidéos ou utiliser une banque en ligne chinoise depuis l'étranger, cliquez sur le drapeau chinois pour l'importer.
3. Sous le QR code se trouvent trois boutons, classés par type d'abonnement. Hiddify utilise le premier (il affiche Hiddify / sing-box / GUI.for.SingBox / Karing, avec le sous-titre « Abonnement sing-box »), le même sur téléphone et sur ordinateur. Sur téléphone : touchez-le, puis basculez dans Hiddify et ajoutez-le comme indiqué, ou scannez le code avec Hiddify sur un autre appareil. Sur ordinateur : cliquez dessus pour copier une adresse https://, puis dans Hiddify cliquez sur « + » → « Add from clipboard » (ajouter depuis le presse-papiers).
4. Cliquez sur Connecter.

Pour la différence entre les trois boutons, l'import dans Clash et d'autres clients, et la question de l'expiration d'un abonnement, voir [02 · Importer un lien d'abonnement (Hiddify, Clash, Shadowrocket)](02-singbox-subscription-links.md). Si l'import est fait mais que la connexion échoue, voir [Dépannage 04](../troubleshooting/04-singbox-import-not-connecting.md).

## FAQ

**Avez-vous modifié les programmes d'installation ?** Non. Les programmes d'installation pour ordinateur sont des copies conformes des paquets officiels de Hiddify. Chaque ligne de la page Hiddify renvoie à la page de publication officielle, pour que vous compariez les versions vous-même, et vous pouvez aussi envoyer le fichier sur VirusTotal pour une double vérification.


**J'ai déjà lancé la commande xattr sur mon Mac et ça ne se connecte toujours pas ?** Le plus probable : l'« extension réseau » n'a pas été autorisée ; suivez la section macOS ci-dessus et activez l'interrupteur de Hiddify dans Réglages Système.

**Après une mise à jour de Hiddify sous Linux, le mode VPN ne marche plus ?** C'est normal ; relancez la commande d'autorisation une fois après chaque mise à jour.

**Fonctionne-t-elle sur les ordinateurs Windows ou Linux ARM ?** Oui, avec une autre méthode d'accès comme OpenVPN, et le même compte ; les paquets Hiddify pour ordinateur sont actuellement en x64.

**Vous ne voulez pas vous embêter avec les autorisations ?** Cisco (Cisco Secure Client), OpenVPN (OpenVPN Connect) et Privé (Tailscale) s'ouvrent tous d'un double-clic ; les antivirus ne les signalent pas, macOS ne prétend pas qu'ils sont « endommagés », et c'est le même compte.

## Pour aller plus loin

- [Page Hiddify : téléchargement des clients et QR codes de chaque région](https://www.leotun.com/fr/singbox?utm_source=github&utm_content=client-09)
- [Importer un lien d'abonnement (Hiddify, Clash, Shadowrocket)](https://www.leotun.com/fr/guides/singbox-subscription?utm_source=github&utm_content=client-09)
- [Client signalé par l'antivirus / Mac qui le dit endommagé : vérifier d'abord, autoriser ensuite](https://www.leotun.com/fr/guides/antivirus-false-positive?utm_source=github&utm_content=client-09)
- [L'autorisation « extension réseau » de macOS : ce que c'est et comment l'accorder](https://www.leotun.com/fr/guides/macos-network-extension?utm_source=github&utm_content=client-09)
- [Quand iOS refuse d'installer une app](https://www.leotun.com/fr/guides/ios-app-store?utm_source=github&utm_content=client-09)

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-09) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-09) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre permanente
