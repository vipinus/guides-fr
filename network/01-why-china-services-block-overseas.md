# 01 · Comment fonctionne l'accès à la Chine depuis l'étranger

## Ce que vous constatez

Vous êtes à l'étranger, vous ouvrez iQIYI, Bilibili ou NetEase Cloud Music, et un message vous indique que « ce contenu n'est disponible qu'en Chine continentale » ; la banque en ligne et 12306 refusent tout simplement de s'ouvrir, ou le code de vérification n'arrive jamais.

## Une seule cause : le pays d'enregistrement de votre IP

Quand votre appareil se connecte à Internet, votre opérateur lui attribue une adresse IP publique. Il existe un registre mondial de ces adresses, qui indique à quel pays et à quel opérateur chacune appartient. Les plateformes chinoises de vidéo et de musique n'achètent les droits que pour la **Chine continentale** et n'ont légalement pas le droit de diffuser ailleurs : elles refusent donc dès qu'elles voient une IP étrangère.

Les banques et les sites de billetterie suivent une autre logique. Pour eux, il ne s'agit pas de droits d'auteur mais de contrôle des risques : une connexion depuis une IP étrangère est jugée à haut risque et bloquée d'office.

## L'approche pour y remédier

Faire en sorte que l'IP vue par le serveur soit une IP de Chine continentale. Pour cela, votre trafic est d'abord envoyé vers un serveur situé en Chine continentale, qui accède ensuite au site visé à votre place. Le site voit l'IP de ce serveur et vous laisse passer.

C'est exactement ce que fait une « ligne vers la Chine » : elle fait sortir votre trafic par une IP de Chine continentale.

## Trois idées reçues

- **Changer de DNS ne sert à rien.** Le DNS ne fait que traduire les noms de domaine en adresses ; le site visé regarde votre IP d'origine, pas le DNS que vous utilisez.
- **Quelques plateformes regardent aussi la région du système.** En plus de l'IP, certaines vérifient la langue de l'appareil et la région de la boutique d'apps ; dans ce cas, changez aussi la région du système.
- **La vitesse dépend de la qualité de la ligne entre les deux points.** La liaison transfrontalière entre l'étranger et la Chine continentale est le goulot d'étranglement : choisir un point d'entrée proche de vous, doté d'une ligne optimisée vers la Chine, compte plus que la puissance du serveur lui-même.

## Pour aller plus loin

- [Quelle méthode de connexion pour quelle situation](02-choose-your-connection-method.md)
- [Liste de vérification : impossible de se connecter, lenteurs, coupures](../troubleshooting/01-cannot-connect-slow-drops.md)

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=network-01) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=network-01) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; chaque ami invité qui paie vous rapporte à tous les deux 15 points (environ 15 jours en formule Personnel), une offre sans date de fin
