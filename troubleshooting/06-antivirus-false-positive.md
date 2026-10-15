# 06 · Que faire quand votre Mac dit que l'app « est endommagée »

> Version sur le site (plus détaillée) : https://www.leotun.com/fr/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-06

La conclusion d'abord : le fichier n'est pas abîmé, et personne ne l'a modifié. Quand un double-clic sur Hiddify sur un Mac affiche « est endommagé et ne peut pas être ouvert » ou « le développeur ne peut pas être vérifié », c'est Gatekeeper, le gardien du système, qui le bloque ; suivez les étapes ci-dessous pour l'autoriser.

Sur Windows, l'installation de Hiddify ne déclenche plus d'alerte virus dans nos tests actuels. Si l'antivirus que vous avez installé le signale malgré tout, suivez le même ordre : vérifier d'abord, autoriser ensuite.

## Pourquoi il est bloqué

**Les fichiers téléchargés depuis une page web reçoivent un marqueur de quarantaine.** Quand Gatekeeper sur macOS voit ce marqueur, il bloque l'app. Le message dit tantôt « est endommagé », tantôt « le développeur ne peut pas être vérifié » ; la cause est la même.

Ce que nous faisons : le client de bureau est un **miroir non modifié** du paquet de publication du projet open source d'origine. Nous ne le modifions pas, ne le réempaquetons pas et n'y injectons rien ; nous l'hébergeons seulement sur notre propre site de téléchargement pour vous faciliter la tâche.

## Vérifiez d'abord vous-même, n'autorisez pas à l'aveugle

Autoriser une app signifie que le système cesse de la contrôler : l'ordre est donc vérifier d'abord, autoriser ensuite.

**Envoyez-le sur VirusTotal pour un second avis.** Glissez l'installateur sur [virustotal.com](https://virustotal.com/gui/home/upload). Quelques moteurs heuristiques qui le signalent pendant que tous les éditeurs reconnus le laissent passer, c'est le profil typique d'un faux positif. Si la plupart des moteurs reconnus le signalent, **ne l'installez pas** : contactez-nous directement.

Ne poursuivez qu'une fois la vérification passée. En cas de doute, contactez d'abord l'assistance et nous vérifierons le site de téléchargement.

## Trois façons de l'autoriser, de la plus ciblée à la plus large

Après le double-clic, vous pouvez voir « "Nom du client" est endommagé et ne peut pas être ouvert. Vous devriez le placer dans la corbeille. » ou « … ne peut pas être ouvert car le développeur ne peut pas être vérifié. ». Les trois étapes ci-dessous vont de la plus ciblée à la plus large ; **si la première fonctionne, n'utilisez pas la troisième**.

1. Retrouvez l'app dans « Applications » dans le Finder, faites Contrôle-clic sur l'icône (ou clic droit), choisissez « Ouvrir », puis cliquez encore sur « Ouvrir » dans la fenêtre qui s'affiche. C'est une autorisation ponctuelle, pour cette seule app.
2. Si le menu du clic droit n'offre pas de « Ouvrir » utilisable, allez dans « Réglages Système » → « Confidentialité et sécurité » et faites défiler jusqu'à la partie Sécurité. Vous verrez « L'utilisation de "Nom du client" a été bloquée car l'app ne provient pas d'un développeur identifié ». Cliquez sur « Ouvrir quand même » à droite et saisissez votre mot de passe pour confirmer.
3. Si le message dit « est endommagé », les deux premières étapes ne marchent généralement pas. Ouvrez « Terminal » et exécutez `sudo xattr -dr com.apple.quarantine` suivi du chemin de l'app (en général une `.app` dans `/Applications/`), appuyez sur Entrée, saisissez votre mot de passe de session, puis rouvrez l'app. Cette commande supprime le marqueur de quarantaine qui signale l'origine du téléchargement.

Au premier lancement, le système vous demandera aussi votre mot de passe pour autoriser l'installation d'une extension réseau. L'app ne peut prendre en charge le trafic qu'après votre accord.

Quelques rappels :

- N'utilisez la commande `xattr` **que sur des fichiers dont vous avez déjà vérifié l'origine** ; voir la section précédente pour la vérification.
- **N'utilisez pas** `sudo spctl --master-disable` pour désactiver Gatekeeper globalement. Cela coupe la protection de toute la machine, alors que « Ouvrir » par clic droit ne concerne qu'une app.
- Depuis macOS 15, Apple a durci le passage par « Ouvrir » au clic droit, et la plupart du temps il faut passer par l'étape « Réglages Système ». C'est un changement du comportement du système, pas un problème de notre paquet.
- Les Mac fournis par l'entreprise sont souvent gérés par un profil MDM, et les trois étapes ci-dessus peuvent toutes être désactivées. Ne forcez pas ; utilisez l'une des trois options ci-dessous.

## Vous ne voulez rien autoriser ? Utilisez l'une de ces trois options

Leurs clients **fonctionnent sur macOS d'un simple double-clic** et n'affichent aucun des messages ci-dessus. C'est le même compte, sans rien payer de plus :

- **Privé (client Tailscale officiel)** : fonctionne dès l'installation, idéal pour rester allumé en permanence
- **OpenVPN Connect** : l'installateur d'OpenVPN lui-même ; il suffit d'importer la configuration
- **Cisco Secure Client** : un client de niveau entreprise, déjà installé sur beaucoup d'ordinateurs professionnels

## FAQ

**Votre programme contient-il vraiment un virus ?**
Non. C'est un miroir non modifié du paquet de publication officiel du projet open source d'origine. Mais vous n'êtes pas obligé de nous croire sur parole ; la méthode pour vérifier vous-même est donnée plus haut : envoyez-le sur VirusTotal et regardez comment se répartissent les verdicts des moteurs.

**Sera-t-il encore signalé sur Windows ?**
Actuellement, dans nos tests, la sécurité intégrée de Windows ne signale plus l'installation de Hiddify. Si l'antivirus que vous avez installé le signale malgré tout, faites d'abord vérifier le fichier par VirusTotal, puis, une fois la vérification passée, déclarez le dossier d'installation de Hiddify comme approuvé dans l'antivirus. Ne désactivez pas la protection en temps réel pour l'installer.

**Il ne s'ouvre pas après l'installation sur Mac. Le téléchargement est-il corrompu ?**
Non. Il ne s'ouvre pas parce que Gatekeeper le bloque. Réglez cela avec les trois façons de l'autoriser décrites plus haut.

**Faut-il installer un antivirus sur le Mac en complément ?**
Non. Ce qui vous bloque sur macOS, c'est le Gatekeeper intégré au système, pas un antivirus. Installer un antivirus tiers ne fera pas disparaître ce message, et peut ajouter de nouveaux blocages.

**Ce problème existe-t-il sur téléphone ?**
Sur iOS, avec une installation depuis l'App Store, le problème n'existe pas. Android avertit parfois au sujet des sources inconnues ; il suffit d'autoriser.

---

Rédigé par l'équipe [LeoTun](https://www.leotun.com/fr?utm_source=github&utm_content=troubleshooting-06) · Une question ? Consultez la [page de contact](https://www.leotun.com/fr/contact?utm_source=github&utm_content=troubleshooting-06) (groupes, e-mail et assistance y sont tous indiqués) · Inscrivez-vous pour un essai gratuit de 24 heures ; invitez un ami qui paie et vous recevez chacun 20 jours en formule Personnel, une offre permanente
