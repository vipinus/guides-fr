# 07 · Voir depuis l'étranger vos caméras installées en Chine

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/home-camera?utm_source=github&utm_content=china-access-07

## Trois cas, trois solutions différentes

| Quel type de système de caméras avez-vous | Peut-on le voir directement depuis l'étranger | Solution |
|---|---|---|
| Appli du fabricant avec cloud (EZVIZ, Xiaomi, TP-Link, Imou, etc.) | En général oui ; dans quelques régions c'est restreint ou extrêmement lent | Passez sur une IP chinoise et utilisez l'édition chinoise de l'appli |
| Un enregistreur vidéo réseau (NVR) consultable uniquement sur le réseau local de la maison | Non, il n'a aucun point d'accès public | Ajoutez un appareil de la maison à un réseau privé, et faites entrer l'appareil à l'étranger dans le réseau local de la maison via ce réseau privé |
| Appli du fabricant, mais celle des boutiques hors de Chine est un système distinct avec ses propres serveurs | Les comptes ne correspondent pas | Installez l'édition chinoise de l'appli et utilisez le compte chinois |

## Cas 1 : le cloud du fabricant

La caméra envoie l'image au serveur du fabricant, et l'appli la récupère sur ce serveur. La liaison entre un réseau étranger et le serveur d'un fabricant chinois est mauvaise, ce qui se traduit par un chargement lent et des flux qui coupent. Une fois passé sur une IP chinoise, vous empruntez une liaison intérieure à la Chine, et c'est nettement mieux.

Attention : l'appli du même nom dans une boutique hors de Chine se connecte généralement à des serveurs à l'étranger, et les comptes ne sont pas interchangeables. Installez l'édition chinoise de l'appli ; pour les problèmes de région de la boutique, voir le [guide de dépannage et d'installation](../client/06-ios-app-store.md).

## Cas 2 : l'enregistreur n'est que sur le réseau local

C'est le cas le plus courant, et aussi le plus difficile. Le NVR n'a pas d'IP publique, et la redirection de ports est le plus souvent impossible sur un accès Internet domestique en Chine. La solution qui fonctionne est un **réseau privé** :

1. Laissez à la maison un appareil allumé en permanence : un ordinateur, un NAS, un Raspberry Pi ou un routeur compatible font l'affaire. Installez-y le client du réseau privé, ajoutez-le à votre réseau privé et activez le partage du réseau local.
2. Ajoutez aussi le téléphone ou l'ordinateur qui est à l'étranger au même réseau privé.
3. Dès lors, l'appareil à l'étranger joint directement le NVR à son adresse sur le réseau local de la maison, exactement comme si vous y étiez.

La méthode « Privé » de LeoTun est précisément ce type de réseau privé. Un compte s'installe sur autant d'appareils que vous voulez, et le nombre d'appareils en ligne en même temps dépend de la formule : Personnel 2, Famille 4, Entreprise 8. Un appareil à la maison plus quelques-uns à l'étranger, cela correspond exactement à la formule Famille.

## Cas 3 : les comptes ne correspondent pas

Un appareil acheté en Chine est lié à un compte chinois, et l'appli de la boutique hors de Chine ne peut pas s'y connecter. La seule solution est d'installer l'édition chinoise de l'appli. Ne réassociez pas l'appareil : cela déconnecterait le compte de votre famille.

## Un mot sur la vie privée

L'image de vos caméras ne devrait circuler qu'entre vos appareils et votre domicile. Avec le réseau privé, la connexion directe d'appareil à appareil est privilégiée, un relais n'intervenant que si elle est impossible, et l'image n'est stockée sur aucun serveur ; avec le cloud du fabricant, en revanche, elle passe par le fabricant. Dans les deux cas, n'utilisez pas d'« outils de tunnel » d'origine inconnue : cela revient à confier vos caméras à quelqu'un d'autre.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-07) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-07) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
