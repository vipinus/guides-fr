# 06 · Jeux sur serveurs chinois et diffusion en direct

## Jeux : la connexion passe, mais la latence est élevée

La plupart des jeux sur serveurs chinois ne bloquent pas les IP étrangères ; le problème, c'est la latence. Si vous êtes en Europe ou en Amérique du Nord, la distance physique jusqu'aux serveurs en Chine impose une latence de base incompressible, à laquelle s'ajoutent la gigue et les pertes de paquets sur la liaison internationale, qui se traduisent par des saccades et des déconnexions.

Ce que fait l'« accélération », c'est faire passer votre trafic par une meilleure ligne vers la Chine, avec moins de détours et moins de pertes de paquets. Elle transforme une connexion instable et pleine de pertes en connexion stable, et pour la plupart des jeux, c'est toute la différence entre jouable et injouable.

## Choisir le point d'entrée

La région choisie est le pays où le trafic ressort : pour les jeux sur serveurs chinois, choisissez la **région Chine**, et c'est une IP chinoise qui sort. Ne choisissez pas des régions comme l'Allemagne ou la France, qui ne transportent pas l'UDP : les jeux n'arrivent pratiquement pas à s'y connecter. Testez-en plusieurs et jugez d'après la latence affichée dans le jeu.

## Choisir le protocole

Les jeux supportent mal les pertes de paquets : préférez les protocoles qui passent par l'UDP et évitez les régions qui ne prennent pas en charge l'UDP. Les protocoles de type TCP retransmettent en cas de perte, et la latence s'envole.

## Diffusion en direct

Douyin, Kuaishou, Douyu et Huya restreignent les IP étrangères de façons différentes ; la plupart se regardent, mais avec une définition limitée. Passer sur une IP chinoise débloque toutes les options de définition. Le direct est un flux continu à haut débit : choisissez un point d'entrée qui a de la bande passante.

## Vérification d'identité

Les jeux sur serveurs chinois exigent une vérification d'identité sous nom réel. C'est une exigence liée au compte, qui n'a rien à voir avec l'IP : changer d'IP ne la résout pas.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=china-access-06) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=china-access-06) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
