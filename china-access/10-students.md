# 10 · Étudiants à l'étranger : bien configurer un VPN vers la Chine

Ce dont un étudiant à l'étranger a besoin, ce n'est pas d'« une ligne vers la Chine connectée en permanence », mais d'obtenir à coup sûr une IP chinoise dans quelques situations précises : suivre des séries et écouter de la musique, se connecter à la banque en ligne et aux applis administratives, décrocher des billets, et de temps en temps vérifier à distance les appareils de la famille restée en Chine. Chaque situation demande quelque chose de différent à la ligne, et les réseaux de campus ont leurs propres limites. Cet article explique, situation par situation, ce qu'il faut, comment le configurer et quand se déconnecter, et se termine par une liste de contrôle à faire en dix minutes avant la rentrée.

## Séries, musique, directs : une IP chinoise suffit, mais il faut fermer l'IPv6

Tencent Video, iQIYI, les animés de Bilibili, NetEase Cloud Music et QQ Music déterminent tous la région d'après l'IP source, et se connecter à la ligne vers la Chine suffit. Le piège dans lequel les étudiants tombent le plus souvent : les réseaux de campus et de résidence universitaire ont fréquemment l'IPv6 ; l'appareil privilégie l'IPv6, qui ne passe pas par la ligne, si bien que le site vidéo voit toujours une adresse étrangère et affiche une « restriction de droits ».

La solution : utiliser une ligne ou un client qui rejette l'IPv6 dans le tunnel, ou désactiver l'IPv6 sur l'appareil. Les trois méthodes de connexion de LeoTun bloquent déjà l'IPv6 côté ligne, sans rien changer sur l'appareil ; pour le dépannage détaillé, voir « Tencent Video ou iQIYI bloqués à l'étranger ».

La qualité d'image dépend de la bande passante transfrontalière. De 20 h à 23 h, heure de Pékin, c'est l'heure de pointe, ce qui correspond à la matinée jusqu'à midi en Europe et en Amérique du Nord ; si le 1080p tourne en boucle sur cette plage, passez à une autre sortie en Chine.

## Banque en ligne, Alipay, applis administratives : connectez-vous par la ligne vers la Chine, puis déconnectez-vous

Les différentes applis bancaires, Alipay, CHSI (la plateforme officielle des diplômes chinois) et la plateforme nationale des services administratifs ne traitent pas les IP étrangères de la même manière : certaines refusent carrément la connexion, d'autres ajoutent plusieurs étapes de vérification, d'autres encore vous laissent entrer mais déclenchent le contrôle des risques lors d'un virement. Point commun : elles enregistrent votre IP de connexion, et les allers-retours entre l'étranger et la Chine sont ce qui vous fait signaler le plus facilement.

La marche à suivre : quand vous devez faire ces opérations, connectez-vous d'abord à la ligne vers la Chine, puis ouvrez l'appli ; une fois fini, quittez l'appli, puis déconnectez la ligne. N'utilisez pas la même appli en basculant sans arrêt entre la ligne vers la Chine et le réseau local.

Les codes de vérification par téléphone qui n'arrivent pas n'ont rien à voir avec la ligne : c'est une question d'itinérance d'un numéro chinois à l'étranger. Avant de quitter la Chine, activez l'itinérance internationale sur ce numéro ou passez à une offre qui permet de recevoir les codes à l'étranger.

## 12306, billets de concert : connectez-vous à l'avance, et ne changez rien au moment de payer

12306 (la billetterie ferroviaire chinoise) demande parfois une vérification supplémentaire depuis une IP étrangère, et dans une course aux billets, une vérification de plus, c'est le billet perdu. Quelques minutes avant l'ouverture des ventes, connectez-vous à la ligne vers la Chine, identifiez-vous et sélectionnez les voyageurs, puis validez dès que l'heure arrive. Quand le paiement vous redirige vers Alipay ou la banque en ligne, ne touchez pas à la ligne.

Le même raisonnement vaut pour les billetteries comme Damai et Maoyan.

## Trois limites des réseaux de campus et de résidence

- IPv6 : voir plus haut ; utilisez une ligne qui bloque l'IPv6.
- UDP restreint ou bridé : bon nombre de réseaux de campus brident voire bloquent le trafic UDP. Le hysteria2 qu'utilise Hiddify passe par l'UDP et, sur ces réseaux, il est même moins stable qu'AnyConnect, qui passe par TLS ; un même compte permet d'utiliser les deux, donc si l'UDP ne passe pas, basculez sur AnyConnect.
- Portail d'authentification (captive portal) : après vous être connecté au Wi‑Fi du campus, terminez d'abord l'authentification dans le navigateur, puis activez la ligne. Si le client est réglé sur « se connecter automatiquement au démarrage », il tentera de se connecter avant l'authentification et échouera ; patientez un peu ou reconnectez-vous manuellement.

## Pendant les vacances en Chine : le même compte, dans l'autre sens

Une fois en Chine, vous avez besoin de Google, de la messagerie de votre université et des bases d'articles scientifiques : changez simplement la région de la ligne, de la Chine vers le Japon, les États-Unis ou une région proche hors de Chine, sans changer de compte. Les 24 régions de LeoTun sont toutes dans le même compte, et accéder à la Chine depuis l'étranger comme à l'étranger depuis la Chine sont les deux sens d'une même chose.

Quand vous vous connectez depuis la Chine, les adresses AnyConnect et Hiddify changent automatiquement pour contourner les blocages, et les adresses enregistrées dans le client n'ont pas besoin d'être modifiées ; si la connexion échoue, changez de région ou de protocole.

## Liste de contrôle en dix minutes avant la rentrée

1. Installez un client (AnyConnect ou Hiddify) sur votre téléphone et un sur votre ordinateur, et connectez-vous ou importez par QR code sur chacun.
2. Connectez-vous à la ligne vers la Chine sur le Wi‑Fi de la résidence et ouvrez une page de test IPv6 pour vérifier que l'IPv6 est indisponible ou affiche une adresse en Chine continentale.
3. Ouvrez Tencent Video et lancez n'importe quel épisode pour vérifier qu'aucune restriction de droits n'apparaît.
4. Connectez-vous une fois à votre appli bancaire pour vérifier que vous pouvez entrer, puis quittez l'appli et déconnectez la ligne.
5. Notez le contact de l'assistance de votre fournisseur de ligne ; en cas de problème, lisez d'abord le guide de dépannage, puis posez la question.

## FAQ

**Utiliser un VPN vers la Chine peut-il nuire à mon compte réseau à l'université ?** Non. La ligne ne fait qu'envoyer votre trafic vers une sortie en Chine, et le réseau du campus ne voit qu'une connexion chiffrée. Le règlement de la plupart des universités n'interdit que les téléchargements illégaux et les attaques, et l'accès personnel aux services de votre propre pays n'en fait pas partie ; en cas de doute, consultez la charte d'utilisation de votre université.

**Peut-on partager un compte avec un colocataire ?** Selon la formule, un compte peut avoir 2 (Personnel), 4 (Famille) ou 8 (Entreprise) appareils en ligne en même temps, et le partager avec la famille ou des colocataires est conforme aux règles. Mais pour des usages comme la banque en ligne, il est plus sûr que chacun ait son propre compte, pour éviter que plusieurs personnes basculent sans arrêt sur la même ligne et déclenchent le contrôle des risques.

**Pourquoi Hiddify est-il lent en résidence alors qu'AnyConnect fonctionne normalement ?** Très probablement parce que le réseau du campus restreint l'UDP. Le protocole hysteria2 de Hiddify repose sur l'UDP et, quand il est bridé, cela se traduit par de la lenteur ou des coupures ; AnyConnect passe par TLS, comme une visite de site HTTPS, et n'est pas affecté.

**Peut-on jouer sur des serveurs chinois avec une ligne vers la Chine ?** On peut se connecter, mais la latence dépend de la distance physique jusqu'à la sortie en Chine. Cette part de latence est incompressible : acceptable pour les jeux au tour par tour et les MOBA, sensible dans les jeux de tir.

**Le compte sert-il encore une fois diplômé et rentré en Chine ?** Oui. Le même compte continue de fonctionner en Chine avec une région hors de Chine, pour accéder à Google, GitHub, la messagerie de votre université et les bases d'articles scientifiques.

## Pour aller plus loin

- [Tencent Video ou iQIYI bloqués à l'étranger : que faire](https://www.leotun.com/fr/guides/overseas-video?utm_source=github&utm_content=china-access-10)
- [Bien choisir un VPN avec IP chinoise](https://www.leotun.com/fr/guides/choose-china-vpn?utm_source=github&utm_content=china-access-10)
- [Télécharger le client AnyConnect](https://www.leotun.com/fr/anyconnect?utm_source=github&utm_content=china-access-10)
- [Client Hiddify et import de l'abonnement](https://www.leotun.com/fr/singbox?utm_source=github&utm_content=china-access-10)

Version de cet article sur le site : https://www.leotun.com/fr/guides/students?utm_source=github&utm_content=china-access-10

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-10) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-10) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
