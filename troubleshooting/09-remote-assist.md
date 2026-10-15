# 09 · Faire examiner votre ordinateur et votre routeur à distance par l'assistance

Certains problèmes restent flous même après une dizaine d'allers-retours de captures d'écran dans le groupe, alors que l'assistance les cerne en deux minutes en regardant directement l'écran. Cet article explique quand l'assistance à distance vaut la peine d'être demandée, quel logiciel utiliser sur ordinateur, comment importer la configuration du serveur de ce site, comment transmettre les informations de connexion à l'assistance en toute sécurité, ce que vous contrôlez pendant la session, comment reprendre la main ensuite, et ce que vous devez faire pour un routeur sous le firmware de ce site.

## Quand l'assistance à distance vaut la peine

- Vous avez parcouru une fois [01 · Liste de contrôle : connexion impossible, lenteur, coupures](01-cannot-connect-slow-drops.md), posé la question en donnant la méthode de connexion, la région, le texte exact de l'erreur ou une capture, et l'heure du problème, et ce n'est toujours pas résolu.
- Vous n'arrivez pas à décrire les étapes vous-même : le réglage est enfoui, vous ne lisez pas la langue du système, ou l'erreur passe trop vite pour être capturée.
- Vous aidez un proche avec son ordinateur, vous n'êtes pas à côté, et vous n'arrivez pas à vous faire comprendre au téléphone.

Dans le cas suivant, **n'utilisez pas l'assistance à distance** ; échangez plutôt par écrit dans le groupe :

- Les ordinateurs gérés de façon centralisée par une entreprise. Les stratégies de groupe interdisent généralement ce genre de programme, et cela peut enfreindre le règlement de l'entreprise.

## Quel logiciel utiliser : RustDesk

Le site recommande [RustDesk](https://rustdesk.com) : il est open source (AGPL-3.0), son code peut donc être audité par n'importe qui ; et le début comme la fin d'une session se décident par votre propre clic. Il fonctionne sous Windows, macOS, Linux, Android et iOS (un iPhone / iPad peut seulement contrôler d'autres appareils, il ne peut pas être contrôlé).

Téléchargez-le sur la [page de contact](https://www.leotun.com/fr/contact#downloads) sous « Centre de téléchargement » → « Assistance à distance », ou sur le site officiel rustdesk.com. N'utilisez pas les sites de téléchargement tiers trouvés dans les résultats de recherche. Les deux côtés de la session doivent l'installer.

## Ce qu'il faut autoriser après l'installation

| Système | Que faire |
|---|---|
| macOS | Dans « Réglages Système → Confidentialité et sécurité », cochez RustDesk à la fois sous « Enregistrement de l'écran » et sous « Accessibilité », puis quittez complètement l'app et rouvrez-la. N'en accorder qu'une seule donne « on voit mais on ne peut pas contrôler » ou un écran entièrement noir. Si le Mac dit qu'elle « est endommagée », voir [06](06-antivirus-false-positive.md) |
| Android | Quand vous êtes aidé, touchez « Start service » (démarrer le service) dans RustDesk et autorisez l'enregistrement de l'écran ; pour que l'assistance puisse toucher votre écran, activez aussi RustDesk dans « Accessibilité » du système |
| Windows / Linux | Fonctionne en général directement après l'installation |

## Se connecter à notre propre serveur

L'assistance à distance passe par le serveur RustDesk auto-hébergé de ce site, qui se connecte aussi de façon fiable depuis la Chine. **Les deux côtés de la session doivent l'importer une fois** ; les deux bouts ne peuvent se trouver que s'ils utilisent le même serveur :

1. Connectez-vous d'abord au site, puis sur la [page de contact](https://www.leotun.com/fr/contact#downloads), allez dans « Centre de téléchargement » → « Assistance à distance » → « Se connecter à notre serveur » et cliquez sur « Copier ».
2. Sur ordinateur, ouvrez dans RustDesk « Settings → Network » (Paramètres → Réseau), cliquez d'abord sur « Unlock network settings » (déverrouiller les paramètres réseau), puis sur « ID/Relay server » (serveur ID/Relais) ; sur téléphone, c'est « Settings → ID/Relay server ».
3. Dans la fenêtre qui s'ouvre, cliquez sur l'icône du presse-papiers en haut à droite (sur téléphone, touchez « Import »). La configuration se remplit automatiquement ; cliquez sur « OK ».

**Ne collez pas la configuration dans les champs de saisie** : cela donne « failed to lookup address » (échec de la résolution de l'adresse). Cette configuration est réservée aux comptes de ce site. Ne la transférez pas.

## Transmettre l'ID et le mot de passe à usage unique à l'assistance

Ouvrez RustDesk : l'écran principal affiche l'ID de cette machine et un mot de passe à usage unique. Avant de les transmettre, vérifiez trois choses :

1. **C'est vous qui avez demandé.** Vous avez décrit le problème dans un groupe officiel indiqué sur la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-09), et c'est l'assistance qui a jugé l'intervention à distance nécessaire, avant de passer à l'étape suivante. Notre équipe ne vous contactera pas d'elle-même, ne vous demandera pas d'installer un logiciel de contrôle à distance et ne vous réclamera pas de code de connexion ; qui que ce soit qui vienne vous le demander, vérifiez d'abord dans le groupe officiel.
2. **Envoyez-les uniquement par les canaux officiels de l'assistance** : les contacts de l'assistance humaine indiqués sur la page de contact. Toute conversation privée hors des groupes se présentant comme « l'assistance LeoTun » n'est pas nous.
3. **Ne les publiez pas dans le groupe.** Un groupe est un lieu visible par beaucoup de monde ; un ID plus un mot de passe, c'est comme laisser la clé de votre ordinateur sur la porte.

## Pendant la session

- Tout au long de la session, vous voyez à l'écran ce qui est fait, et vous pouvez couper la connexion à tout moment dans la fenêtre RustDesk.
- Si quelqu'un vous demande de réduire la fenêtre, de vous éloigner de l'ordinateur, ou d'ouvrir des applis de banque en ligne ou de paiement, **coupez immédiatement**.
- Quand le mot de passe de votre compte doit être saisi, tapez-le vous-même ; ne le dictez pas à l'assistance.

## Reprendre la main ensuite

1. Cliquez sur déconnecter dans la fenêtre RustDesk et vérifiez que l'autre côté est bien hors ligne.
2. Renouvelez le mot de passe à usage unique pour que celui que vous venez d'envoyer ne soit plus valable.
3. Quittez RustDesk. Si vous n'en avez plus besoin, vous pouvez tout simplement le désinstaller et le retélécharger la prochaine fois.

## Routeurs : ce que vous avez à faire

Pour un routeur sous le firmware de ce site, vous n'avez à installer aucun logiciel de contrôle à distance, ni sur le routeur ni sur l'ordinateur, et vous n'avez pas à envoyer le mot de passe d'administration du routeur à l'assistance. Il vous suffit de :

- Laisser le routeur allumé avec le câble réseau branché, et le compte connecté sur le routeur.
- Donner à l'assistance, dans le groupe officiel, votre compte, le modèle du routeur et les symptômes ; l'assistance s'occupe du reste.
- Ne pas le débrancher et le redémarrer à répétition pendant l'intervention, sauf si l'assistance vous le demande.

## FAQ

**L'assistance va-t-elle m'écrire d'elle-même en privé pour me faire installer un logiciel de contrôle à distance ?** Non. Chaque fois que quelqu'un vous aborde sans que vous ayez rien demandé, vérifiez toujours son identité dans le groupe officiel d'abord.

**« failed to lookup address » à l'import ?** Très probablement, la configuration a été collée dans les champs de saisie. Videz ces champs, revenez à la fenêtre « ID/Relay server » et importez en cliquant sur l'icône du presse-papiers en haut à droite.

**Connecté sur macOS mais l'écran est noir, ou on voit sans pouvoir contrôler ?** Les autorisations sont incomplètes. Cochez à la fois « Enregistrement de l'écran » et « Accessibilité », puis quittez complètement l'app et rouvrez-la.

**Que faire d'autre une fois la session terminée ?** Déconnecter, renouveler le mot de passe à usage unique, quitter le programme. Une fois ces trois étapes faites, l'autre côté ne pourra plus jamais se connecter.

## Pour aller plus loin

- [Utiliser RustDesk pour l'aide à distance (guide du site)](https://www.leotun.com/fr/guides/rustdesk-certificate?utm_source=github&utm_content=troubleshooting-09)
- [Que faire quand votre Mac dit que l'app « est endommagée »](https://www.leotun.com/fr/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-09)
- [Page de contact : groupes d'assistance, assistance humaine et e-mail](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-09)
- [05 · Nous joindre, et ne jamais perdre le contact](05-how-to-reach-us.md)
- [01 · Liste de contrôle : connexion impossible, lenteur, coupures](01-cannot-connect-slow-drops.md)

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=troubleshooting-09) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-09) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
