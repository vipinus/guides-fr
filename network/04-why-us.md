# 04 · Ce qui nous distingue des autres VPN

Les VPN du marché se rangent grosso modo en trois familles : les grandes marques internationales destinées au monde entier, les fournisseurs de lignes proxy bien connus dans le monde sinophone (des abonnements proxy revendus, appelés « jichang » en chinois), et toutes sortes de logiciels gratuits. LeoTun exploite ses propres serveurs depuis 2006 et ne fait qu'une chose : garder une connexion stable dans les deux sens, pour les utilisateurs en Chine continentale comme pour ceux qui, à l'étranger, ont besoin de la Chine. Cet article nous compare point par point à ces trois familles, en indiquant à qui chacune convient et comment nous travaillons, pour que vous y voyiez clair avant de payer.

## Notre positionnement en une phrase

Nous sommes un service **optimisé spécifiquement pour le réseau de Chine continentale**, pas un revendeur de lignes internationales. La qualité des sorties internationales de China Telecom, China Unicom et China Mobile varie énormément : nous réglons chaque opérateur séparément et recommandons des régions différentes selon l'opérateur. Nous avons des nœuds d'arrivée en Chine, pour que même les utilisateurs avec un accès Internet moyen aient un point d'entrée stable. Et nous ajustons sans cesse ports et protocoles au gré de l'évolution du réseau en Chine, au lieu de tout installer puis de ne plus y toucher.

À l'inverse, quand on est à l'étranger et qu'on a besoin des services chinois, il suffit de choisir la région Chine avec le même compte : les sites chinois sortent par une IP chinoise, tandis que les sites hors de Chine continuent de sortir hors de Chine. Accéder à la Chine depuis l'étranger et accéder à l'étranger depuis la Chine, ce sont les deux sens d'une même chose.

## Face aux grandes marques internationales

- Leurs points forts : des dizaines de pays, des milliers de serveurs, des applis abouties, des politiques sans journaux vérifiées par des audits indépendants. Si vous êtes en Europe ou en Amérique du Nord et voulez seulement chiffrer votre connexion sur un Wi‑Fi public ou regarder le catalogue de streaming d'un autre pays, c'est un bon choix.
- Leurs points faibles : le produit n'est pas conçu pour le réseau chinois. La signature d'un protocole propriétaire est fixe, et dès qu'elle est identifiée en Chine, c'est toute l'appli qui cesse de fonctionner ; ils n'ont pas de nœuds d'arrivée en Chine, donc pour regarder des vidéos chinoises depuis l'étranger, soit la fonction n'existe pas, soit elle passe par des IP de Hong Kong ou de Taïwan, que Tencent Video et iQIYI bloquent tout autant.
- Ce que nous faisons : uniquement des protocoles standard (AnyConnect, OpenVPN, Hiddify, Tailscale, proxy web HTTPS), avec des clients fournis par les éditeurs ou la communauté open source. Ce qui peut être bloqué, c'est une adresse précise, et il suffit de changer d'adresse ; le client lui-même ne peut pas être neutralisé.
- Nos compromis : 24 régions, chacune adossée à plusieurs machines, la moins chargée étant choisie automatiquement à la connexion ; les clients sont les versions officielles des éditeurs et de la communauté open source, configurées par QR code ou import en un clic ; pas de rapport d'audit tiers ; ce que nous enregistrons et n'enregistrons pas est écrit noir sur blanc sur la page À propos, et nous misons sur cette transparence plutôt que sur un label.

## Face aux fournisseurs de lignes proxy

- Leurs points forts : pas chers, beaucoup de nœuds, utilisables dès qu'on colle un lien d'abonnement, et ceux qui aiment bricoler leurs clients apprécient la liberté.
- Leurs points faibles : la plupart sont des particuliers ou de petites équipes qui louent des machines à l'étranger et revendent du trafic, sans point d'arrivée en Chine qui leur appartienne, et la qualité des sorties dépend des lignes louées ; les disparitions avec la caisse, les changements de nom et les fermetures sont fréquents, et payer un an ne garantit pas de pouvoir l'utiliser un an ; les clients sont presque entièrement laissés aux utilisateurs, et personne n'est responsable quand quelque chose ne va pas.
- Ce que nous faisons : les machines nous appartiennent, et les sorties en Chine sont nos propres machines, enregistrées sous nom réel chez des hébergeurs cloud de Chine continentale ; un même compte offre six méthodes de connexion, et la solution routeur pour tout le foyer comme le groupe d'assistance 24 h/24 n'existent pas chez les fournisseurs de lignes proxy ; nous fonctionnons de 2006 à aujourd'hui, et les comptes, les durées de validité et les prix n'ont pas changé avec le changement de nom.
- Nos prix : formule Personnel 5 $ par mois, Famille 10 $, Entreprise 20 $, ce qui couvre nos propres machines, six méthodes de connexion et le groupe d'assistance 24 h/24 ; vous ne choisissez que la région, et derrière chaque région le système prend la machine la moins chargée : inutile de tester les débits et de trier les nœuds vous-même.

## Face aux logiciels gratuits

- Leurs points forts : ça ne coûte rien, et ça suffit pour une recherche de temps en temps.
- Leurs points faibles : la bande passante de sortie en Chine continentale se paie à l'usage, donc un service gratuit ne tient qu'en entassant les utilisateurs, en bridant le débit ou en vendant des données ; les extensions de navigateur ne font passer que les requêtes web, pas la vidéo, les applis ni le DNS du système ; enfin, un installateur d'origine inconnue est un risque en soi, voir « Comment repérer un logiciel VPN à risque ».
- Ce que nous faisons : l'essai gratuit de 4 heures sans carte bancaire sert à juger sur pièce ; le paiement à la journée (points) s'adresse aux utilisateurs occasionnels ; quand un ami que vous invitez paie, vous recevez chacun 20 jours (base formule Personnel), une source durable de temps gratuit.
- Notre organisation : le temps gratuit vient de l'essai de 4 heures et des récompenses de parrainage ; pour un usage durable, on paie au mois, à l'année ou à la journée.

## Six méthodes de connexion, un seul compte

Privé (Tailscale) : une seule connexion et l'appareil reste en ligne pour de bon, avec changement de région depuis le menu. Cisco AnyConnect : la meilleure compatibilité, intégré au système ou via le client officiel. OpenVPN : pour les routeurs, NAS et Linux. Proxy Web : seul le navigateur passe par la ligne, et par conception il n'y a pas de connexion qui puisse tomber. Hiddify : résiste à la perte de paquets, avec le meilleur débit. Routeur : accès pour tout le foyer, téléviseurs, box TV et appareils des parents âgés compris.

Chaque réseau a sa méthode la plus adaptée, c'est pourquoi vous avez les six : avec le même compte, vous basculez à tout moment, de Hiddify vers AnyConnect quand un réseau de campus restreint l'UDP, vers le Proxy Web quand la connexion est instable. Pour choisir, voir « Quelle méthode de connexion pour quelle situation ».

## Règles du compte

- Le compte existe en trois formules, Personnel, Famille et Entreprise, avec respectivement 2, 4 et 8 appareils en ligne en même temps ; régions, trafic et méthodes de connexion sont identiques sur les trois. Le nombre d'appareils sur lesquels vous installez n'est pas limité, seul compte le nombre de connexions simultanées. Si vous dépassez la limite de votre formule, vous pouvez passer temporairement à une formule supérieure (le temps restant est converti à valeur égale selon le prix) et revenir en arrière ensuite.
- Vous pouvez passer d'une formule à l'autre à tout moment, le temps restant étant converti à valeur égale (Famille et Entreprise coûtent respectivement 2 fois et 4 fois le prix de Personnel) ; les trois formules prennent en charge le routeur, et Personnel suffit pour une personne seule.
- Les remboursements se font au prorata du temps utilisé, à tout moment, et sont traités manuellement ; aucun délai précis de versement n'est promis.
- Débit : nous garantissons une lecture fluide de YouTube, même à l'heure de pointe du soir, à condition que votre accès Internet soit bon : China Unicom dans le nord ou China Telecom dans le sud. Le haut débit partagé des résidences (accès mutualisé fourni par l'immeuble, très répandu en Chine) fait exception. Si une région est lente, changez de région ou de méthode de connexion.
- Les configurations Hiddify et OpenVPN contiennent votre compte, et changer le mot de passe révoque les anciennes configurations : si un téléphone est perdu ou un lien a fuité, un changement de mot de passe suffit à tout reprendre, puis il n'y a plus qu'à réimporter.

## Notre façon de faire

- Nous ne gardons que les informations nécessaires à la facturation. Nous n'enregistrons pas ce que vous consultez, n'injectons pas de publicité et ne vendons pas de données.
- Tous les clients viennent d'éditeurs officiels et d'organisations open source reconnues : Cisco, OpenVPN, Hiddify et Tailscale, mis en miroir tels quels, sans modification ; la configuration se fait par QR code ou import en un clic.
- La région Chine tourne sur des machines en Chine continentale, et ses IP de sortie sont toutes en Chine continentale.

## FAQ

**Êtes-vous plus sûrs que les grandes marques internationales ?** La force du chiffrement est comparable : tout le monde utilise des protocoles standard. La différence tient au modèle de confiance : les grandes marques s'appuient sur des rapports d'audit ; nous, nous ne gardons que les informations nécessaires à la facturation, et tous nos clients viennent d'éditeurs officiels et d'organisations open source reconnues.

**Pourquoi ne pas proposer des centaines de nœuds comme les fournisseurs de lignes proxy ?** Plus de nœuds ne veut pas dire plus de stabilité. Derrière chacune de nos régions se trouvent plusieurs machines, et à la connexion le système choisit la moins chargée : pas besoin de tester les débits ni de trier les nœuds vous-même. Quand une adresse est bloquée, elle est remplacée automatiquement, sans rien changer dans votre client.

**Le prix pourrait-il être plus bas ?** La formule Personnel coûte 5 $ par mois, et plus la durée est longue, plus la remise est forte (−5 % → −10 % → −20 %) ; à la journée avec des points, cela revient à environ 0,32 $ par jour ; quand un ami que vous invitez paie, vous recevez chacun 20 jours de plus (base formule Personnel), sans limite de nombre. L'inscription donne aussi droit à un essai gratuit de 4 heures.

**Comment vérifier ce que vous dites ?** Prenez l'essai de 4 heures, connectez-vous à la région Chine à l'heure de pointe du soir et regardez un épisode sur Tencent Video, connectez-vous à une région hors de Chine et ouvrez YouTube, puis vérifiez la localisation enregistrée de l'IP et une page de test IPv6. La liste de contrôle se trouve dans « Bien choisir un VPN avec IP chinoise ».


## Pour aller plus loin

- [Quelle méthode de connexion pour quelle situation](https://www.leotun.com/fr/guides/choose-connection?utm_source=github&utm_content=network-04)
- [Comment repérer un logiciel VPN à risque](https://www.leotun.com/fr/guides/risky-vpn-apps?utm_source=github&utm_content=network-04)
- [VPN vers la Chine : gratuit ou payant](https://www.leotun.com/fr/guides/free-vs-paid?utm_source=github&utm_content=network-04)
- [À propos : comment le service est construit et ce que nous enregistrons](https://www.leotun.com/fr/about?utm_source=github&utm_content=network-04)

Version de cet article sur le site : https://www.leotun.com/fr/guides/why-us?utm_source=github&utm_content=network-04

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=network-04) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=network-04) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; chaque ami invité qui paie vous rapporte à tous les deux 20 jours en formule Personnel, une offre sans date de fin
