# 03 · Connecté, mais le site vidéo affiche toujours une restriction de droits : IPv6 et DNS passent à côté

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/overseas-video?utm_source=github&utm_content=troubleshooting-03

Vous avez franchi l'étape 1 de [02 · Connecté à la Chine mais impossible de regarder](02-still-blocked-after-connecting.md) — l'IP de sortie est bien en Chine continentale — et pourtant le site affiche toujours que la vidéo « ne peut pas être lue en raison de restrictions de droits ». Neuf fois sur dix, il reste sur l'appareil un chemin qui ne passe pas par le VPN : **IPv6** ou **DNS**. Un site vidéo déduit où vous êtes de l'adresse qu'il voit, et tant qu'un seul chemin fuit, ce qu'il voit reste l'étranger.

## Pourquoi les fuites se produisent

- Les appareils récents ont à la fois une adresse IPv4 et une adresse IPv6, et les navigateurs privilégient l'IPv6. Si le VPN ne prend en charge que l'IPv4, les requêtes IPv6 sortent directement par votre connexion Internet.
- Le « DNS sécurisé » intégré au navigateur, le « DNS privé » d'Android, ou un autre outil de réseau maillé en marche (Tailscale et consorts) prennent tous la main sur la résolution des noms avant le VPN.

« Connecté » signifie seulement que le tunnel est établi. Cela ne veut pas dire que tout le trafic passe par le tunnel.

## Vérification en cinq étapes

1. **Vérifiez l'IPv6.** Une fois connecté, cherchez « test ipv6 » et ouvrez une page de test. Si le champ IPv6 affiche une adresse du pays où vous êtes → le problème est là, passez à l'étape 2. Si les deux champs indiquent la Chine continentale, ou si l'IPv6 est indisponible → passez à l'étape 3.
2. **Désactivez l'IPv6, ou passez à un client qui bloque l'IPv6.** Windows : dans les propriétés de la carte réseau, décochez « Protocole Internet version 6 ». macOS : Réglages réseau → TCP/IP → réglez IPv6 sur « Lien local uniquement ». Téléphone : coupez le Wi‑Fi et essayez une fois en données mobiles ; les box Internet ont généralement l'IPv6, alors que les données mobiles des opérateurs souvent non.
3. **Vérifiez le DNS.** Chrome Paramètres → Confidentialité et sécurité → désactivez « Utiliser un DNS sécurisé » ; sur Android, désactivez le « DNS privé » ; quittez les autres VPN, outils de réseau maillé et extensions de proxy.
4. **Quittez complètement l'app et rouvrez-la ; pour la version web, effacez les données du site.** Les plateformes gardent en cache leur précédente vérification de région.
5. **Passez par un autre point d'entrée et réessayez.** L'adresse d'une sortie donnée vient peut-être d'être repérée par la plateforme.

## Ce que fait LeoTun

Depuis septembre 2026, les trois méthodes de connexion de LeoTun (Hiddify, Cisco AnyConnect, OpenVPN) rejettent directement l'IPv6 dans le tunnel et envoient des réglages DNS qui forcent la résolution dans le tunnel : aucun réglage à modifier sur votre appareil. **Les configurations Hiddify importées avant septembre n'ont pas cette règle. Supprimez-les et scannez à nouveau le QR code pour les réimporter.**

Le routeur, lui, ne fuit pas du tout : tout le réseau local sort par le routeur, donc l'IPv6 et le DNS des appareils n'atteignent jamais l'extérieur.

## Cas où le message apparaît encore

| Cas | Symptôme | Solution |
|---|---|---|
| La sortie n'est pas en Chine continentale | La recherche d'IP indique Hong Kong / Taïwan / Japon | Passez à un point d'entrée en Chine ; pour Tencent et iQIYI, les adresses de Hong Kong et de Taïwan comptent aussi comme l'étranger |
| Des règles de routage personnalisées mettent les domaines vidéo en « direct » | Les pages web s'ouvrent, mais les vidéos ne se lisent pas | Faites passer les domaines chinois par le nœud ; à l'étranger, n'activez pas « Chine en direct » |
| Vous utilisez le proxy web | Fonctionne dans le navigateur, pas dans les apps | Regarder des vidéos demande un tunnel couvrant tout l'appareil ; le proxy web ne couvre que le navigateur |

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=troubleshooting-03) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-03) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
