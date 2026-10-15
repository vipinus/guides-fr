# 06 · Que faire quand iOS refuse d'installer une app

Si vous ne trouvez pas Hiddify, Tailscale ou Telegram sur votre iPhone, ou si le message « Cette app n'est actuellement pas disponible dans votre pays ou région » s'affiche, l'app n'a pas disparu : l'App Store est découpé en boutiques selon la région de votre identifiant Apple, et la boutique chinoise ne propose pas la plupart des apps réseau. Sur iOS, installez-les depuis l'App Store avec un identifiant Apple d'une région autre que la Chine ; la marche à suivre est sur cette page. Nous conseillons d'en créer un nouveau plutôt que de modifier votre compte existant. Voici les étapes, l'astuce pour choisir « Aucun » comme moyen de paiement, et pourquoi il ne faut jamais utiliser un compte prêté par quelqu'un d'autre.

## Pourquoi cela arrive

L'App Store est découpé en boutiques selon la région de l'identifiant Apple, et chaque région propose des apps différentes. La boutique chinoise n'a ni Hiddify ni Tailscale, et Telegram et Discord y apparaissent et disparaissent ; Cisco Secure Client et OpenVPN Connect sont disponibles dans la plupart des régions. C'est une différence de catalogue, pas un problème avec les apps, et un compte d'une autre région peut les installer.

Sur iPhone, Hiddify comme la méthode Privé (Tailscale) de ce site s'installent depuis l'App Store ; suivez simplement les étapes ci-dessous pour passer à un identifiant Apple d'une autre région. Les fichiers d'installation pour Android, Windows et macOS sont fournis directement par ce site et ne sont pas concernés.

## Option 1 (recommandée) : créer un nouvel identifiant Apple hors de la région Chine

1. Déconnectez-vous du compte App Store actuel : Réglages → votre nom en haut → Contenu multimédia et achats → Se déconnecter. Cela ne vous déconnecte que de l'App Store, pas d'iCloud : vos photos, sauvegardes et contacts ne sont pas touchés.
2. Dans l'App Store, trouvez une app gratuite, touchez « Obtenir » et suivez l'invite pour « Créer un identifiant Apple ». Choisissez comme région les États-Unis, Hong Kong, le Japon ou Singapour, et « Aucun » comme moyen de paiement. Ce choix « Aucun » n'apparaît que si vous créez le compte en téléchargeant une app gratuite ; en passant directement par le site web, il n'est souvent pas proposé.
3. Connectez-vous à l'App Store avec le nouveau compte, puis cherchez et téléchargez Hiddify, Tailscale et Telegram.
4. Une fois les apps installées, vous pouvez revenir à votre compte d'origine ; les apps installées continuent de fonctionner et de se mettre à jour normalement. Rebasculez quand vous devez installer une nouvelle app.

## Option 2 : changer la région de votre compte existant

Connectez-vous sur account.apple.com et changez le pays ou la région. Il faut d'abord résilier tous les abonnements et épuiser votre solde, parfois ajouter un moyen de paiement local, et revenir en arrière est tout aussi pénible. À éviter, sauf si vous comptez de toute façon changer de région durablement.

## Ce qu'il ne faut jamais faire

- N'utilisez pas un identifiant Apple prêté par quelqu'un d'autre, y compris les « comptes partagés » qui circulent dans des groupes ou en ligne. Le propriétaire du compte peut verrouiller votre appareil à distance, et un iPhone verrouillé ne peut être débloqué que par lui ; une fois l'authentification à deux facteurs activée, elle ne peut plus être désactivée, et le risque comme les litiges retombent sur vous. L'assistance de ce site ne fournira pas non plus de compte partagé.
- N'installez pas de profils de configuration d'origine inconnue, ni de fichiers d'installation « signés avec un certificat d'entreprise ». Ce sont des moyens courants de contourner la boutique, mais aussi une porte d'entrée pour implanter des certificats et détourner le trafic.

## Après l'installation

Hiddify : retournez sur la page Hiddify de ce site et scannez le code, ou touchez le bouton « Abonnement sing-box » pour copier, puis passez dans Hiddify et ajoutez-le. Tailscale : déconnectez-vous d'abord du compte officiel, puis suivez les étapes de la page Privé pour saisir l'adresse du serveur de contrôle de ce site. Telegram, Discord : allez sur la page Contact de ce site et scannez le code pour rejoindre le groupe.

## FAQ

**Faut-il une carte bancaire pour créer un compte dans une autre région ?** Non. Avec l'option 1 (création en téléchargeant une app gratuite), vous pouvez choisir « Aucun » comme moyen de paiement.

**Le nouveau compte touche-t-il à mon iCloud et à mes photos ?** Non. Vous ne changez de compte que dans l'App Store ; iCloud reste sur votre compte d'origine.

**Est-ce pareil sur iPad ?** Oui, iPadOS suit les mêmes règles d'App Store.

**Les téléphones Android ont-ils aussi ce problème ?** Non. Les fichiers d'installation pour Android, Windows, macOS et Linux sont distribués directement par ce site et ne dépendent d'aucune boutique d'apps.

## Pour aller plus loin

- [Page Contact : cartes de téléchargement des clients et les trois groupes](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-06)
- [Hiddify : importer en scannant le code](https://www.leotun.com/fr/singbox?utm_source=github&utm_content=client-06)
- [Privé (Tailscale) : étapes de connexion](https://www.leotun.com/fr/mesh?utm_source=github&utm_content=client-06)
- [Comment nous contacter et ne pas perdre le contact](https://www.leotun.com/fr/guides/stay-in-touch?utm_source=github&utm_content=client-06)

Version de cet article sur le site : https://www.leotun.com/fr/guides/ios-app-store?utm_source=github&utm_content=client-06

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-06) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-06) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
