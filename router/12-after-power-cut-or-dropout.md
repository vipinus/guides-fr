# 12 · Le routeur se rétablit-il tout seul après une coupure de courant ou de connexion ?

Quiconque a déjà bricolé son propre routeur VPN a sans doute connu ça : une coupure de courant, ou une brève panne de la box, et après le redémarrage tout semble normal, mais le tunnel ne revient jamais tant que vous n'êtes pas allé le reconfigurer dans la page d'administration.

## La réponse courte

Oui, il se rétablit tout seul. Après une coupure de courant et un redémarrage, une coupure de la connexion Internet, ou un tunnel qui tombe en cours d'utilisation, le firmware se reconnecte de lui-même. Pas de page d'administration, pas de reconnexion au compte.

## Comment il s'y prend

Le firmware fait tourner en permanence un contrôle qui vérifie le tunnel environ toutes les trente secondes. S'il le trouve coupé, il se reconnecte et remet en place le routage sélectif.

Pendant le court délai avant le retour du tunnel, les sites chinois continuent de fonctionner. Le foyer ne perd pas Internet simplement parce que le tunnel n'est pas encore rétabli.

Vos réglages sont aussi conservés : la région, le mode de routage sélectif et l'option « Automatically pick the fastest line » (choisir automatiquement la ligne la plus rapide) survivent à un redémarrage ou à une reconnexion. Si vous avez désactivé le routage sélectif, il reste désactivé.

## Ce qui se passe dans chaque cas

| Ce qui s'est passé | Ensuite |
|---|---|
| Le courant revient après une coupure | Le routeur démarre et le tunnel se reconnecte tout seul |
| La connexion Internet tombe puis revient | Le tunnel se reconnecte dès que la ligne est rétablie |
| Le tunnel tombe en cours d'utilisation | Le contrôle s'en aperçoit et reconnecte |
| Le compte expire | Le trafic cesse de passer par le tunnel, le réseau de la maison continue de fonctionner. Après le renouvellement, tout reprend tout seul, sans avoir à se reconnecter |
| Nous changeons l'adresse d'un serveur | Le routeur suit. Rien à reconfigurer |

## Toujours rien après quelques minutes ? Vérifiez ceci

1. **La connexion Internet elle-même fonctionne-t-elle ?** Ouvrez un site chinois. Si cela échoue, le problème vient de la ligne ou de la box, pas du tunnel.
2. **Le compte a-t-il expiré ?** Le tunnel ne se connecte pas après l'expiration. Connectez-vous au site pour vérifier.
3. **Essayez une autre région.** Changez de région dans la page d'administration. Il arrive qu'une région ait un problème passager.
4. **Redémarrez le routeur.** Débranchez-le, attendez dix secondes, rebranchez-le.
5. Si rien de tout cela n'aide, envoyez à l'assistance une capture d'écran de l'état affiché dans la page d'administration.

## Le tout premier démarrage après le flashage

Le premier démarrage est plus lent que d'habitude : le firmware cherche des mises à jour de ses composants et détecte le pays pour régler la puissance d'émission Wi-Fi. **Branchez un câble réseau pour ce premier démarrage.** Un Wi-Fi faible avant qu'il ait été en ligne une première fois est normal.

## FAQ

**Est-il utilisable là où les coupures de courant sont fréquentes ?** Oui. Il se reconnecte à chaque retour du courant.

**Faut-il redémarrer le routeur régulièrement ?** Non.

**Les mises à jour des composants vont-elles couper ma connexion ?** Non. Les mises à jour sont vérifiées et téléchargées au démarrage et prennent effet au démarrage suivant. Le routeur ne redémarrera pas sous vos yeux en pleine utilisation.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-12) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-12) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
