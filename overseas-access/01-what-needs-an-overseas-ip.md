# 01 · Quels services exigent une IP hors de Chine, et comment fonctionne la ligne

Le critère est l'inverse de l'accès à la Chine depuis l'étranger : quand le service voit que votre IP d'origine est en Chine continentale, ou que vous ne pouvez pas du tout joindre ses serveurs, il ne s'ouvre pas, fonctionne en mode dégradé ou devient extrêmement lent. Le tableau ci-dessous est classé par usage.

| Catégorie | Exemples | Sans la ligne, depuis la Chine | Ce qu'il faut en plus d'une IP |
|---|---|---|---|
| Travail | Google Workspace, Slack, Zoom, Teams, Notion | Ne s'ouvre pas, ou coupe sans arrêt | Un compte d'entreprise |
| Développement | GitHub, npm, Docker Hub, sources PyPI hors miroirs, Stack Overflow | Si lent que tout expire | Rien |
| IA | ChatGPT, Claude, Gemini | Ne s'ouvre pas | Le pays d'inscription du compte, un numéro de téléphone |
| Recherche | Google Scholar, bases d'articles scientifiques, messagerie universitaire | Ne s'ouvre pas, ou extrêmement lent | Un compte universitaire |
| Jeux | Steam régions hors de Chine, PSN, Switch eShop, serveurs à l'étranger | La boutique ne s'ouvre pas, forte latence | Un compte rattaché aux serveurs de la région |
| Vidéo et musique | YouTube, Netflix, Disney+, Spotify | Ne s'ouvre pas | Un compte payant, dont la région doit correspondre à l'IP |
| Réseaux sociaux | X, Instagram, Telegram, Discord, WhatsApp | Ne s'ouvre pas | Un numéro de téléphone |

## Une distinction importante

**« Avoir besoin d'une IP hors de Chine » et « avoir besoin d'un compte étranger » sont deux choses différentes.** Pour GitHub et YouTube, changer d'IP suffit ; Netflix exige un compte payant d'une région correspondante ; s'inscrire à ChatGPT demande un numéro de téléphone étranger capable de recevoir un code de vérification. La ligne résout la question « est-ce que ça s'ouvre » ; le compte, c'est à vous de le gérer.

## Comment fonctionne la ligne

Votre trafic est d'abord chiffré et envoyé à un serveur hors de Chine, qui accède ensuite à la destination. Ce que voit la destination, c'est l'IP de ce serveur. Il y a trois façons de procéder : un client, le proxy web et un routeur. Pour choisir, voir [Quelle méthode de connexion pour quelle situation](../network/02-choose-your-connection-method.md).

## Trois idées reçues

- **Changer de DNS ne sert à rien.** L'échec de connexion est un problème de chemin, pas de résolution de noms.
- **La vitesse dépend de la ligne entre les deux points.** Depuis la Chine, le goulot d'étranglement est la liaison transfrontalière et la sortie de votre opérateur : le choix de la région compte donc plus que la puissance du serveur ; voir [03](03-which-region-is-fastest.md).
- **Quand vous utilisez des apps chinoises, tout n'a pas à passer par la ligne.** Activez le routage sélectif : par défaut, seuls les sites bloqués passent par la ligne, tandis que les sites chinois et les sites étrangers qui s'ouvrent de toute façon depuis la Chine restent en direct, sans détour ; voir [Routage sélectif sur le routeur](../router/03-router-split-routing.md).

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=overseas-access-01) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=overseas-access-01) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
