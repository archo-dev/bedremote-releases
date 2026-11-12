# Politique de confidentialité — BedRemote et l'extension « BedRemote Universal »

Dernière mise à jour : 12 novembre 2026

Éditeur : BedRemote, projet indépendant publié par archo-dev sur GitHub. Contact : https://github.com/archo-dev/bedremote-releases/issues
Adresse publique de cette politique : https://bedremote.vercel.app/privacy/ (version anglaise : /en/privacy/).

## En bref
- BedRemote fonctionne **entièrement sur votre réseau local**. Pas de compte, pas de cloud, pas de publicité, pas de télémétrie.
- L'extension lit seulement **l'état des lecteurs vidéo et audio** des sites que **vous** avez autorisés, et ne l'envoie
  **qu'à l'application BedRemote installée sur le même PC** (adresse 127.0.0.1).
- Rien n'est vendu, rien n'est partagé, rien n'est envoyé à l'éditeur.

## Ce que comprend BedRemote
1. **L'application BedRemote** (Windows), installée sur votre PC.
2. **L'extension « BedRemote Universal »** (Chrome / Edge), qui relie les lecteurs du navigateur à l'application.
3. **La télécommande**, une page web servie par l'application de votre PC et ouverte sur votre téléphone, sur le même Wi-Fi.

## Données traitées par l'extension
Uniquement sur les sites que vous avez autorisés (tous les sites, ou site par site, depuis la page d'accueil de l'extension) :

| Donnée | Pourquoi | Où elle va |
|---|---|---|
| État du lecteur : lecture/pause, position, durée, volume, vitesse, « en direct » ou non | Afficher et piloter la lecture depuis le téléphone | Application BedRemote sur ce PC uniquement |
| Titre de la vidéo ou du morceau, titre de l'onglet, nom de domaine du site | Afficher ce qui est en cours et choisir le profil du site | Application BedRemote sur ce PC uniquement |
| Présence des boutons « épisode suivant » / « passer l'intro » affichés par le site | Proposer ces actions sur le téléphone | Application BedRemote sur ce PC uniquement |
| Secret d'appairage avec l'application, liste des sites autorisés, préférences | Fonctionnement de l'extension | Stockage local du navigateur |

L'extension **ne lit pas** : vos identifiants, mots de passe, cookies, formulaires, messages, données de paiement,
historique de navigation, ni le contenu des vidéos (aucune image ni aucun son n'est capturé ou transmis).
Elle ne communique avec **aucun serveur sur Internet** : sa seule connexion réseau est une WebSocket vers `127.0.0.1`
(votre propre PC). Elle n'exécute aucun code téléchargé : tout son code est contenu dans le paquet publié.

## Données traitées par l'application BedRemote
- Configuration locale (`%APPDATA%\BedRemote\`) : jeton de la télécommande, réglages, calibrations, profils personnels.
- Échanges avec votre téléphone sur le réseau local : commandes (lecture, pause, volume…) et état de la lecture.
  Ces échanges se font en HTTP local non chiffré : évitez les Wi-Fi publics non fiables.
- **Mises à jour** : BedRemote 3.0.0 ne contacte **aucun** serveur de mise à jour (adresse non configurée). Les versions
  ultérieures qui l'activeront téléchargeront en HTTPS un manifeste signé (Ed25519) depuis GitHub Pages
  (archo-dev.github.io). Comme pour toute requête web, GitHub voit votre adresse IP ; aucune autre donnée (aucun
  identifiant, aucun historique) n'est envoyée. La vérification automatique peut être désactivée dans Réglages.

## Hébergement du site et des téléchargements
Le site de présentation (bedremote.vercel.app) est hébergé par Vercel et les fichiers à télécharger par GitHub.
Ces hébergeurs traitent les données techniques de connexion (adresse IP, navigateur) selon leurs propres politiques.
Le site n'utilise ni cookie, ni traceur, ni mesure d'audience ; sa démonstration 3D fonctionne entièrement dans votre
navigateur et ne communique jamais avec un PC équipé de BedRemote.

## Partage et vente
Aucune donnée n'est vendue, louée, partagée avec des tiers, utilisée à des fins publicitaires, de profilage ou
d'évaluation de solvabilité, ni utilisée pour un autre but que la télécommande des lecteurs.

## Conservation et suppression
- L'état de lecture n'est pas conservé : il est remplacé à chaque mise à jour et disparaît à la fermeture de l'application.
- Pour tout effacer : désinstallez l'extension (son stockage local est supprimé par le navigateur) et l'application,
  puis supprimez le dossier `%APPDATA%\BedRemote\`.
- Vous pouvez retirer à tout moment l'accès d'un site depuis la page de l'extension ou les réglages du navigateur.

## Vos droits
Les données restent sur vos appareils ; l'éditeur n'en détient aucune. Pour toute question : https://github.com/archo-dev/bedremote-releases/issues.

## Enfants
BedRemote ne collecte sciemment aucune donnée, y compris d'enfants.

## Modifications
Toute modification de cette politique sera indiquée par sa date de mise à jour, et décrite dans le journal des versions.

## Marques
BedRemote est un logiciel indépendant, sans affiliation avec les plateformes dont il peut piloter le lecteur.
