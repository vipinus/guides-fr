# 05 · Comment repérer un logiciel VPN à risque

Tout votre trafic passe entre les mains d'une appli VPN, et elle peut regarder ce qu'elle veut. Deux catégories de produits sur le marché appellent une prudence particulière : d'une part ce que le milieu appelle les « VPN rouges », adossés aux autorités, qui exigent votre identité réelle au nom de la conformité et transmettent les journaux ; d'autre part les accélérateurs gratuits d'origine inconnue, qui se rémunèrent sur vos données, sur votre appareil ou sur ce qu'ils y installent en douce. Point commun des deux : « ça marche très bien à l'usage » ; le problème se trouve là où vous ne voyez rien. Voici dix signaux que vous pouvez vérifier vous-même, que faire si vous en avez déjà installé un, et un auto-contrôle en trois minutes.

## Pourquoi un logiciel VPN est plus risqué qu'une appli ordinaire

Un VPN travaille au niveau du système : il reçoit le trafic de tous les programmes de l'appareil, y compris ceux dont vous ignorez qu'ils tournent en arrière-plan. Une appli ordinaire divulgue les données qu'elle a elle-même collectées ; un VPN divulgue tout ce que vous faites sur cet appareil. Le niveau d'exigence pour choisir un logiciel VPN doit donc être bien plus élevé que pour une appli ordinaire.

« Je l'ai utilisé et il ne s'est rien passé » ne prouve pas la sécurité. L'enregistrement, la transmission et l'injection se font côté serveur ou en arrière-plan et sont imperceptibles côté utilisateur ; quand un problème survient, c'est souvent des mois plus tard, et impossible de remonter jusqu'au logiciel en cause.

## Dix signaux

- Origine inconnue : l'installateur arrive par une discussion de groupe, un espace de stockage en ligne ou un QR code, sans site officiel ni page sur une boutique d'applis. Un client légitime vient soit d'une boutique d'applis, soit du site officiel du développeur, soit d'une page de publication où la signature peut être vérifiée.
- Vous demande d'installer un certificat racine : pendant l'installation, il vous demande de « faire confiance au certificat » ou d'« installer le profil » et exige d'approuver une autorité de certification. Une fois le certificat racine installé, il peut ouvrir tout votre trafic HTTPS, banque en ligne et e-mail compris. Un VPN normal n'a pas besoin de cette étape.
- Trop d'autorisations : un VPN qui demande les contacts, les SMS, l'historique des appels, la position précise et l'accès à la photothèque. Un VPN n'a besoin que de l'autorisation de créer un tunnel ; le reste ne lui sert à rien.
- Exige une inscription sous identité réelle : l'inscription demande une carte d'identité, une reconnaissance faciale ou l'association d'un numéro de mobile de Chine continentale. C'est ainsi qu'un VPN dit conforme relie votre identité à vos journaux de trafic ; un service légitime n'a besoin que d'une adresse e-mail.
- Protocole propriétaire + client fermé : vous ne pouvez utiliser que sa propre appli, et il ne prend en charge aucun protocole standard (AnyConnect, OpenVPN, WireGuard, Hiddify), si bien que vous ne pouvez pas vérifier avec un client open source tiers ce qu'il transmet réellement.
- Gratuit, sans source de revenus visible : pas d'offre payante, pas de publicité, pas de clients professionnels, et pourtant il tourne année après année. La bande passante de sortie en Chine continentale se facture à l'usage, et un service qui ne fait pas payer se rattrape toujours ailleurs.
- Ni société, ni assistance, ni historique : l'entité qui l'exploite est introuvable, personne à contacter, le domaine a été enregistré il y a moins d'un an, et il change souvent de nom et de façade.
- Trafic anormal en arrière-plan : l'appareil envoie des données en continu même quand vous ne l'utilisez pas, et la batterie comme le forfait fondent vite. Il se peut qu'il fasse de votre appareil la sortie de quelqu'un d'autre, ou qu'il synchronise vos données.
- Sa promotion insiste sur « officiel », « enregistré », « légal et conforme » et laisse entendre que tout le reste est illégal : c'est l'argumentaire le plus typique d'un « VPN rouge », dont la conformité consiste à enregistrer et transmettre.
- Les notes sur les boutiques d'applis sont unanimes, les avis se ressemblent, et le nombre de téléchargements est sans rapport avec le nombre d'avis : ils sont truqués.

## Comment vérifier

1. Regardez le protocole : le site officiel indique-t-il le protocole utilisé, et peut-on utiliser un client tiers ? Avec un service auquel on peut se connecter avec des clients open source ou standard comme OpenVPN, AnyConnect, Hiddify et Tailscale, vous pouvez capturer les paquets vous-même et voir ce qui est transmis.
2. Regardez les autorisations : après l'installation, allez dans les réglages du système pour voir les autorisations demandées, désactivez tout sauf le VPN, et voyez si cela fonctionne encore. Sinon, désinstallez.
3. Regardez les certificats : sur iOS, Réglages → Général → VPN et gestion de l'appareil ; sur Android, Paramètres → Sécurité → Chiffrement et identifiants → Identifiants de confiance → Utilisateur ; sous Windows, « Autorités de certification racines de confiance » dans le gestionnaire de certificats. S'il y a un certificat qu'il a installé, supprimez-le et désinstallez l'appli.
4. Testez les fuites : une fois connecté, ouvrez un test de fuite DNS et une page de test IPv6 pour voir si la résolution et l'adresse passent toutes deux par ses serveurs ; puis ouvrez un site HTTPS et vérifiez que l'émetteur du certificat est bien l'autorité d'origine.
5. Vérifiez l'entité : le site officiel présente-t-il la société ou l'équipe, depuis combien d'années le service existe et où se trouve l'assistance ; les règles de remboursement sont-elles écrites ; la politique de confidentialité dit-elle clairement ce qui est enregistré ?

## Que faire si vous en avez déjà installé un

1. Désinstallez le logiciel, puis vérifiez les emplacements cités plus haut et supprimez les certificats et profils qu'il a installés.
2. Changez vos mots de passe : banque en ligne, e-mail, comptes fréquemment utilisés, en particulier ceux auxquels vous vous êtes connecté pendant que vous l'utilisiez.
3. Pour les comptes avec validation en deux étapes, consultez l'historique des connexions et supprimez tout appareil inconnu.
4. S'il était installé sur un routeur, restaurez les réglages d'usine puis reflashez un firmware officiel ou de confiance.

## Comment nous vous permettons de vérifier

Tous les clients LeoTun proviennent d'éditeurs officiels et d'organisations open source reconnues : Cisco, OpenVPN, Hiddify et Tailscale, reproduits tels quels sans modification, et vous pouvez à tout moment remplacer la copie téléchargée sur ce site par le client officiel ou open source. Les protocoles sont tous standard et vérifiables par capture de paquets.

L'inscription ne demande qu'une adresse e-mail, ni numéro de téléphone ni pièce d'identité. Nous ne conservons que les informations nécessaires à la facturation ; nous n'enregistrons pas ce que vous consultez, n'injectons pas de publicité et ne vendons pas de données.

Nous n'installons aucun certificat et ne demandons ni contacts ni position. Si un jour notre client vous demande d'installer un certificat racine, ce n'est certainement pas nous.

## FAQ

**Tout ce qui est gratuit est-il inutilisable ?** Les clients de la communauté open source (OpenVPN, Hiddify, Tailscale) sont eux-mêmes gratuits et dignes de confiance ; le risque vient d'un « service gratuit », pas d'un « logiciel gratuit ». Face à un service gratuit, demandez-vous de quoi il vit.

**Un logiciel est-il sûr parce qu'il est sur une boutique d'applis ?** Être référencé prouve seulement qu'il a passé la vérification automatique de la boutique ; cela ne veut pas dire que le serveur n'enregistre rien. Regardez parmi les dix signaux ci-dessus les autorisations, l'identité réelle, le protocole et l'entité ; la boutique ne les vérifie pas pour vous.

**Qu'est-ce qu'un « VPN rouge » ?** Le nom donné dans le milieu à un VPN adossé aux autorités, qui exige une inscription sous identité réelle au nom de la conformité et conserve des journaux. Ils se présentent généralement comme « officiels » et « légaux » et fonctionnent normalement à l'usage ; le problème, c'est que votre identité et tous vos journaux de trafic sont liés.

**Comment savoir si un VPN a enregistré mes contenus ?** Impossible à voir côté utilisateur ; vous ne pouvez que regarder combien de moyens de vérification il vous donne : protocole standard ou non, client open source ou non, politique de confidentialité précise ou non, entité exploitante identifiable ou non. S'il n'en a aucun des quatre, partez du principe qu'il enregistre.

**Un firmware de routeur présente-t-il aussi ce risque ?** Oui ; un « firmware de contournement de la censure » d'origine inconnue peut détourner tout le réseau de la maison. Ne flashez qu'OpenWrt officiel ou un firmware dont la source est vérifiable ; le firmware de ce site est compilé à partir d'OpenWrt, avec seulement l'ajout des composants de connexion à la ligne et des règles de routage sélectif.

## Pour aller plus loin

- [Ce qui nous distingue des autres VPN](https://www.leotun.com/fr/guides/why-us?utm_source=github&utm_content=network-05)
- [VPN vers la Chine : gratuit ou payant](https://www.leotun.com/fr/guides/free-vs-paid?utm_source=github&utm_content=network-05)
- [Que faire quand Tencent Video affiche une restriction de droits à l'étranger](https://www.leotun.com/fr/guides/overseas-video?utm_source=github&utm_content=network-05)
- [À propos : comment le service est construit et ce que nous enregistrons](https://www.leotun.com/fr/about?utm_source=github&utm_content=network-05)

Version de cet article sur le site : https://www.leotun.com/fr/guides/risky-vpn-apps?utm_source=github&utm_content=network-05

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=network-05) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=network-05) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
