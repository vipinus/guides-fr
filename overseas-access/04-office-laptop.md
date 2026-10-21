# 04 · Avec un ordinateur professionnel : sans droits administrateur, VPN d'entreprise déjà actif

Un ordinateur professionnel a trois contraintes : impossible d'installer un logiciel non autorisé, pas de droits administrateur, et il est souvent déjà connecté au VPN de l'entreprise. Un VPN qui couvre tout l'appareil, ici, soit ne s'installe pas, soit entre en conflit avec le VPN de l'entreprise. Le bon outil, c'est le Proxy Web : une extension de navigateur qui ne fait passer par la ligne que les requêtes de ce navigateur, tandis que l'intranet, le client de messagerie et le VPN de l'entreprise restent exactement comme ils sont, sans droits administrateur. Cet article explique comment le configurer, ce qu'il permet, ce qu'il ne faut pas faire, et comment rester en bons termes avec la politique informatique de l'entreprise.

## Pourquoi le Proxy Web

- Aucun client à installer : ce n'est qu'une extension de navigateur, et la plupart des entreprises autorisent les extensions mais pas les logiciels.
- Pas de droits administrateur : l'extension tourne dans l'espace utilisateur et ne touche pas aux réglages réseau du système.
- Cohabite avec le VPN de l'entreprise : celui-ci prend en charge les routes du système, tandis que le Proxy Web n'agit qu'au niveau du navigateur ; les deux ne se gênent pas, et les pages de l'intranet continuent de passer par le VPN de l'entreprise.
- Par conception, pas de connexion qui puisse tomber : le proxy fonctionne requête par requête, sans connexion permanente, si bien que vous ne remarquez pas non plus les instabilités du réseau de l'entreprise.

## Configuration en deux étapes

1. Installez l'extension ZeroOmega (la suite de SwitchyOmega) dans le navigateur ; la page Proxy de ce site donne le lien d'installation pour chaque navigateur.
2. Connectez-vous à ce site et, sur la page Proxy, cliquez sur « Copier le lien de restauration de l'extension », puis collez-le dans l'extension sous Import/Export (importer/exporter) → Restore from online (restaurer en ligne). Régions et adresses sont importées d'un coup ; ensuite, cliquez sur l'icône de l'extension, choisissez une région, et saisissez l'identifiant et le mot de passe de votre compte de ce site dans la fenêtre de connexion qu'affiche le navigateur.
3. Nous recommandons un profil de navigateur séparé (ou un autre navigateur) réservé au proxy, le navigateur de travail restant en local, pour ne pas mélanger les deux.

## Ce pour quoi il convient, et quand prendre une autre méthode

- Oui : faire des recherches, ouvrir Google, GitHub, Stack Overflow, les sites de documentation étrangers, la version web de ChatGPT et les messageries web.
- Autre méthode : les applis vidéo, les logiciels de bureau et les outils en ligne de commande n'utilisent pas par défaut les réglages proxy du navigateur (pour la ligne de commande, vous pouvez mettre l'adresse du proxy dans la variable d'environnement http_proxy ; voir l'article sur Linux).
- Autre méthode : regarder les sites vidéo chinois (pour les utilisateurs à l'étranger) ; ces sites vérifient aussi l'IPv6 et le DNS, que le Proxy Web ne couvre pas, et ce cas demande un VPN qui couvre tout l'appareil.

## Rester en bons termes avec la politique informatique

Tout ce qui se passe sur un ordinateur professionnel peut être audité par l'entreprise, extensions comprises. Lisez d'abord la charte d'utilisation : ce que la plupart des entreprises interdisent, ce sont les logiciels non autorisés et le contournement de la politique de sécurité ; une extension de navigateur qui accède à des sites externes se situe en général dans une zone grise. En cas de doute, demandez au service informatique.

N'installez pas de VPN qui couvre tout l'appareil (Cisco, Privé, Hiddify) sur un ordinateur professionnel pour contourner la politique de l'entreprise : ils modifient les routes du système, ce qui déclenche des alertes dans les logiciels de gestion des postes et fait aussi sortir le trafic de l'intranet. Le Proxy Web n'affecte qu'un navigateur et présente le moins de risques.

Séparez comptes professionnels et comptes personnels : ne vous connectez pas aux comptes de l'entreprise dans le navigateur qui utilise le proxy, ni à vos comptes personnels dans le navigateur de l'entreprise.

## FAQ

**Et si l'entreprise interdit d'installer des extensions ?** Utilisez alors votre propre téléphone ou ordinateur personnel. N'utilisez pas de logiciel portable d'origine inconnue pour contourner les restrictions.

**L'extension verra-t-elle le trafic de l'intranet ?** Non. Avec les règles de routage sélectif, les domaines de l'intranet sont en connexion directe et ne passent pas par le proxy ; en mode global, ils sont simplement envoyés au serveur proxy puis reviennent, et le proxy ne voit que le nom de domaine, pas le contenu. Par prudence, donnez au proxy son propre profil de navigateur.

**Le proxy fonctionne-t-il avec le VPN de l'entreprise activé ?** Oui, les deux ne sont pas en conflit. Une petite minorité de VPN d'entreprise forcent tout le trafic par la sortie de l'entreprise et désactivent les réglages proxy ; dans ce cas, l'extension indique qu'elle ne peut pas se connecter, et la seule option est de couper le VPN de l'entreprise.

**Est-ce pareil sur un Mac professionnel ?** Oui ; les extensions pour Chrome, Edge et Firefox existent toutes sur Mac. Safari n'a pas cette extension : utilisez un autre navigateur.

## Pour aller plus loin

- [Page de configuration du proxy : installation de l'extension et lien de restauration](https://www.leotun.com/fr/httpproxy?utm_source=github&utm_content=overseas-access-04)
- [Le Proxy Web : ce que c'est et quand l'utiliser](https://www.leotun.com/fr/guides/web-proxy?utm_source=github&utm_content=overseas-access-04)
- [Faire passer un serveur Linux et les outils en ligne de commande par la ligne](https://www.leotun.com/fr/guides/linux-server?utm_source=github&utm_content=overseas-access-04)
- [Quelle méthode de connexion pour quelle situation](https://www.leotun.com/fr/guides/choose-connection?utm_source=github&utm_content=overseas-access-04)

Version de cet article sur le site : https://www.leotun.com/fr/guides/office-laptop?utm_source=github&utm_content=overseas-access-04

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=overseas-access-04) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=overseas-access-04) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
