# 09 · Comment fonctionne le routage sélectif du routeur

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/router-smart-split?utm_source=github&utm_content=router-09

Tous s'appellent « routage sélectif intelligent », et pourtant certains routeurs sont pénibles à l'usage. Pour ce qu'est le routage sélectif, voir [03](03-router-split-routing.md) ; cet article ne traite que de ce que le routage sélectif doit faire, des symptômes quand une partie manque, et de la façon dont notre routeur s'y prend.

## En une phrase

Ce que doit faire le routage sélectif : chaque site, **avec ses images, ses vidéos et sa connexion au compte**, passe par le VPN ou reste en direct selon l'endroit où il se trouve, et **tous les appareils de la maison suivent les mêmes règles**. Quand une partie seulement est faite, vous voyez les symptômes ci-dessous.

## Symptômes comparés

| Ce que vous voyez | Ce qui se passe en coulisse |
|---|---|
| Une fois le routage sélectif activé, les sites chinois deviennent au contraire plus lents | Les sites chinois sont pris pour des sites étrangers et font tout un aller-retour à l'étranger |
| La page web s'ouvre, mais la vidéo tourne sans fin, les images n'apparaissent pas et la connexion au compte reste bloquée | La liste ne contient que le site principal, et la vidéo, les images et la connexion du même site prennent un autre chemin |
| Vous êtes à l'étranger avec la ligne vers la Chine activée, et l'appli vidéo affiche toujours « 仅限中国大陆 » (Chine continentale uniquement) | Une partie du trafic n'est pas entrée dans le VPN, et le site a vu une adresse étrangère |
| Ça se lit sur le téléphone mais pas sur le téléviseur ou la box TV ; un ordinateur refuse obstinément de passer par le VPN | Cet appareil a ses propres réglages réseau et contourne le routeur |
| Les applis bancaires et de paiement signalent de temps en temps une « connexion depuis un autre lieu » | Le trafic d'une même appli sort tantôt en Chine, tantôt à l'étranger |
| Le routage sélectif disparaît en cours d'utilisation (après un redémarrage ou une reconnexion, soit tout passe par le VPN, soit rien) | Le réglage n'a pas été mémorisé |

Aucun de ces cas **ne produit d'erreur**. Le routeur affiche « Connecté » tout du long, ce qui les rend les plus difficiles à diagnostiquer, et beaucoup finissent par croire que la ligne est mauvaise.

## Ce que doit faire le routage sélectif

- Un site suit un seul chemin avec ses pages, ses images, ses vidéos et sa connexion au compte, sans être découpé
- Pour décider « chinois ou étranger », il se place du bon côté, et les sites chinois ne font aucun détour
- Tous les appareils de la maison suivent les mêmes règles, et des réglages réseau modifiés sur l'appareil lui-même ne permettent pas de les contourner
- Le sens change automatiquement avec la région choisie (accéder à la Chine depuis l'étranger et accéder aux services étrangers depuis la Chine sont deux jeux de règles opposés)
- La liste se met à jour toute seule, sans reflasher
- Les réglages sont mémorisés : inchangés après un redémarrage ou une reconnexion ; et une fois désactivé, il n'est pas réactivé en douce

## Le routage sélectif intelligent de notre routeur

| | Comment c'est fait |
|---|---|
| Activation | Activé par défaut ; choisir une région en Chine = le sens « accéder à la Chine depuis l'étranger », choisir une région hors de Chine = le sens « accéder aux services étrangers depuis la Chine », appliqué automatiquement. Le sens « services étrangers depuis la Chine » a en plus une case « Blocked sites only » (sites bloqués uniquement) dans « VPN settings » (réglages VPN) → routage sélectif intelligent, cochée par défaut ; décochée = sites chinois en direct, tout le reste par le VPN. Les firmwares flashés avant octobre 2026 n'affichent pas encore cette case ; contactez le service client pour la faire modifier à distance |
| Liste | Organisée par « site entier » : les pages vont avec les sources de vidéo, d'images et de connexion qu'elles utilisent |
| Accéder aux services étrangers depuis la Chine | Par défaut, seuls les sites et services bloqués passent par le VPN (d'après une liste de sites bloqués mise à jour automatiquement chaque jour, plus des services comme Telegram qui se connectent à des adresses fixes) ; les sites chinois, et les sites étrangers qui s'ouvrent déjà normalement depuis la Chine (sites d'entreprises étrangères, téléchargements Apple et Microsoft, plateformes de jeu), restent en direct sans détour, à la même vitesse que sans le routeur |
| Appareils de la maison | Pris en charge uniformément ; des réglages réseau modifiés sur l'appareil lui-même suivent quand même les règles ; il n'y a pas de « porte dérobée » pour contourner le routeur |
| Mises à jour | La liste et les règles se mettent à jour automatiquement au démarrage du routeur ; la liste des sites bloqués se met aussi à jour automatiquement chaque jour |
| Mémorisation | Conservé après une reconnexion ou un redémarrage ; une fois désactivé, il le reste |
| Réseau local | Imprimantes, NAS et caméras restent joignables directement, comme d'habitude |

**Le seul cas où il faut votre aide** : quand un téléphone ou un navigateur a activé un réglage chiffré comme « DNS privé » ou « DNS sécurisé », l'appareil chiffre lui-même ses requêtes et le routeur ne les voit pas. Si un appareil se comporte mal, ou si les sites bloqués ne s'ouvrent pas alors que tout le reste fonctionne, désactivez d'abord ce type de réglage.

## Vérifiez par vous-même

1. Vous êtes en Chine (accès aux services étrangers) : Baidu et Taobao, ainsi que les sites étrangers qui s'ouvrent déjà normalement depuis la Chine, comme les téléchargements Apple et Microsoft, vont à vitesse normale ; les sites étrangers bloqués s'ouvrent et les vidéos se lisent.
2. Vous êtes à l'étranger (accès à la Chine) : choisissez n'importe quel épisode sur Tencent Video ou iQIYI, il se lit, sans message « 仅限中国大陆 » (Chine continentale uniquement) ; les sites locaux de banque et d'achats fonctionnent comme d'habitude.
3. Essayez chaque appareil, en particulier le téléviseur et la box TV ; pour celui qui se comporte mal, vérifiez d'abord « DNS privé / DNS sécurisé », puis assurez-vous qu'il est bien connecté au Wi‑Fi de ce routeur et non à celui de la box.
4. Un site ne s'ouvre pas en routage sélectif : passez temporairement en « Global ». S'il s'ouvre en Global mais pas en routage sélectif, il n'est pas encore dans la liste ; envoyez l'adresse au service client pour qu'il l'ajoute, et elle arrivera avec la mise à jour automatique. En Chine, vous pouvez aussi décocher « Blocked sites only » dans la partie routage sélectif intelligent et réessayer ; s'il s'ouvre alors, il est lui aussi bloqué mais pas encore dans la liste.

## FAQ

**Dois-je activer moi-même le routage sélectif intelligent ?** Non. Il est actif dès que vous avez connecté votre compte et choisi une région.

**Faut-il configurer séparément l'accès à la Chine depuis l'étranger et l'accès aux services étrangers depuis la Chine ?** Non. Le sens est déterminé automatiquement par la région choisie.

**Cela affecte-t-il les imprimantes ou le NAS ?** Non. Les appareils du réseau de la maison restent joignables directement, comme d'habitude.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-09) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-09) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
