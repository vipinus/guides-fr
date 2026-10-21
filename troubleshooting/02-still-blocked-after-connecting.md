# 02 · Connecté pour accéder à la Chine mais toujours impossible de regarder : que faire

Vérifiez dans l'ordre. Chaque étape prend une minute.

1. **Vérifiez que l'IP de sortie a vraiment changé.** Ouvrez dans le navigateur un site qui indique la localisation de votre IP et regardez s'il s'agit de la Chine continentale. Sinon, le VPN n'est pas actif : reconnectez-vous.
2. **Fuites IPv6 et DNS.** Si l'IP de sortie est bonne mais que le site vous considère toujours à l'étranger, le plus probable est que l'IPv6 ou le DNS local de l'appareil contourne le VPN. C'est le cas le plus fréquent, et il a son propre article : [03 · IPv6 et DNS passent à côté](03-ipv6-and-dns-leak.md).
3. **Cache de l'appli.** Les applis de vidéo et de musique gardent en cache le résultat de leur contrôle de région. Quittez complètement l'appli et rouvrez-la ; si cela ne suffit pas, effacez les données de l'appli.
4. **Version de l'appli.** Si vous avez installé la version internationale (iQIYI, WeTV), le catalogue n'est pas le même. Passez à la version Chine continentale.
5. **Région d'inscription du compte.** Quelques plateformes limitent le contenu selon la région où le compte a été créé, quelle que soit votre IP actuelle. Dans ce cas, la seule solution est un autre compte.
6. **Région et langue du système.** Certaines applis lisent la région du système. Réglez la région du système sur la Chine et réessayez.
7. **Région d'entrée.** Certains contenus diffèrent aussi selon la province de l'IP. Passez à un autre point d'entrée et réessayez.

## Ça ne marche toujours pas

Donnez ces quatre éléments à l'assistance : le site ou l'appli visé, le texte exact de l'erreur, la localisation actuelle de votre IP de sortie, et la méthode de connexion utilisée. Avec cela, le problème peut être cerné du premier coup.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=troubleshooting-02) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-02) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre permanente
