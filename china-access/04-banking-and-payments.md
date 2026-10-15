# 04 · Banque en ligne, banque mobile et paiements

## Ce que regarde le contrôle des risques d'une banque

Une banque ne regarde pas seulement l'IP. Elle combine plusieurs signaux et leur attribue un score :

1. **La localisation enregistrée de l'IP** : une IP étrangère fait immédiatement monter le niveau de risque.
2. **La carte SIM** : l'appli bancaire lit les informations de la SIM, et une carte d'un opérateur étranger compte contre vous.
3. **L'empreinte de l'appareil** : un nouvel appareil, ou un appareil jailbreaké ou rooté.
4. **Le comportement** : un gros virement dès la première connexion depuis un nouvel endroit.

D'où la situation courante : une fois passé sur une IP chinoise, vous arrivez à vous connecter, mais le virement reste bloqué. L'IP ne règle que le premier point.

## Ce que vous pouvez faire

- Après être passé sur une IP chinoise, **commencez par de petites opérations** pour que le contrôle des risques s'habitue à cet environnement, puis passez aux montants importants.
- Gardez une carte SIM chinoise et activez l'itinérance : les codes de vérification comme le contrôle de la SIM en dépendent.
- Installez si possible l'édition chinoise de l'appli bancaire ; pour les problèmes de région de la boutique, voir [Que faire quand iOS refuse d'installer une app](../client/06-ios-app-store.md) dans le dépôt voisin.
- Si vous êtes bloqué, ne réessayez pas en boucle. Les échecs répétés déclenchent un gel temporaire, et appeler le service client de la banque est le moyen le plus rapide de le lever.

## Alipay et WeChat Pay

Tous deux sont plus tolérants que les banques vis-à-vis de l'IP et fonctionnent en général avec une IP étrangère, mais les comptes liés à une carte étrangère ont des limites de montant et de lieu d'utilisation. Quand vous devez payer avec une carte chinoise ou virer de l'argent à un commerçant chinois, passer sur une IP chinoise rend les choses bien plus fluides.

## À éviter

N'effectuez pas d'opérations bancaires sur un Wi-Fi public, que vous passiez par la ligne ou non. La ligne ne fait que changer votre IP de sortie et ne chiffre rien pour vous entre la sortie et la banque ; la sécurité vient du chiffrement propre à l'appli bancaire.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-04) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-04) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
