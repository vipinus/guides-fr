# 13 · WeChat, Alipay et mini-programmes chinois

## Ce que vous constatez

Vous êtes à l'étranger, WeChat et Alipay eux-mêmes fonctionnent, mais dès que vous touchez aux **mini-programmes, aux articles des comptes officiels ou à Channels** qu'ils contiennent, vous tombez sur une roue de chargement ou un écran blanc :

- Vous ouvrez un article de compte officiel et les images ne finissent jamais de charger
- Un mini-programme reste bloqué sur son écran de lancement, ou affiche « erreur réseau »
- Dans Channels, vous voyez défiler les vignettes, mais rien ne se lit quand vous touchez une vidéo
- Les pages Centre citoyen, assurance maladie et fonds de prévoyance pour le logement d'Alipay ne s'ouvrent pas

## La cause

La **messagerie et les virements** de WeChat et d'Alipay passent par leurs propres canaux, qui fonctionnent dans le monde entier, d'où l'impression que « l'appli marche ».

Mais les mini-programmes, les articles des comptes officiels et Channels sont au fond des **pages web**, servies par des serveurs tiers dont la plupart ne servent que les utilisateurs en Chine. Avec une IP à l'étranger, soit ils ne vous renvoient aucun contenu, soit ils sont si lents qu'ils expirent.

D'où ces symptômes curieusement partagés : vous pouvez discuter et recevoir des enveloppes rouges, mais pas ouvrir ce qu'il y a à l'intérieur.

## Que faire

Passez sur une IP chinoise et rouvrez : tout fonctionne normalement. Deux détails font souvent trébucher :

**Premièrement, redémarrez l'appli, ne vous contentez pas de rouvrir la page.** WeChat met en cache « l'endroit où il s'est connecté la dernière fois », et rafraîchir le mini-programme juste après avoir changé d'IP échoue souvent. Fermer complètement WeChat en arrière-plan puis y revenir réussit bien plus souvent.

**Deuxièmement, ne faites pas passer que le navigateur par la ligne.** Les mini-programmes tournent dans WeChat, et les méthodes de type extension de navigateur ne les atteignent pas. Il faut que **tout le téléphone**, ou au moins l'appli WeChat, passe par la ligne.

## Ne faire passer que WeChat par la ligne sur un téléphone

Les clients Android et iOS prennent tous deux en charge le mode « par appli », dans lequel vous ne cochez que WeChat et Alipay et laissez les autres applis sur le réseau local. Avantages :

- Les applis qui dépendent de votre **position réelle**, comme la livraison de repas, les VTC et les cartes, ne sont pas affectées
- Cela économise la batterie et les données
- Les applis bancaires ne déclenchent pas le contrôle des risques parce que « la localisation a soudain changé »

## Un malentendu courant

Certains pensent qu'un compte officiel qui ne s'ouvre pas a été « banni » ou qu'il y a « un problème de compte », et désinstallent puis réinstallent sans fin. Ce n'est presque jamais le cas : le même article apparaît aussitôt l'IP changée. Le test est simple : demandez à un ami en Chine d'ouvrir le même lien et de vous envoyer une capture d'écran. S'il le voit et pas vous, c'est l'IP.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-13) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-13) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre durable
