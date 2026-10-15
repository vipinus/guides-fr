# 02 · Cisco AnyConnect fonctionne-t-il en Chine ?

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/anyconnect-china?utm_source=github&utm_content=overseas-access-02

Oui. AnyConnect est le protocole VPN d'entreprise de Cisco. Des entreprises du monde entier s'en servent pour le télétravail, et les filiales chinoises des groupes étrangers l'utilisent tous les jours : l'interdire purement et simplement coûterait trop cher. **Ce qui est réellement bloqué, c'est une adresse de serveur précise, pas le protocole.** La question « est-ce que ça marche ? » revient donc à savoir si le fournisseur a assez d'adresses et les remplace assez vite.

## Pourquoi il résiste mieux au blocage que les applis VPN propriétaires

| | AnyConnect | Appli VPN propriétaire |
|---|---|---|
| Signature du trafic | TLS standard, comme la visite d'un site HTTPS | Protocole maison, à la signature fixe |
| Une fois identifié | Seule cette adresse cesse de se connecter | Toute l'appli cesse de fonctionner |
| Client | Publié par Cisco ; l'alternative open source OpenConnect existe sur toutes les plateformes | Disparu dès qu'il est retiré de la boutique d'applis |

LeoTun exploite ses propres machines dans 24 régions. Quand une adresse est repérée, elle est remplacée par une nouvelle, le nom de domaine est redirigé automatiquement, et l'adresse enregistrée dans votre client n'a pas à changer.

## Installation

1. Téléchargez l'installateur pour votre système sur la page Cisco du site. Windows 10 et ultérieur, macOS, iOS, Android et Linux sont tous couverts ; Windows 7/8 ne peut utiliser que la version 4.9, la dernière qui les prend en charge.
2. Ouvrez le client et saisissez l'adresse du serveur dans le champ d'adresse : sur le site, cliquez sur le drapeau d'une région pour la copier.
3. Saisissez votre identifiant et votre mot de passe, puis connectez-vous. Aucun fichier de certificat ni import de configuration n'est nécessaire.
4. Une fois « Connected » (connecté) affiché, vérifiez votre IP de sortie.

## Si la connexion échoue, procédez dans cet ordre

1. **Changez de région.** Si une autre région se connecte, seul ce serveur est temporairement injoignable.
2. **Changez de réseau.** Si le haut débit échoue, passez aux données mobiles, et inversement ; les perturbations ne sont pas synchronisées d'un opérateur à l'autre.
3. **Lisez le message d'erreur.** `Login failed` concerne l'identifiant, le mot de passe ou l'expiration ; `Untrusted server certificate` vient le plus souvent d'une horloge système fausse ou d'un réseau qui intercepte le TLS, donc changez de réseau ; seul `Connection attempt has failed` signifie que l'adresse est injoignable.
4. **Mettez à jour le client.** C'est particulièrement important après une mise à jour majeure du système.
5. **Changez de méthode de connexion.** Le même compte permet d'utiliser OpenVPN ou Hiddify pour se connecter aux mêmes serveurs, et le blocage des trois protocoles est indépendant ; voir [02 · Quelle méthode de connexion pour quelle situation](../network/02-choose-your-connection-method.md).

## Mettre à jour Cisco AnyConnect

Cisco l'a renommé Cisco Secure Client ; il s'utilise de la même façon. Inutile de désinstaller d'abord : installez la nouvelle version par-dessus l'ancienne, et les adresses enregistrées sont conservées. Sur téléphone, mettez à jour dans l'App Store / Google Play ; si la recherche dans la boutique ne le trouve pas, utilisez l'open source OpenConnect, qui emploie le même protocole et le même compte (pour changer la région de la boutique iOS, voir [Client 06](../client/06-ios-app-store.md)).

## FAQ

**Un débit lent est-il le signe d'un bridage ?** Changez d'abord de région : regardez les voyants rouge, jaune et vert dans la liste des régions du site et choisissez-en une au vert. Si c'est toujours lent, la cause habituelle est l'accès Internet local : haut débit partagé de résidence, ou opérateur et région mal assortis (China Unicom dans le nord : Japon ou Corée ; China Telecom dans le sud : Asie du Sud-Est ou Australie ; autres fournisseurs : les points d'entrée en Chine).

**Pourquoi la même adresse est-elle tantôt bonne, tantôt mauvaise ?** L'adresse est un nom de domaine, et les machines derrière sont remplacées automatiquement selon les blocages et la charge. Attendre une minute ou deux avant de réessayer suffit généralement : vous êtes tombé en plein changement.

**Se déconnecte-t-il tout seul après une longue connexion ?** Pas à cause de la durée. Quand le compte expire, le serveur vous déconnecte ; renouvelez et reconnectez-vous.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=overseas-access-02) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=overseas-access-02) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
