# 01 · Cisco AnyConnect : installer, se connecter et mettre à jour sur toutes les plateformes

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/anyconnect-china?utm_source=github&utm_content=client-01

AnyConnect est le client VPN d'entreprise de Cisco. Il s'appelle désormais officiellement **Cisco Secure Client** et fonctionne de la même façon. Pas besoin de fichier de certificat ni de profil à importer : saisissez l'adresse, votre identifiant et votre mot de passe, et vous pouvez vous connecter. Pour savoir s'il fonctionne en Chine et vers quoi basculer quand il ne se connecte pas, voir [Accéder aux services étrangers depuis la Chine, guide 02](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/02-anyconnect-in-china.md) (en chinois).

## Installation

| Plateforme | Quoi installer | Où le trouver |
|---|---|---|
| Windows 10 et versions ultérieures | Cisco Secure Client 5.x | [La page Cisco du site](https://www.leotun.com/fr/anyconnect?utm_source=github&utm_content=client-01) |
| Windows 7 / 8 | AnyConnect 4.9 (dernière version compatible ; plus mise à jour) | Idem |
| macOS | Cisco Secure Client 5.x | Idem |
| iOS | Cisco Secure Client | App Store ; si la boutique ne le propose pas, installez OpenConnect, client open source qui utilise le même protocole |
| Android | Cisco Secure Client | Google Play, ou l'APK de la page du site |
| Linux | Le fichier d'installation de la page du site, ou openconnect depuis les dépôts de votre distribution | Idem |

Sous Windows, il existe aussi OpenConnect-GUI, open source ; le même compte fonctionne avec lui.

## Se connecter en quatre étapes

1. Ouvrez le client et saisissez l'adresse du serveur dans le champ d'adresse. Les utilisateurs LeoTun peuvent **cliquer sur le drapeau d'une région** sur le site pour copier l'adresse de cette région.
2. Saisissez votre identifiant (l'e-mail utilisé à l'inscription) et votre mot de passe.
3. Quand « Connected » (connecté) s'affiche, ouvrez une page web qui indique votre IP pour vérifier que votre sortie est bien dans la région choisie.
4. Pour changer de région, utilisez une autre adresse. Le client mémorise les adresses déjà utilisées : la prochaine fois, choisissez-en une dans la liste déroulante.

## Mise à jour

Inutile de désinstaller d'abord : installez la nouvelle version par-dessus l'ancienne, vos adresses enregistrées sont conservées. Sur téléphone, mettez à jour depuis la boutique d'apps. Après une mise à jour majeure du système d'exploitation, mettez d'abord le client à jour, et seulement ensuite cherchez la cause d'éventuels problèmes de connexion.

## Messages courants

| Message | Signification |
|---|---|
| Login failed | Identifiant ou mot de passe erroné, ou compte expiré |
| Untrusted server certificate | Le plus souvent, l'horloge du système est fausse, ou le réseau actuel intercepte les connexions chiffrées ; essayez un autre réseau |
| Connection attempt has failed | Cette adresse est momentanément injoignable ; changez de région |

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-01) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-01) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
