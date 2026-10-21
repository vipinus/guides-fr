# 01 · Premiers pas avec un routeur préinstallé

## Trois étapes au déballage

1. **Branchez l'alimentation et le câble réseau** : reliez le port WAN du routeur à votre box ou routeur existant, et attendez que le voyant se stabilise, environ une minute.
2. **Connectez-vous au Wi-Fi** : le nom et le mot de passe Wi-Fi par défaut sont imprimés sur la carte d'instructions (par défaut, les deux sont le nom de domaine du site). Une fois connecté, ouvrez un navigateur et allez à l'adresse d'administration `http://192.168.11.1`.
3. **Connectez votre compte** : sur la page d'administration, saisissez l'e-mail et le mot de passe de votre compte, puis enregistrez (les comptes Personnel, Famille et Entreprise peuvent tous utiliser un routeur). Dès lors, chaque appareil connecté à ce Wi-Fi passe automatiquement par le VPN.

## Changez les mots de passe par défaut

Le mot de passe d'administration et le mot de passe Wi-Fi d'usine sont publics : changez-les dès votre première connexion. Page d'administration → System → Administration (système → administration) ; Wireless → Interfaces → Wireless Security (sans fil → interfaces → sécurité sans fil).

## Le mode routage sélectif

Le mode par défaut est le routage sélectif : les domaines chinois de la liste passent par le VPN, tout le reste est en connexion directe. C'est le mode qui convient le mieux si vous êtes à l'étranger pour regarder des vidéos chinoises, ou si des parents âgés utilisent la télévision. Quand vous êtes en Chine et choisissez une région hors de Chine, le sens s'inverse automatiquement : par défaut, seuls les sites et services bloqués passent par le VPN, tandis que les sites chinois et les sites étrangers qui s'ouvrent déjà normalement depuis la Chine restent en direct ; voir [03 · Ce qu'est le routage sélectif](03-router-split-routing.md). Si vous avez besoin temporairement que tout passe par le VPN, passez en « Global » (tout par la ligne), puis revenez en arrière ensuite.

## FAQ

- **Le voyant est normal mais les appareils connectés n'ont pas Internet** : vérifiez l'état du compte sur la page d'administration ; un compte expiré comme un mot de passe erroné y sont indiqués.
- **Vous voulez passer à un autre routeur** : déliez d'abord l'ancien sur le site ; voir [Liaison par adresse MAC et remplacement du routeur](05-mac-binding-and-replacing.md).

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-01) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-01) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
