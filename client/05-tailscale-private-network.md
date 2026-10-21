# 05 · Privé (Tailscale) : installer, se connecter au serveur de contrôle de ce site, choisir une sortie

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/tailscale-mesh?utm_source=github&utm_content=client-05

La rubrique Privé utilise Tailscale (un outil de mise en réseau bâti sur WireGuard). LeoTun exploite son propre serveur de contrôle, et vous vous connectez avec **votre compte de ce site**, qui n'a rien à voir avec un compte Tailscale officiel. Connectez-vous une fois et vous restez en ligne ; la région de sortie se change à tout moment depuis le menu. Pour la différence avec un VPN et à qui cela convient, voir le [Guide réseau 03](../network/03-private-network-vs-vpn.md).

## Installation

| Plateforme | Où l'obtenir |
|---|---|
| Windows / macOS / Linux / Android | La zone de téléchargement de [la page Privé du site](https://www.leotun.com/fr/mesh?utm_source=github&utm_content=client-05) (servie directement par ce site, inutile de passer par le site officiel) |
| iPhone / iPad | App Store ; exige un identifiant Apple d'une région autre que la Chine (voir [Clients 06](06-ios-app-store.md)) |

## Connexion

1. **Déconnectez-vous d'abord du compte officiel** (si vous vous y êtes déjà connecté) : sur téléphone, touchez votre avatar → Log Out ; sur ordinateur, exécutez `tailscale logout`. Tant que vous n'êtes pas complètement déconnecté, l'option nécessaire à l'étape suivante n'apparaît pas.
2. **Faites pointer la connexion vers ce site** :
   - Téléphone : sur l'écran déconnecté, touchez « ⋯ » en haut à droite → Use custom server (Use an alternate server selon les versions ; utiliser un serveur personnalisé), saisissez l'adresse indiquée sur la page Privé du site, puis touchez Log in.
   - Windows / Linux : copiez la commande `tailscale up --login-server=…` depuis la page du site et exécutez-la dans PowerShell / un terminal.
   - macOS : **ne cliquez pas sur Log in**. Dans la fenêtre Tailscale, cliquez sur la flèche de la ligne du compte → Account Settings… → Accounts → la petite flèche à côté de « Add Account… » → Add Account Using Alternate Server, collez l'adresse et cliquez sur Add Account….
3. Le navigateur ouvre automatiquement la page de connexion de ce site ; confirmez avec votre compte de ce site. De retour dans le client, l'appareil est déjà en ligne.

## Choisir une sortie

- Téléphone : menu → Exit Node (nœud de sortie), choisissez une région ; c'est immédiat.
- Ordinateur : icône de la barre des tâches / de la barre des menus → sous-menu Exit Node ; ou `tailscale set --exit-node=<region-name>` (`tailscale exit-node list` affiche ce qui est disponible).
- Pour ne pas utiliser de sortie, choisissez None (aucune ; en ligne de commande, laissez vide la valeur après le signe égal). Une seule sortie à la fois.

## Expiration et nombre d'appareils

- La validité de la connexion d'un appareil suit la date d'expiration du compte, et il passe hors ligne quelques minutes après l'expiration ; après le renouvellement, il suffit de se reconnecter une fois. Aucune réinstallation nécessaire.
- Le nombre d'appareils en ligne en même temps dépend de votre formule (Personnel 2, Famille 4, Entreprise 8), et le quota est commun aux autres méthodes d'accès ; si vous dépassez la limite de votre formule, vous pouvez passer temporairement à une formule supérieure (le temps restant est converti à valeur égale selon le prix) et revenir en arrière ensuite.

## Deux cas où une autre méthode convient mieux

- Un autre VPN tourne sur le même appareil (AnyConnect de l'entreprise, autre logiciel de réseau maillé) : ils se disputent le DNS et les routes. C'est ce qui explique les messages de restriction de droits sur les vidéos chinoises et les intranets d'entreprise qui ne s'ouvrent plus.
- Sur un réseau de campus / d'entreprise qui restreint l'UDP : WireGuard passe par l'UDP et ne peut alors que passer par des relais, ce qui est très lent ; passez à AnyConnect.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-05) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-05) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
