# 02 · Flasher le firmware vous-même : du système d'origine au nôtre, pas à pas (avec vidéo)

> Tutoriel vidéo (environ deux minutes et demie, commentaire en anglais ou en chinois) : https://www.leotun.com/fr/video/router-flash?utm_source=github&utm_content=router-02
>
> Version sur le site : https://www.leotun.com/fr/guides/router-flash?utm_source=github&utm_content=router-02

Ce guide s'adresse à ceux qui ont déjà un routeur dont le modèle figure dans la liste des modèles pris en charge. Votre routeur tourne encore sous son système d'origine ; nous allons de l'ouverture du site jusqu'à toute la maison connectée : sur quoi cliquer à chaque étape, ce que vous verrez, et où l'on se trompe le plus souvent. La démonstration utilise un GL.iNet GL-MT3000. Les autres modèles suivent les mêmes étapes, seule l'interface d'administration d'origine change d'aspect. Si vous préférez ne pas le faire vous-même, un routeur préinstallé est plus simple : voir [01](01-plug-and-play-router.md). Pour choisir un modèle, voir [07](07-which-router-to-buy.md).

## Avant de commencer

- **Vérifiez que votre modèle est pris en charge.** Connectez-vous, ouvrez la section **Routeur** et cherchez votre modèle par marque. La révision matérielle indiquée après le nom du modèle (v1, v2, etc.) doit aussi correspondre.
- **Votre compte doit être actif.** Les formules Personnel, Famille et Entreprise permettent toutes d'utiliser un routeur.
- **Prévoyez un câble réseau.** Le port WAN du routeur se branche sur votre box ou votre routeur amont. Pendant le flash, mieux vaut aussi relier l'ordinateur au routeur par câble : c'est plus stable que le Wi-Fi.
- **Gardez une copie du firmware d'origine.** Téléchargez le firmware d'origine de votre modèle sur le site du fabricant, au cas où vous voudriez revenir en arrière.

## Étape 1 : générer le firmware sur le site

1. Connectez-vous et cliquez sur **Routeur** dans la barre de navigation.
2. Trouvez votre modèle et cliquez sur **Firmware**, ou descendez jusqu'à « Compiler le Firmware » et choisissez le modèle dans la liste des marques.
3. Cliquez sur **Démarrer la compilation**.

Quelques points à savoir :

- **Une compilation prend 3 à 5 minutes.** Le firmware est fabriqué pour votre compte sur le moment ; ce n'est pas un fichier tout prêt. Aux heures chargées, la compilation peut attendre dans une file. La page vous le signale : patientez, inutile de cliquer à nouveau.
- **Un e-mail vous prévient quand c'est prêt.** La ligne correspondante dans « Compilations récentes » passe à « Terminé » et un avis arrive dans votre boîte de réception.
- **La langue de l'interface du firmware suit celle du site.** Si vous utilisez le site en français, les pages d'administration du routeur seront en français. Pour une autre langue, changez d'abord la langue du site, puis lancez la compilation.
- **Le lien de téléchargement est valable un jour.** S'il a expiré, relancez simplement une compilation.

## Étape 2 : télécharger et décompresser

1. Dans « Compilations récentes », cliquez sur **Télécharger**. Vous obtenez un fichier zip.
2. Ouvrez votre dossier Téléchargements et **décompressez**-le.
3. Le dossier extrait contient le fichier du firmware.

Quel fichier utiliser :

| Votre routeur tourne actuellement sous | Fichier à utiliser |
|---|---|
| Le système d'origine GL.iNet (le cas de la vidéo) | celui qui se termine par `sysupgrade.bin` |
| Le système d'origine d'une autre marque | celui dont le nom contient `factory` |
| Déjà notre firmware, pour une mise à jour | celui dont le nom contient `sysupgrade` |

Si le zip ne contient qu'un seul fichier, c'est celui-là.

> ⚠️ **Ce firmware est à vous seul.** Il contient les informations de votre compte pour que le routeur puisse se connecter tout seul après le flash. N'envoyez ce fichier à personne et ne le publiez pas.

## Étape 3 : le flasher depuis l'interface d'origine

Avec GL.iNet comme exemple :

1. Reliez l'ordinateur au routeur, ouvrez l'interface d'administration d'origine dans un navigateur (`http://192.168.8.1` sur GL.iNet) et connectez-vous avec le mot de passe administrateur.
2. Dans le menu de gauche, ouvrez **System** → **Upgrade** (système → mise à jour).
3. Passez à l'onglet **Firmware Local Upgrade** (mise à jour locale du firmware).
4. Cliquez sur la zone d'envoi et choisissez le fichier de firmware extrait.
5. Attendez que la vérification affiche **Pass** (réussie).
6. **Désactivez « Keep Settings » (conserver les réglages).** C'est l'étape la plus souvent oubliée. Les deux systèmes n'ont pas le même format de configuration, et garder les anciens réglages provoque toutes sortes de problèmes bizarres.
7. Cliquez sur **Install** (installer).

La page affiche alors une mise à jour avec redémarrage et un anneau de progression. **Comptez deux à trois minutes. Ne débranchez pas le routeur et ne fermez pas la page pendant ce temps.** Il est normal que la page ne se charge plus une fois la progression terminée : le routeur tourne désormais sous un autre système, et son adresse comme son Wi-Fi ont changé. Voir l'étape suivante.

Autres marques : cherchez « Firmware Upgrade », « System Upgrade » ou « Local Upgrade » (ou leur équivalent en français) dans l'interface d'origine, envoyez le fichier, et là encore ne conservez pas les réglages.

## Étape 4 : rejoindre le nouveau Wi-Fi

Après le flash, l'ancien nom de Wi-Fi disparaît et un nouveau apparaît :

- **Nom du Wi-Fi : `www.anyfq.com`**
- **Mot de passe du Wi-Fi : `www.anyfq.com`** (identique au nom)

Ordinateurs et téléphones doivent **passer sur ce Wi-Fi** pour accéder à Internet ou ouvrir la page d'administration du routeur. Un ordinateur relié au routeur par câble n'a rien à changer.

La nouvelle adresse d'administration est `http://192.168.11.1` (tapez vous-même le `http://` du début).

## Étape 5 : attendre qu'il se connecte tout seul

Pas d'identifiants à saisir, pas de région à choisir. **Tant que votre compte est actif, le routeur se connecte tout seul en moins de 10 minutes.** Ensuite, tous les appareils de ce Wi-Fi passent automatiquement par le service, téléviseurs, box TV et consoles de jeu compris.

Pour vérifier qu'il est connecté, ouvrez depuis un appareil branché sur le routeur un site que vous ne pouvez pas atteindre d'habitude, ou regardez l'état dans la page d'administration.

## Deux choses à faire ensuite

1. **Changez les mots de passe par défaut.** Le mot de passe du Wi-Fi et celui de l'administration sont, au départ, des valeurs par défaut publiques. Changez les deux dans la page d'administration.
2. **Un signal Wi-Fi faible juste après le flash est normal.** Le routeur doit d'abord se connecter une fois à Internet pour déterminer dans quel pays il se trouve, avant de monter la puissance d'émission au niveau autorisé localement. Branchez le câble réseau et laissez-le se connecter.

## Remplacer un ancien routeur par un nouveau

Un compte n'est lié qu'à un seul routeur à la fois. Si votre compte a déjà servi sur un autre routeur :

1. Connectez-vous, ouvrez la section **Routeur** : sous le titre « Compiler le Firmware », vous voyez le modèle **Lié**, avec **Délier** à côté.
2. Cliquez sur Délier. C'est possible même si l'ancien routeur est en panne ou n'est pas sous la main.
3. Rien à faire sur le nouveau routeur : il **se connecte automatiquement** et se lie à votre compte.

Si vous flashez le nouveau routeur avant de délier l'ancien, ce n'est pas grave non plus. Le nouveau routeur attend et se connecte tout seul dès que vous déliez.

Le détail des règles est dans [05 · Liaison par adresse MAC et remplacement du routeur](05-mac-binding-and-replacing.md).

## Et si mon compte expire

Après l'expiration, le routeur ne fait plus passer le trafic par le service, mais votre réseau domestique continue de fonctionner normalement. **Dès que vous renouvelez, le routeur reprend tout seul : pas besoin de se reconnecter, ni de reflasher.**

## Il ne s'est pas connecté tout seul : comment vérifier

Si rien ne marche après une dizaine de minutes, vérifiez dans cet ordre :

1. **La connexion Internet elle-même fonctionne-t-elle ?** Depuis un appareil branché sur le routeur, ouvrez n'importe quel site ordinaire. Si cela échoue, le problème vient du câble ou de la box : vérifiez que le câble du port WAN est bien enfoncé.
2. **Le compte a-t-il expiré ?** Connectez-vous au site et regardez la date d'expiration. Après un renouvellement, attendez quelques minutes.
3. **Le compte est-il encore lié à l'ancien routeur ?** Dans la section Routeur, regardez le modèle lié. Si ce n'est pas ce routeur, cliquez sur Délier.
4. **Redémarrez le routeur une fois.** Débranchez-le, attendez dix secondes, rebranchez-le et laissez-lui deux à trois minutes.
5. **Connectez-vous manuellement.** Ouvrez `http://192.168.11.1` et connectez-vous au routeur avec l'utilisateur `root` et le mot de passe `www.anyfq.com`. Allez ensuite dans **Services** → **VPN**, saisissez l'e-mail et le mot de passe de votre compte, puis enregistrez.

Toujours bloqué ? Demandez dans le groupe en indiquant le modèle du routeur et l'étape de la liste ci-dessus où vous en êtes.

## Quand il vaut mieux ne pas flasher soi-même

Le modèle n'est pas dans la liste, la révision matérielle ne correspond pas, ou c'est un vieux routeur sans mode de récupération. Dans ces trois cas, un routeur préinstallé vous évitera bien des ennuis.

## Si le flash tourne mal

La plupart des routeurs ont un mode de récupération : débranchez l'alimentation, maintenez le bouton reset enfoncé en la rebranchant, gardez-le enfoncé quelques secondes, puis reliez un ordinateur par câble et envoyez le firmware d'origine en suivant les instructions du fabricant. Pour GL.iNet, cherchez « uboot » dans sa documentation. C'est à cela que sert le firmware d'origine que vous avez gardé.

## Questions fréquentes

**Le flash annule-t-il la garantie ?** Cela dépend du fabricant. Les routeurs GL.iNet reposent dès le départ sur un système open source et peuvent être reflashés avec leur firmware d'origine.

**Puis-je revenir au firmware d'origine ?** Oui. Utilisez le mode de récupération décrit dans « Si le flash tourne mal » pour envoyer le firmware d'origine.

**Un même fichier de firmware peut-il servir sur deux routeurs ?** Non. Le firmware est généré par compte, et un compte n'est lié qu'à un seul routeur à la fois.

**Faut-il recompiler si je change de compte ?** Non. Déconnectez-vous dans la page d'administration et reconnectez-vous avec le nouveau compte.

**Les futures mises à jour exigeront-elles un nouveau flash ?** Les mises à jour courantes sont récupérées par le routeur tout seul ; vous n'avez rien à faire. Seule une version majeure demande une nouvelle compilation et un flash du fichier sysupgrade, et le site l'annoncera le moment venu.

---
Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=router-02) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=router-02) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 4 heures ; invitez un ami qui paie et vous recevez chacun 15 points (environ 15 jours en formule Personnel), une offre durable
