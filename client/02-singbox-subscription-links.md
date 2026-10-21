# 02 · Importer un lien d'abonnement (Hiddify, Clash, Shadowrocket)

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/singbox-subscription?utm_source=github&utm_content=client-02

Le « lien d'abonnement » que vous donne un fournisseur de lignes proxy n'est rien d'autre qu'une adresse HTTPS depuis laquelle le client télécharge une configuration complète : serveur, port et identifiants y sont tous, si bien que rien n'est à saisir à la main. La page Hiddify de LeoTun vous fournit la même chose, et directement en trois formats : Hiddify, Clash et Shadowrocket prennent chacun le leur, et rien n'est à convertir.

## Les trois boutons de la fenêtre

Connectez-vous au site → page Hiddify → cliquez sur le drapeau d'une région. Un QR code s'affiche, avec trois boutons en dessous. Les boutons sont regroupés **par type d'abonnement**, pas par système d'exploitation : téléphone et ordinateur affichent donc les mêmes :

| Clients nommés sur le bouton | Sous-titre | Ce que copie le clic |
|---|---|---|
| Hiddify / sing-box / GUI.for.SingBox / Karing | Abonnement sing-box | Sur téléphone, le lien d'import `sing-box://import-remote-profile?url=…`, qui lance l'appli ; sur ordinateur, l'URL de configuration `https://…` simple, à coller. La configuration contient déjà les règles de routage et une règle qui rejette l'IPv6 : inutile de l'envelopper dans un « modèle d'abonnement » |
| Clash Meta / Clash Verge / FlClash / Stash / Mihomo Party / Clash Nyanpasu / ClashX Meta / OpenClash | Abonnement Clash | Une URL d'abonnement au format Clash (YAML), à coller dans la liste d'abonnements / de profils du client |
| NekoBox / Shadowrocket / v2rayN / v2rayNG / Streisand / V2Box / Loon / Egern / Husi / NekoRay / Pharos Pro / Bedlam / Furious / daed / Lumen KVN / Kitty Pro | Lien de partage | Une seule ligne `hysteria2://…`, qui ne contient que le nœud, sans règles de routage |

- Quand les noms ne tiennent pas sur une ligne, ils défilent en boucle ; c'est normal.
- **Un clic sur un bouton fait aussi passer le QR code du dessus à ce type**, pour que le client correspondant puisse le scanner. À l'ouverture de la fenêtre, le QR code est celui de Hiddify / sing-box, et les autres clients qui le scannent directement obtiennent « QR code invalide » : cliquez d'abord sur le bouton de votre client, puis scannez ou collez.
- La fenêtre « Importer toutes les régions · sélection auto » en haut de la page n'a que les deux premiers boutons, sans lien de partage.

**Conversion d'abonnement** : des sites tiers qui convertissent un format en un autre. LeoTun vous donne directement les trois formats : **aucune conversion n'est nécessaire** ; confier à un site de conversion un lien qui contient vos identifiants revient à confier votre compte à un tiers, ne le faites donc pas.

## Famille Hiddify / sing-box : le premier bouton

1. Installez Hiddify (Android : la page de téléchargement du site ou Google Play ; iOS : App Store ; l'appli de bureau couvre Windows / macOS / Linux). Le cœur sing-box est intégré.
2. Cliquez sur le drapeau d'une région, et le QR code s'affiche.
3. Téléphone : touchez le premier bouton et passez à Hiddify, qui proposera de l'ajouter depuis le presse-papiers ; ou utilisez « Scan QR code » (scanner le QR code) dans Hiddify sur un autre appareil. Ordinateur : cliquez sur le même bouton, qui copie une adresse https://, puis dans Hiddify « + » → « Add from clipboard » (ajouter depuis le presse-papiers), et enregistrez.
4. Touchez connecter et autorisez le VPN la première fois. Pour ajouter une région, cliquez sur un autre drapeau ; chaque région est un profil distinct.

## Famille Clash : le deuxième bouton

Pour Clash Meta (mihomo), Clash Verge, FlClash, Stash et consorts, cliquez sur le bouton « Abonnement Clash » et collez l'URL copiée dans la liste d'abonnements / de profils du client. Aucun convertisseur d'abonnement n'est nécessaire.

**Les clients de la famille Clash ne doivent pas utiliser le lien de partage** : ils ne savent pas importer une ligne `hysteria2://` isolée comme profil.

## Autres clients : le troisième bouton

Cliquez sur le bouton « Lien de partage », puis utilisez « Import from clipboard » (importer depuis le presse-papiers) dans NekoBox / Shadowrocket / v2rayN / v2rayNG, etc., ou scannez le QR code du dessus après avoir cliqué sur le bouton. Un lien de partage ne contient aucune règle : vous devez régler vous-même le routage et l'IPv6 ; si vous êtes à l'étranger et voulez regarder des contenus chinois, faites passer les domaines chinois par le nœud et désactivez l'IPv6.

Les clients cités après v2rayN sur le bouton prennent tous en charge hysteria2, mais le lien de partage utilise un format hysteria2 étendu que quelques clients ne savent pas lire ; si l'import échoue ou que la connexion ne passe pas, passez à Hiddify.

## Clients inutilisables

| Client | Pourquoi |
|---|---|
| Surge | Prend en charge hysteria2 mais ne lit que son propre format de configuration : aucun des trois types ne convient |
| Quantumult X | Ne prend pas en charge ce type de ligne |
| Le Clash d'origine, Clash for Windows | Le cœur ne gère pas hysteria2 ; utilisez plutôt un client à cœur mihomo |

## L'abonnement expire-t-il ?

- **Il n'expire pas avec le temps.** Le jeton de l'URL d'abonnement est lié à votre compte et reste valable tant que le compte l'est ; renouveler ou changer de formule n'oblige pas à réimporter.
- **Changer de mot de passe invalide immédiatement l'ancienne URL.** C'est ainsi que vous coupez l'accès en cas de téléphone perdu ou de lien divulgué ; après le changement, scannez de nouveau le code.
- **Une fois le compte expiré**, l'URL renvoie une erreur 401 ; après le renouvellement, inutile de remplacer le profil existant.
- **Les profils importés avant septembre 2026** n'ont pas la règle qui rejette l'IPv6 ; supprimez-les et importez-les de nouveau.

Si vous avez importé mais que la connexion échoue, voir [Dépannage 04](../troubleshooting/04-singbox-import-not-connecting.md).

## FAQ

**Quelle différence entre un abonnement Hiddify et un abonnement Clash ?** Le format diffère (JSON ou YAML), et aucun client ne reconnaît l'abonnement de l'autre, mais les nœuds eux-mêmes fonctionnent avec les deux. LeoTun vous donne directement les deux : les clients de la famille Clash cliquent sur le bouton « Abonnement Clash » et ne doivent pas utiliser le lien de partage.

**Un profil peut-il contenir toutes les régions ?** L'import depuis un drapeau donne un profil par région, et vous passez de l'un à l'autre dans la liste des profils du client ; ainsi, un changement d'adresse dans une région ne touche que celle-ci. Pour importer d'un coup toutes les régions hors de Chine et laisser le client choisir automatiquement, cliquez sur « Importer toutes les régions · sélection auto » en haut de la page (elle n'a que les boutons Abonnement sing-box et Abonnement Clash).

**Puis-je envoyer le QR code à ma famille ?** Le QR code contient les identifiants de votre compte : la personne à qui vous l'envoyez a votre compte. Le partager en famille est permis (appareils simultanés selon la formule : Personnel 2, Famille 4, Entreprise 8), mais ne le publiez nulle part en public ; s'il fuite, changez votre mot de passe et il cessera de fonctionner.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=client-02) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=client-02) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre permanente
