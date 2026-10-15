# 08 · Vérifier que vous êtes vraiment connecté, et par quelle région vous sortez

Le client qui affiche « Connecté » ne signifie pas que les sites que vous visitez voient l'adresse du VPN. Le plus simple pour vérifier se trouve dans la barre du haut de ce site : le champ « Réseau actuel » montre **vous, tel que ce site vous voit à cet instant** : le pays, la province ou l'État, et le réseau par lequel vous sortez. Cet article explique comment lire ce champ, comment comparer avant et après la connexion, comment savoir si chacune des six méthodes de connexion est connectée, ce que signifient les voyants rouge, jaune et vert de la liste des régions, et ce que vous pouvez vérifier vous-même quand vous êtes « connecté mais toujours affiché en local ».

## Ce qu'affiche « Réseau actuel » dans la barre du haut

| Position | Contenu |
|---|---|
| Au début | Le drapeau du pays de sortie ; remplacé par une icône Wi‑Fi quand le pays ne peut pas être identifié |
| Au milieu | Le nom de la province ou de l'État, dans la langue de l'interface (les États-Unis, le Canada, l'Australie, etc. utilisent les abréviations courantes comme CA, ON, NSW) ; Hong Kong, Macao et Singapour affichent directement le nom de la région |
| À la fin | Le nom du réseau : les trois grands opérateurs chinois, le réseau éducatif, etc. apparaissent dans l'interface chinoise sous des noms courts comme 电信 (China Telecom), 移动 (China Mobile), 联通 (China Unicom) et 教育网 (réseau éducatif) ; les autres affichent leur marque en anglais (par ex. Comcast, Bell) |

- **Quand la province ou l'État est introuvable, seul « drapeau · nom du réseau » s'affiche.** Le nom du pays ne sert pas de bouche-trou : le drapeau vous indique le pays.
- Sur ordinateur, survolez ce champ avec la souris : il affiche le nom complet de l'organisation, la province ou l'État, le code pays et l'**IP de sortie**. Cette IP n'est montrée qu'à vous, et c'est l'information la plus utile quand vous contactez l'assistance.
- Chrome / Edge sous Windows n'ont pas de police pour les drapeaux : le drapeau apparaît sous forme de deux lettres (par ex. JP, US). Le sens est le même.
- Sur ordinateur, il n'apparaît dans la barre du haut qu'une fois connecté au compte ; sur téléphone, il s'affiche sans connexion.

## Comparez avant et après la connexion pour trancher d'un coup d'œil

1. **VPN désactivé**, ouvrez ce site et regardez : vous devriez voir l'opérateur de votre connexion à la maison ou de vos données mobiles, et le drapeau du pays où vous êtes.
2. **Connectez le VPN** et revenez au navigateur : le drapeau passe à la région choisie, et le nom du réseau devient en général celui d'un centre de données ou d'un hébergeur cloud plutôt que celui de votre opérateur.
3. Si les deux sont identiques, ce navigateur ne passe pas par le VPN pour visiter ce site. Voir « Connecté, mais toujours affiché en local » plus bas.

**Inutile de rafraîchir la page sans arrêt.** Ce champ revérifie automatiquement quand vous revenez sur la fenêtre du navigateur, vérifie encore quelques fois dans les secondes qui suivent un changement de réseau, et se met aussi à jour toutes les dix à vingt secondes tant que la page est ouverte. Si vous voyez encore l'ancienne valeur juste après la connexion, attendez dix à vingt secondes ou changez de fenêtre ; si rien ne change, rafraîchissez manuellement.

**Quand vous êtes en Chine et avez choisi un « point d'entrée en Chine »**, il est normal que la barre du haut affiche un pays étranger : les points d'entrée en Chine font du routage sélectif, si bien que les sites chinois sortent depuis la Chine et que les sites étrangers ressortent par la route internationale. Ce site étant à l'étranger, c'est naturellement le côté étranger qui s'affiche.

## Comment savoir si chaque méthode de connexion est connectée

| Méthode | Ce qu'il faut regarder dans le client | La barre du haut de ce site change-t-elle ? |
|---|---|---|
| Cisco (AnyConnect) | Le client affiche « Connected » (connecté) | Oui. Une fois Cisco connecté, tout le trafic passe par le VPN |
| Hiddify | Le client affiche connecté | Elle change en mode global ; en « routage automatique », cela dépend de la liste |
| OpenVPN | Le client affiche connecté | Oui. Par défaut, tout le trafic passe par le VPN |
| Privé (Tailscale) | Le client est en ligne, **et** une région est choisie comme Exit Node (nœud de sortie) | Elle ne change que si une sortie est choisie ; avec None (aucune), les appareils peuvent seulement se joindre entre eux et le trafic ne passe pas par le VPN |
| Proxy Web | Il n'y a pas d'état « connecté » ; regardez quel mode de région est choisi dans l'icône de l'extension | Seul le navigateur où l'extension est installée change ; les règles de « auto switch » (bascule automatique) peuvent faire passer ce site en direct |
| Routeur | Dans la page d'administration, l'état du compte est normal et la date d'expiration s'affiche | Regardez depuis un appareil connecté au Wi‑Fi de ce routeur ; en mode routage sélectif, cela dépend de la liste |

Le routage sélectif signifie que les sites de la liste passent par le VPN et que tout le reste va en direct. Si la barre du haut affiche votre réseau local alors que le routage sélectif est actif, cela ne veut pas forcément dire que vous n'êtes pas connecté : **passez temporairement en « global » et regardez de nouveau**. Si cela change, le VPN fonctionne et ce site n'est simplement pas dans la liste.

## Les voyants rouge, jaune et vert de la liste des régions

Sur les pages Cisco, Hiddify, Proxy et OpenVPN, un petit voyant se trouve sous le drapeau de chaque région, et le même voyant apparaît devant les noms des sorties dans le client Privé. Il est calculé automatiquement d'après la bande passante moyenne en temps réel de chaque serveur de la région, et se met à jour environ une fois par minute :

| Voyant | Signification |
|---|---|
| Vert (fixe) | Libre |
| Jaune (clignotant) | En utilisation |
| Rouge (clignotant) | Chargé |
| Pas de voyant | Aucune donnée obtenue pour le moment ; cela ne veut pas dire que le serveur est en panne |

Sur ordinateur, survolez le voyant avec la souris pour voir la charge moyenne de la région.

**Que faire quand vous voyez un voyant rouge :**

- Rouge ne veut pas dire en panne ; cela signifie seulement qu'il y a beaucoup de monde à ce moment. Si vous êtes déjà connecté et que le débit vous suffit, n'y touchez pas.
- Si cela vous semble lent, passez à une région au vert. Pour Cisco, cliquez sur un autre drapeau sur la page web pour copier la nouvelle adresse ; pour Hiddify, importez la configuration d'une autre région ; pour Privé, changez-la dans Exit Node ; pour le proxy web, cliquez sur une autre région dans l'icône de l'extension.
- Derrière chaque région se trouvent plusieurs machines, et la moins chargée est choisie automatiquement à la connexion. Inutile de choisir une machine vous-même.
- De 20 h à 23 h, c'est l'heure de pointe. Pendant cette période, choisissez une région au vert ou changez de méthode de connexion ; si c'est toujours lent, la cause habituelle est l'accès Internet local (haut débit partagé de résidence, ou opérateur et région mal assortis). Pour choisir une région selon l'opérateur, voir « Pour aller plus loin ».

## Connecté, mais toujours affiché en local

Par ordre de fréquence :

1. **Les règles de routage font passer ce site en direct.** Le routage automatique de Hiddify, l'« auto switch » de l'extension de proxy web et le mode routage sélectif du routeur peuvent tous laisser ce site hors du VPN. Passez temporairement en global pour vérifier ; les utilisateurs du proxy web peuvent aussi ajouter ce site aux règles.
2. **Le proxy web ne couvre que ce navigateur-là.** Depuis un autre navigateur ou une appli de téléphone, vous verrez évidemment toujours votre réseau local.
3. **Pas de sortie choisie dans Privé.** En ligne ≠ passer par le VPN ; quand Exit Node est sur None, les appareils peuvent seulement se joindre entre eux.
4. **Vous regardez depuis le mauvais appareil.** Pour la solution Routeur, regardez depuis un appareil connecté au Wi‑Fi de ce routeur, pas depuis un téléphone connecté au Wi‑Fi de la box ou en données mobiles.
5. **Un autre VPN ou outil de réseau maillé est actif en même temps.** Un VPN d'entreprise ou l'accélérateur d'un autre fournisseur se disputeront les routes. N'en gardez qu'un.
6. **Ce n'est pas encore rafraîchi.** Attendez dix à vingt secondes, changez de fenêtre, ou rafraîchissez une fois manuellement.

## La barre du haut vérifie l'IP ; vérifiez l'IPv6 et le DNS à part

La barre du haut regarde l'adresse IPv4 de la connexion reçue par ce site. Si elle affiche ce qu'il faut, cela signifie seulement que ce navigateur est passé par le VPN pour visiter ce site :

- **L'IPv6 et le DNS n'y sont pas visibles.** Quand le navigateur visite ce site en IPv6, le champ ne s'affiche tout simplement pas ; il ne fera pas passer un mauvais réseau pour le bon. Si un site vidéo affiche toujours une restriction de droits, l'IPv6 ou le DNS contourne très probablement le VPN ; voir [03 · IPv6 et DNS passent à côté](03-ipv6-and-dns-leak.md).
- **Les applis gardent en cache leur contrôle de région.** La barre du haut est recalculée à chaque fois et n'est pas affectée par le cache ; mais les applis de vidéo et de musique retiennent la région précédente. Quittez-les complètement et rouvrez-les ; voir [02 · Connecté pour accéder à la Chine mais toujours impossible de regarder](02-still-blocked-after-connecting.md).

## FAQ

**Le champ « Réseau actuel » de la barre du haut a disparu ?** Sur ordinateur, connectez-vous d'abord au compte. S'il ne s'affiche toujours pas après la connexion, cette connexion est très probablement passée par l'IPv6 ou ne peut pas être identifiée pour le moment ; attendez dix à vingt secondes ou rafraîchissez. Il préfère ne rien afficher plutôt qu'afficher quelque chose de faux.

**Même région, mais une IP différente à deux connexions ?** C'est normal. Derrière une région se trouvent plusieurs machines, et chaque connexion prend la moins chargée à ce moment. Une connexion établie n'est pas déplacée en cours de route.

**La province affichée n'est pas celle que j'attendais ?** La barre du haut affiche la province ou l'État où se trouve l'IP de sortie, et n'est précise qu'à ce niveau. Si le drapeau correspond, la sortie est bien dans le pays ou la région choisis.

**Que signaler en contactant l'assistance ?** Survolez ce champ de la barre du haut avec la souris et envoyez ce qui s'affiche (IP de sortie comprise), avec la méthode de connexion, la région choisie et l'heure du problème.

## Pour aller plus loin

- [Dépanner une connexion impossible, lente ou qui coupe](https://www.leotun.com/fr/guides/connect-issues?utm_source=github&utm_content=troubleshooting-08)
- [Quelle région est la plus rapide depuis la Chine](https://www.leotun.com/fr/guides/pick-region?utm_source=github&utm_content=troubleshooting-08)
- [Quelle méthode de connexion pour quelle situation](https://www.leotun.com/fr/guides/choose-connection?utm_source=github&utm_content=troubleshooting-08)
- [Ce qu'est le proxy web et quand l'utiliser](https://www.leotun.com/fr/guides/web-proxy?utm_source=github&utm_content=troubleshooting-08)
- [Ce que peut faire le firmware du routeur](https://www.leotun.com/fr/guides/router-firmware?utm_source=github&utm_content=troubleshooting-08)
- [Que faire quand Tencent Video affiche une restriction de droits à l'étranger](https://www.leotun.com/fr/guides/overseas-video?utm_source=github&utm_content=troubleshooting-08)

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=troubleshooting-08) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-08) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
