# 03 · Ce qu'est le routage sélectif sur le routeur

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/router-firmware?utm_source=github&utm_content=router-03

## En une phrase

Configurez le VPN sur le routeur, et chaque appareil de la maison passe automatiquement par lui dès qu'il est connecté au Wi-Fi. Les appareils incapables d'installer un client, comme les box TV, les consoles de jeu et les imprimantes, en profitent aussi.

## Le problème que résout le routage sélectif

Si tout le trafic passe par le VPN, vous rencontrez deux problèmes : les sites locaux deviennent lents (ils font un détour), et les appareils locaux deviennent injoignables (imprimantes, NAS et page d'administration du routeur sont sur le réseau local, mais le trafic a été envoyé à l'extérieur).

Le routage sélectif consiste à donner une liste au routeur : les domaines de la liste passent par le VPN, tout le reste se connecte directement. Le sens dépend de l'endroit où vous êtes et du côté que vous voulez joindre, et il est déterminé automatiquement par la région choisie :

- **À l'étranger, région Chine choisie (accéder à la Chine)** : les sites et applis chinois passent par le VPN, tout le reste se connecte directement.
- **En Chine, région hors de Chine choisie (accéder aux services étrangers)** : par défaut, seuls les sites et services bloqués passent par le VPN ; les sites chinois, et les sites étrangers qui s'ouvrent de toute façon depuis la Chine (sites d'entreprises étrangères, téléchargements Apple et Microsoft, plateformes de jeu, etc.), se connectent directement sans détour, aussi vite que sans le routeur.

## Trois modes

| Mode | Où va le trafic | Quand l'utiliser |
|---|---|---|
| Global (tout par la ligne) | Tout passe par le VPN | Temporairement, pour un dépannage |
| Split routing (routage sélectif) | Les domaines de la liste passent par le VPN, le reste se connecte directement | Au quotidien |
| Direct (sans la ligne) | Rien ne passe par le VPN | Quand vous n'en avez pas besoin pendant un moment |

## Accéder aux services étrangers depuis la Chine : sites bloqués uniquement

Depuis le 14 octobre 2026, dans le sens « accéder aux services étrangers depuis la Chine », le routage sélectif ne fait passer par défaut par le VPN que les sites et services bloqués. Il s'appuie sur une liste de sites bloqués mise à jour automatiquement chaque jour, plus des services comme Telegram qui se connectent à des adresses fixes sans chercher de nom de site. Les sites qui s'ouvrent de toute façon depuis la Chine, chinois ou étrangers, se connectent directement.

Le réglage se trouve dans la page d'administration du routeur, sous « VPN settings » (réglages VPN), partie routage sélectif intelligent : la case « Blocked sites only » (sites bloqués uniquement), cochée par défaut. Décochez-la pour revenir à l'ancien comportement : sites chinois en direct, tout le reste par le VPN.

Les firmwares flashés avant octobre 2026 n'affichent pas encore cette case ; le nouveau comportement par défaut s'applique déjà à ces routeurs via les mises à jour automatiques. Pour le modifier, contactez le service client, qui peut le faire à distance.

Le sens « accéder à la Chine depuis l'étranger » ne change pas.

## Pièges

- **Un site ne s'ouvre pas en routage sélectif** : vérifiez d'abord s'il est dans la liste. Les sites hors liste se connectent directement, et si ce site ne s'ouvrait déjà pas au départ, le routage sélectif n'y changera rien. Passez temporairement en « Global » pour vérifier.
- **En Chine, un site étranger ne s'ouvre pas** : décochez « Blocked sites only » dans la partie routage sélectif intelligent (ou passez temporairement en « Global ») et réessayez. S'il s'ouvre alors, le site est bloqué mais pas encore dans la liste ; envoyez l'adresse au service client.
- **Les sites bloqués ne s'ouvrent pas, mais tout le reste fonctionne** : l'appareil a très probablement activé un DNS chiffré (« DNS privé » sur Android, « DNS sécurisé » dans le navigateur), si bien que le routeur ne voit pas quel site est recherché. Désactivez ce réglage.
- **L'imprimante ou le NAS est injoignable après la connexion** : cela signifie que les adresses du réseau local sont aussi envoyées à l'extérieur. Vérifiez que les règles de routage sélectif excluent les plages privées comme 192.168.x.x.
- **Les performances du routeur** fixent le plafond. Le processeur d'un vieux routeur sature sur le trafic chiffré, ce qui se traduit par un ralentissement de tout le foyer. Dans ce cas, la ligne VPN n'y est pour rien.

## Un compte, un routeur

La plupart des services lient le routeur au compte (par adresse MAC). Un compte est lié à un seul routeur, et il faut le délier avant de changer de routeur. Ainsi, le compte reste à vous seul.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-03) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-03) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
