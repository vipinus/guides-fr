# 03 · Utiliser les sites administratifs et de services publics chinois

## Ce que vous constatez

La plateforme nationale des services administratifs, les sites de services des provinces et des villes, le bureau des impôts en ligne, la consultation de la sécurité sociale et du fonds de logement (housing provident fund), CHSI, 12306 : depuis l'étranger, soit ils ne s'ouvrent pas, soit ils s'ouvrent mais le code de vérification n'arrive jamais ou la reconnaissance faciale échoue.

## Commencez par identifier à quel niveau se situe le problème

| Symptôme | Cause | Solution |
|---|---|---|
| La page ne s'ouvre pas du tout, ou expire | Le site n'est ouvert qu'aux IP de Chine continentale, ou des paquets sont perdus sur la ligne internationale | Passez sur une IP chinoise |
| La page s'ouvre, mais le code de vérification par téléphone n'arrive jamais | Le SMS doit être envoyé à un numéro chinois | Gardez une carte SIM chinoise et activez l'itinérance internationale pour recevoir les SMS |
| Le code arrive, mais la reconnaissance faciale échoue | Vous utilisez la version d'une boutique d'applis étrangère, ou c'est l'autorisation d'accès à la caméra | Installez l'édition chinoise de l'appli et autorisez la caméra |
| On vous dit que « l'environnement réseau actuel est anormal » | Le contrôle des risques a détecté des signes de proxy | Réessayez avec une autre région d'entrée, ou passez par la solution routeur (qui ressemble davantage à une connexion domestique) |

## Le cas de 12306

12306 (le site de réservation des trains chinois) est extrêmement sensible à l'IP : depuis une IP étrangère, même la page d'accueil peut refuser de s'ouvrir. Une fois sur une IP chinoise : l'inscription demande un numéro de téléphone chinois, l'achat d'un billet exige une pièce d'identité au nom réel, et le paiement passe par une carte bancaire chinoise ou Alipay. Il vous faut les trois pour acheter un billet. Aux pics de réservation, le site limite aussi le nombre de requêtes par IP : n'ouvrez pas plusieurs fenêtres en rafraîchissant sans arrêt.

## CHSI et la vérification des diplômes

CHSI (le portail officiel de vérification des diplômes chinois) n'est pas particulièrement strict avec les IP étrangères ; le principal problème, c'est la lenteur. Mais ses SMS de vérification ne partent eux aussi que vers des numéros chinois. Avant une vérification de diplôme, les étudiants à l'étranger doivent d'abord s'assurer que leur numéro chinois reçoit toujours les SMS.

## Un conseil

Les démarches administratives ne reviennent souvent qu'une ou deux fois par an, et chercher une ligne à la dernière minute à chaque fois est une vraie corvée. Configurer la ligne vers la Chine comme un point d'entrée fixe, puis revenir en arrière une fois terminé, est moins pénible que de tout reconfigurer à chaque fois.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-03) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-03) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre permanente
