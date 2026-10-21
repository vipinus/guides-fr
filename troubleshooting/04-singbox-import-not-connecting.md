# 04 · Hiddify importé mais impossible de se connecter

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/singbox-subscription?utm_source=github&utm_content=troubleshooting-04

Retrouvez votre erreur dans le tableau. Pour l'import lui-même, voir [Importer un lien d'abonnement (Hiddify, Clash, Shadowrocket)](../client/02-singbox-subscription-links.md).

| Symptôme | Cause | Que faire |
|---|---|---|
| « Unable to fetch subscription » (impossible de récupérer l'abonnement), 401 | Le compte a expiré, ou le mot de passe a été changé (changer de mot de passe invalide aussitôt les anciennes configurations ; c'est voulu) | Connectez-vous au site et vérifiez la période de validité ; après un renouvellement ou un changement de mot de passe, scannez à nouveau le QR code |
| L'import réussit, la connexion expire | L'adresse de cette région vient de changer, ou ce point d'entrée est perturbé par l'opérateur | Touchez « Update subscription » (mettre à jour l'abonnement) dans le client pour récupérer la dernière configuration ; passez à une autre région : chaque région est une configuration distincte, indépendante des autres |
| Connecté mais pas d'Internet | Les règles de routage du client envoient le trafic en « direct » | Remettez la sortie par défaut sur ce nœud, ou supprimez les règles que vous avez ajoutées vous-même |
| Le scan indique « Invalid QR code » (QR code invalide) | À l'ouverture de la fenêtre, le QR code affiché est celui de Hiddify / sing-box, et les autres clients qui le scannent directement obtiennent cette erreur ; ou bien il a été scanné depuis la capture d'écran de quelqu'un d'autre | Cliquez d'abord sur le bouton de votre client, qui bascule le QR code vers le bon type, puis scannez ou collez : les clients de la famille Clash cliquent sur « Abonnement Clash » ; Shadowrocket / NekoBox / v2rayN, etc. cliquent sur « Lien de partage ». Le QR code contient vos propres identifiants, celui de quelqu'un d'autre ne fonctionnera pas |
| Débit lent | La région choisie est très chargée, ou votre connexion locale et la région ne vont pas bien ensemble | Regardez les voyants rouge, orange et vert dans la liste des régions du site et passez à une région au voyant vert ; si c'est encore lent, changez de région selon votre opérateur |
| Un client de la famille Clash n'arrive pas à importer le lien de partage | Clash Meta, Clash Verge, FlClash, Stash et consorts ne savent pas importer une simple ligne hysteria2:// comme profil | Cliquez sur le bouton « Abonnement Clash » et collez l'URL dans la liste d'abonnements du client ; le Clash d'origine et Clash for Windows n'ont pas hysteria2 dans leur moteur : utilisez plutôt un client à moteur mihomo |
| Le lien de partage ne s'importe pas ou ne se connecte pas | Le lien de partage utilise un format étendu que quelques clients ne savent pas lire | Passez à Hiddify |

## Faut-il réimporter après un renouvellement, un changement de formule ou de mot de passe

- **Renouvellement ou changement de formule (Personnel / Famille / Entreprise)** : non. La configuration existante continue de fonctionner.
- **Changement de mot de passe** : l'ancienne configuration cesse aussitôt de fonctionner ; scannez à nouveau le QR code. Si vous perdez votre téléphone ou si le lien a fuité, c'est ainsi que vous révoquez l'accès.
- **Compte expiré** : la configuration renvoie 401. Après le renouvellement, pas besoin de nouvelle configuration : reconnectez-vous simplement.
- **Importé avant septembre 2026** : la règle qui rejette l'IPv6 manque, si bien que regarder des vidéos chinoises depuis l'étranger affiche un message de restriction de droits. Supprimez et réimportez ; voir [03](03-ipv6-and-dns-leak.md).

## Quand contacter l'assistance

Indiquez trois choses à l'assistance : le nom et la version du client, la région, et le texte exact de l'erreur ou une capture d'écran.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=troubleshooting-04) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-04) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
