# 12 · Se préparer pour un voyage d'affaires ou un séjour

Pour un court séjour hors de Chine ou un voyage d'affaires en Chine, pas besoin de routeur ni d'étudier les protocoles : installez le client Cisco (Cisco Secure Client) sur votre téléphone, faites un essai de connexion avant de partir, et tout fonctionne dès l'atterrissage. Les deux sens reviennent au même : hors de Chine, quand il vous faut Google, la messagerie de l'entreprise et les cartes, choisissez une région étrangère proche ; en Chine, pour regarder des vidéos chinoises ou vous connecter à une banque en ligne chinoise, choisissez la région Chine. Cet article couvre les dix minutes de préparation avant le départ, deux pièges courants des réseaux d'hôtel et d'aéroport, et l'utilisation des applis de banque et de paiement.

## Dix minutes avant de partir

1. Installez Cisco Secure Client sur votre téléphone (App Store / Google Play, ou l'installateur de la page Cisco de ce site), connectez-vous à ce site et cliquez sur un drapeau pour copier l'adresse d'une région, saisissez-la, puis connectez-vous une fois avec l'identifiant et le mot de passe de ce site pour vérifier que tout marche.
2. Copiez les adresses de deux autres régions et enregistrez-les dans le client : une proche de votre destination et une de secours. Le réseau sur place sera différent, et la meilleure région change souvent.
3. Notez les quatre domaines (leotun.com → 7d24hrs.com → 7x24btc.com → anyfq.com) et l'accès à au moins un groupe d'assistance, pour trouver de l'aide si quelque chose cloche dans un endroit dont vous ne connaissez pas le réseau.
4. Installez-en un aussi sur votre portable, ou utilisez l'extension de proxy web ; même quand un ordinateur professionnel ne peut pas installer de client, cela fonctionne.

## Une fois arrivé

- Si vous êtes passé sur une carte SIM locale ou avez activé l'itinérance, le client se connecte tel quel, sans rien reconfigurer ; si les données en itinérance sortent déjà du pays, la connexion à la ligne ne sert qu'à fixer la région de sortie.
- Hors de Chine, quand il vous faut Google, Gmail, la messagerie de l'entreprise et les cartes : choisissez une région étrangère proche pour le meilleur débit.
- En Chine, pour regarder Tencent Video et iQIYI, écouter NetEase Cloud Music ou vous connecter à une banque en ligne : choisissez la région Chine. Les sites chinois sortent par une IP chinoise et les sites étrangers ressortent toujours à l'étranger : être connecté à la région Chine en Chine ne vous empêche donc pas de continuer à utiliser Gmail.
- Si une région étrangère refuse de se connecter depuis la Chine : changez de région, passez aux données mobiles, et si cela échoue encore, passez à Hiddify ou OpenVPN ; le blocage des trois protocoles est indépendant.

## Deux pièges des réseaux d'hôtel, d'aéroport et de café

- Portail de connexion (portail captif) : après vous être connecté au Wi‑Fi, terminez d'abord l'authentification dans le navigateur, puis activez la ligne. Un client réglé pour se connecter automatiquement essaiera avant l'authentification et échouera ; patientez un instant ou reconnectez-vous manuellement.
- Restrictions UDP : bon nombre de réseaux d'hôtel et d'aéroport brident ou bloquent l'UDP. Cisco passe par TLS et n'est pas concerné : c'est aussi pourquoi Cisco est la première recommandation en voyage ; si vous utilisez Hiddify ou Privé et que c'est lent ou que ça coupe, passez à Cisco.

## Banque en ligne, paiements, 12306

Ces applis enregistrent l'IP de connexion, et les allers-retours entre l'étranger et la Chine sont ce qui déclenche le plus facilement le contrôle des risques. Quand vous avez une démarche à faire, connectez-vous d'abord à la région Chine puis ouvrez l'appli ; une fois terminé, quittez l'appli puis déconnectez-vous. En voyage, n'utilisez pas la même banque en ligne en alternant sans cesse entre les deux types de réseau.

Les codes de vérification par SMS qui n'arrivent jamais n'ont rien à voir avec la ligne : c'est une question d'itinérance du numéro. Avant de partir, activez l'itinérance de votre numéro chinois ou passez à un forfait qui reçoit les codes à l'étranger.

## FAQ

**Le voyage ne dure que quelques jours. Faut-il acheter un mois ?** Non. Demandez l'essai gratuit de 4 heures, ou rechargez des points et payez à la journée : la formule Personnel coûte 1 point par jour, soit environ 0,36 dollar US par jour, ce qui convient bien à quelques jours.

**Mon téléphone et mon portable peuvent-ils se connecter en même temps ?** Oui. Selon la formule, un compte permet 2 / 4 / 8 appareils en ligne simultanément (Personnel / Famille / Entreprise), et la formule Personnel correspond exactement à un téléphone plus un portable.

**Pourquoi recommander Cisco plutôt que Hiddify en voyage ?** Sur un réseau inconnu, la principale crainte est un UDP restreint. Cisco passe par TLS, comme la visite d'un site HTTPS, et passe presque partout ; Hiddify est plus rapide sur les réseaux avec beaucoup de pertes de paquets, mais ne fonctionne pas quand l'UDP est restreint. Installer les deux et basculer quand l'un ne marche pas est le plus fiable.

**Utiliser la région Chine hors de Chine ralentit-il les sites locaux ?** Les sites locaux sont plus fluides en connexion directe : déconnectez-vous une fois que vous avez fini avec les contenus chinois, ou ne vous connectez qu'au besoin.

## Pour aller plus loin

- [Cisco AnyConnect : téléchargement et configuration](https://www.leotun.com/fr/anyconnect?utm_source=github&utm_content=china-access-12)
- [Étudiants à l'étranger : bien configurer un VPN vers la Chine](https://www.leotun.com/fr/guides/students?utm_source=github&utm_content=china-access-12)
- [Nous joindre, et ne jamais perdre le contact](https://www.leotun.com/fr/guides/stay-in-touch?utm_source=github&utm_content=china-access-12)
- [VPN vers la Chine : gratuit ou payant](https://www.leotun.com/fr/guides/free-vs-paid?utm_source=github&utm_content=china-access-12)

Version de cet article sur le site : https://www.leotun.com/fr/guides/travel?utm_source=github&utm_content=china-access-12

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-12) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-12) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre permanente
