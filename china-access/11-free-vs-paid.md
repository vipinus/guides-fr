# 11 · VPN vers la Chine : gratuit ou payant

Faisons d'abord le calcul : le poste le plus coûteux d'une ligne vers la Chine, c'est la bande passante de sortie en Chine continentale, que les hébergeurs cloud chinois facturent au volume, et pas bon marché. Une offre gratuite ne fait pas de miracle. Elle ne peut que choisir l'une de trois voies : entasser beaucoup de monde sur une seule machine, limiter le trafic et la durée, ou se rembourser sur vos données et la publicité. Cela ne veut pas dire que le gratuit est inutilisable : pour une recherche de temps en temps, il suffit. Mais pour suivre des séries, faire de la banque en ligne ou équiper sa famille, un mois de ligne payante coûte généralement moins qu'un café, et le temps gagné vaut bien plus que cela.

## Trois raisons pour lesquelles les nœuds gratuits coupent sans arrêt

- Surchargés : des centaines ou des milliers de personnes partagent une machine et une ligne transfrontalière. Ça va dans la journée, et de 20 h à 23 h, heure de Pékin, tout le monde regarde tourner la roue de chargement.
- Bridés : ça coupe quand le trafic est épuisé, ça coupe quand le temps est écoulé, le débit est maintenu sous le 1080p, et une fenêtre surgit au milieu pour vous demander de payer. Ce sont en fait des versions d'essai de produits payants qui ne le disent pas.
- Revendus : ils tiennent en injectant de la publicité, en collectant l'historique de navigation ou en utilisant votre appareil comme nœud de sortie pour d'autres. C'est particulièrement courant avec les extensions de navigateur gratuites « vers la Chine ».

## Deux autres pièges invisibles du gratuit

Premièrement, la sortie n'est pas forcément en Chine continentale. Bon nombre de nœuds gratuits « vers la Chine » sont en réalité des adresses de Hong Kong, de Taïwan ou du Japon. Ils ouvrent les pages web chinoises, mais Tencent Video et iQIYI affichent toujours une restriction de droits, et la banque en ligne vous considère aussi comme à l'étranger. Vérifiez une fois la localisation enregistrée de l'IP après connexion et vous serez fixé.

Deuxièmement, l'IPv6 et le DNS ne sont pas traités. Les offres gratuites ne rejettent presque jamais l'IPv6 dans le tunnel, et si votre appareil a l'IPv6, le site vidéo voit toujours une adresse étrangère. C'est la cause la plus fréquente du « je suis bien connecté mais je ne peux toujours pas regarder » ; voir « Tencent Video ou iQIYI bloqués à l'étranger ».

## Quand le gratuit suffit, et quand il faut payer

Il suffit : pour ouvrir de temps en temps une page web chinoise afin de chercher une information ou lire l'actualité, sans exigence de débit ni de stabilité, et sans vous y connecter à aucun compte.

Il est temps de payer : si vous voulez regarder des séries et écouter de la musique, vous connecter à la banque en ligne ou à Alipay, équiper la télévision et les parents âgés à la maison, ou décrocher des billets à heure fixe. Ces situations exigent que « ça marche à chaque fois », et le gratuit ne peut pas l'offrir.

Un test simple : si une coupure vous agace, c'est qu'il est temps de payer.

## Combien dépenser

La formule Personnel de LeoTun coûte 5 dollars US par mois et comprend 24 régions, 2 appareils en ligne en même temps et toutes les méthodes de connexion (AnyConnect / OpenVPN / Hiddify / Proxy Web) ; elle s'utilise aussi avec un routeur. Les formules Famille et Entreprise coûtent respectivement 2 fois et 4 fois la formule Personnel. Régions, lignes et méthodes de connexion sont strictement identiques sur les trois formules ; seule change la limite d'appareils en ligne en même temps (4 et 8).

Si vous ne voulez pas acheter au mois, il y a deux voies : demandez d'abord l'essai gratuit de 4 heures (sans carte bancaire, une fois par compte) et testez-le une fois à l'heure de pointe du soir ; ou payez à la journée. Après une recharge de points, la formule Personnel consomme 1 point par jour, et 28 points coûtent 10 dollars US, soit environ 0,36 dollar US par jour ; n'en acheter que quelques jours avant un séjour en Chine convient très bien.

Quand un ami que vous invitez s'inscrit et paie pour la première fois, vous recevez chacun 15 points (environ 15 jours en formule Personnel), sans limite de nombre. C'est une source durable de temps gratuit.

## Comment juger sur pièce avant de payer

1. Demandez l'essai, connectez-vous à la ligne vers la Chine et vérifiez que l'IP est enregistrée en Chine continentale.
2. Ouvrez une page de test IPv6 et vérifiez que l'IPv6 est indisponible ou correspond lui aussi à une adresse en Chine continentale.
3. Lancez un épisode en 1080p après 20 h, heure de Pékin, et voyez s'il se met en mémoire tampon à répétition.
4. Passez à une autre sortie en Chine et refaites l'essai, pour vous assurer que ce n'était pas de la chance.
5. Vérifiez s'il utilise des protocoles standard (AnyConnect, OpenVPN, Hiddify) : les clients viennent de l'éditeur ou de la communauté open source, et si le fournisseur ferme, la configuration reste utilisable ailleurs ; avec une appli propriétaire, une fois qu'elle est retirée, il ne reste rien.

## FAQ

**Existe-t-il un VPN vers la Chine vraiment gratuit et stable ?** Pas qui soit stable sur la durée ; la structure des coûts l'interdit. Stable et gratuit, cela n'existe que pendant la période d'essai d'un produit payant. S'en servir pour juger sur pièce, c'est bien ; compter dessus à long terme, ce n'est pas réaliste.

**Un VPN gratuit va-t-il voler mes mots de passe ?** Il ne voit pas le contenu HTTPS dans le tunnel, mais il voit les domaines que vous consultez et peut injecter du contenu dans les pages non chiffrées. Les proxys gratuits en extension de navigateur ont des autorisations encore plus étendues. Ne vous connectez pas à la banque en ligne sur une ligne gratuite.

**Qu'est-ce qui revient le moins cher, à la journée ou au mois ?** Si vous l'utilisez 12 jours ou plus par mois, le mois est plus avantageux ; si vous l'utilisez quelques jours de temps en temps, c'est la journée. Les points n'expirent pas, et une recharge dure longtemps.

**L'essai exige-t-il une carte bancaire ?** Non. Demandez-le en page d'accueil après l'inscription : 4 heures avec toutes les fonctions, une fois par compte.

**J'ai payé et ça coupe toujours. Que faire ?** Changez d'abord de région, puis de méthode de connexion (les trois protocoles sont utilisables sur le même compte) ; si ça ne fonctionne toujours pas, lisez le guide de dépannage ou contactez l'assistance. Payer, c'est aussi avoir quelqu'un de responsable.

## Pour aller plus loin

- [Tarifs et essai gratuit](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-11)
- [Bien choisir un VPN avec IP chinoise](https://www.leotun.com/fr/guides/choose-china-vpn?utm_source=github&utm_content=china-access-11)
- [Tencent Video ou iQIYI bloqués à l'étranger : que faire](https://www.leotun.com/fr/guides/overseas-video?utm_source=github&utm_content=china-access-11)
- [VPN vers la Chine pour les étudiants à l'étranger](https://www.leotun.com/fr/guides/students?utm_source=github&utm_content=china-access-11)

Version de cet article sur le site : https://www.leotun.com/fr/guides/free-vs-paid?utm_source=github&utm_content=china-access-11

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-11) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-11) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
