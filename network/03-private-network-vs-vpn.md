# 03 · Ce qui distingue Privé (Tailscale) d'un VPN, et quand l'utiliser

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/tailscale-mesh?utm_source=github&utm_content=network-03

La rubrique Privé repose sur Tailscale, un outil de mise en réseau construit sur WireGuard. LeoTun fait tourner lui-même le serveur de contrôle, et vous vous connectez avec votre compte de ce site. Ce n'est pas la même chose que les VPN « à connexion » comme AnyConnect et OpenVPN.

## Trois différences

| | VPN à connexion (AnyConnect / OpenVPN / Hiddify) | Privé (Tailscale) |
|---|---|---|
| Connexion | Vous touchez « Connecter » à chaque fois, et vous reconnectez après une coupure | Une seule connexion, puis l'appareil reste en ligne ; il se rétablit tout seul quand vous changez de réseau |
| Sortie | Une fois connecté, tout le trafic passe par la sortie | La sortie est facultative : sans sortie choisie, le trafic vers Internet part en local et seul le trafic entre les appareils du réseau privé est chiffré ; ce n'est qu'en choisissant la sortie d'une région que cela équivaut à un VPN |
| Accès entre appareils | Aucun | Les téléphones, ordinateurs et NAS d'un même compte se joignent directement, sans redirection de ports ni IP publique |

## Quand l'utiliser

- Vous avez plusieurs appareils et voulez les configurer une fois, puis qu'ils restent en ligne pour de bon.
- Vous avez à la maison un NAS, un ordinateur ou une caméra à joindre de l'extérieur : connectez les deux côtés à Privé et accédez-y directement par le nom de l'appareil, comme sur le même réseau local.
- Les appareils qui doivent rester connectés longtemps : il n'y a pas d'expiration de session.

## Quand une autre méthode convient mieux

- Vous n'en avez besoin qu'une fois, ponctuellement : importer Hiddify par QR code ou installer AnyConnect est plus rapide.
- L'appareil fait déjà tourner un VPN d'entreprise ou un autre logiciel réseau : les deux se disputent le DNS et les routes, avec pour symptômes des restrictions de droits sur les vidéos chinoises et l'intranet de l'entreprise qui ne s'ouvre plus. Prenez une méthode qui ne touche que le navigateur, comme le Proxy Web.
- Réseaux de campus ou d'entreprise qui restreignent l'UDP : WireGuard passe par l'UDP et doit alors se rabattre sur des relais, qui sont lents ; passez à AnyConnect.

## Expiration et nombre d'appareils

La validité de connexion d'un appareil suit la date d'expiration du compte ; il passe hors ligne quelques minutes après l'expiration, et il suffit de se reconnecter après le renouvellement. Le nombre d'appareils en ligne en même temps dépend de la formule (Personnel 2, Famille 4, Entreprise 8), avec un quota commun aux autres méthodes de connexion ; si vous dépassez la limite de votre formule, vous pouvez passer temporairement à une formule supérieure (le temps restant est converti à valeur égale selon le prix) et revenir en arrière ensuite.

Pour l'installation et la connexion, voir le [guide client 05](../client/05-tailscale-private-network.md).

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=network-03) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=network-03) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; chaque ami invité qui paie vous rapporte à tous les deux 15 points (environ 15 jours en formule Personnel), une offre sans date de fin
