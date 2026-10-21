# 10 · Le NAS, l'imprimante et les caméras derrière le routeur seront-ils affectés ?

Quand on installe un routeur VPN, la première inquiétude concerne généralement le reste de la maison : le NAS, l'imprimante et les caméras vont-ils continuer à fonctionner, et le NAS va-t-il faire passer tout son trafic par le VPN ?

## La réponse courte

Non. Le routage sélectif est activé par défaut : **le trafic entre les appareils de la maison et le trafic vers les services en Chine n'entrent jamais dans le tunnel. Seuls les sites qui ont besoin du VPN passent par lui.**

## Trois types de trafic, trois chemins

| Trafic | Chemin | Exemples |
|---|---|---|
| Entre appareils de la maison | Reste sur le réseau local, ne touche jamais le tunnel | Copier des fichiers sur le NAS, diffuser vers la télé, imprimer |
| Vers des services en Chine | En direct, par votre propre connexion Internet | NAS qui se synchronise avec un stockage en ligne chinois, caméras qui envoient vers un cloud chinois, téléchargements locaux |
| Vers des sites bloqués | Par le tunnel | YouTube, moteurs de recherche, outils d'IA |

Copier des fichiers sur le NAS de la maison se fait donc à pleine vitesse locale, et ses sauvegardes vers un stockage en ligne chinois utilisent toute votre connexion sans toucher au VPN.

Quand vous êtes à l'étranger et utilisez une ligne vers la Chine, le sens s'inverse : les sites chinois de la liste passent par le tunnel et tout le reste en direct. Voir [03 · Ce qu'est le routage sélectif](03-router-split-routing.md).

## Trois situations courantes

**Accéder au NAS depuis l'extérieur (fichiers à distance, sauvegarde des photos du téléphone)**
Deux possibilités :
- Utiliser la méthode Privé (Tailscale) : connectez le NAS et votre téléphone au même compte, et joignez le NAS par son nom d'appareil depuis n'importe où. Ni IP publique, ni redirection de ports. Voir [Réseau privé ou VPN](../network/03-private-network-vs-vpn.md).
- Continuer comme avant (accès à distance du fabricant, redirection de ports). Le routeur ne le bloque pas.

**Téléchargements lancés sur le NAS**
Les téléchargements depuis des sources chinoises passent en direct et ne sont pas affectés. Ceux depuis des sites étrangers qui s'ouvrent de toute façon depuis la Chine (téléchargements Apple et Microsoft, par exemple) passent aussi en direct par défaut ; seuls les téléchargements depuis des sites bloqués passent par le tunnel, à la vitesse du tunnel. Si vous ne voulez pas que les téléchargements utilisent le tunnel, branchez le NAS sur le routeur amont ou la box : il contournera complètement ce routeur.

**Un portable professionnel qui doit utiliser le VPN de l'entreprise**
Connectez-le au Wi-Fi du routeur amont ou de la box, à l'écart de ce routeur. Deux VPN empilés l'un sur l'autre empêchent généralement d'accéder au réseau de l'entreprise.

## Quand un appareil ne se comporte pas comme prévu

- L'appareil a le « DNS privé » ou le « DNS sécurisé » activé. Il résout alors les noms tout seul, en contournant le routeur, et le routage sélectif ne le voit pas. Désactivez ce réglage.
- Vérifiez sur quel Wi-Fi il est connecté. S'il est sur le Wi-Fi de la box, il n'est jamais passé par ce routeur.

## FAQ

**Le NAS occupe-t-il une place d'appareil sur mon compte ?** Non. Le routeur occupe une place, et rien de ce qui est derrière n'est compté à part.

**Avec toute la maison dessus, vais-je manquer de données ?** Les comptes ont des données illimitées, et le trafic local n'entre de toute façon jamais dans le tunnel.

**Puis-je garder un appareil hors du VPN en permanence ?** Oui, connectez-le au routeur amont ou à la box. La page d'administration permet aussi de passer tout le routeur en mode « Direct », mais cela s'applique à tout le monde à la fois.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-10) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-10) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
