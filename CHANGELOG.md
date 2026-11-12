# Journal des versions

## 3.0.0 Universal Media Remote — 2026-11-12
### Applications Windows (nouveau)
- Sessions multimédias Windows (GlobalSystemMediaTransportControlsSessionManager, liaisons WinRT officielles) : Spotify,
  Lecteur multimédia, applications de musique/podcasts, navigateurs sans extension. Métadonnées (titre, artiste, album,
  illustration fournie localement), état, position, et **seulement les commandes annoncées par l'application**.
- Volume **indépendant par application** (sessions audio Windows du processus, jamais une autre application).
- VLC : interface web officielle limitée à 127.0.0.1, mot de passe fort, assistant avec accord explicite et sauvegarde de vlcrc.
- Sélecteur universel de sources (navigateur + Windows), mode automatique stable (pas de bascule intempestive) ou verrouillé ;
  déduplication navigateur/Windows (l'extension, plus capable, est prioritaire). Minuteur « fin du morceau » pour la musique.
### V2.1 — fiabilisation
- Volume vérifié avec nouvelle tentative (corrige Vimeo), reprise vérifiée (corrige Wikimedia/fichiers directs),
  lecteurs `<audio>`, Media Session (artiste/album), délais de vérification adaptés.
- Netflix clarifié : limitation de recherche = *précaution technique non testée*, pas un résultat.
### V2.2 — génériques intelligents
- Mode A (boutons natifs) conservé ; mode B : chapitres officiels « Intro/Récap » du lecteur ; mode C : plages
  personnalisées depuis le téléphone (épisode, saison, série), automatiques seulement avec identifiant fiable, sinon
  proposées avec confirmation ; plusieurs plages (générique + récap).
- Bibliothèque : 72 profils (32 nouveaux, dont 12 audio), statuts « Partiellement vérifié »/« Testé sur fixtures »…,
  limitations typées (Confirmé / Précaution technique / Hypothèse), profils personnels `custom_profiles.json` (données uniquement).
### V2.3 — extensions prêtes pour les boutiques
- Accès aux sites en **permission facultative** accordée par l'utilisateur (tous les sites ou site par site), scripts
  enregistrés dynamiquement ; ZIP Chrome et Edge sans clé ; dossier `Publication/` (fiches, justifications, confidentialité,
  questionnaires, instructions). Aucune publication effectuée.
- Appairage de l'extension par **secret propre à l'installation + défi HMAC** ; un autre identifiant (boutique) doit être
  approuvé dans BedRemote.
### V2.4 — mises à jour sécurisées
- Manifeste signé Ed25519 (clé publique intégrée, clé privée hors projet), HTTPS uniquement, SHA-256 + taille, anti-retour
  arrière et anti-rejeu, installation silencieuse, retour automatique à la version précédente en cas d'échec, réglages conservés.
  Canal non configuré tant qu'aucun hébergement officiel n'existe.
### Sécurité / appairage
- Nouveaux téléphones : code d'appairage à usage unique (10 min) dans le fragment de l'URL, jeton par appareil stocké haché,
  révocable un par un. L'ancien lien permanent reste accepté (désactivable) pour les raccourcis existants.
### Interfaces
- Téléphone : sélecteur de sources, modes vidéo / musique / générique, aléatoire/répétition/arrêt si disponibles,
  générique personnalisé, illustration, paysage, grand texte, mode nuit.
- Windows : onglets Médias, Génériques, Appareils (téléphones, extensions, approbations), mises à jour, assistant de premier lancement.

## 2.0.0 Universal — 2026-11-12
### Moteur universel (extension BedRemote Universal, Manifest V3, Chrome/Edge)
- Contrôle **direct** des lecteurs HTML5 (HTMLMediaElement) : lecture, pause explicite, lecture/pause, recherche précise,
  ±10 s, volume du lecteur, muet, vitesse — **sans souris ni premier plan**, onglet ou navigateur en arrière-plan.
- Détection des vidéos ajoutées dynamiquement, remplacées, dans les iframes (même d'une autre origine), en shadow DOM
  (profils concernés), navigation SPA, vidéos en direct (LIVE), plusieurs vidéos par page.
- Reconnaissance de la technologie (Video.js, JW Player, Plyr, Shaka, Flowplayer, MediaElement.js, MSE hls.js/dash.js).
- Canal local WebSocket 127.0.0.1 : reprise automatique après suspension du service worker (≈ 1 s mesurée),
  aucune activité quand aucune vidéo n'est ouverte depuis 5 min.
- Sélection automatique du lecteur pertinent (lecture en cours, taille, visibilité, profil) : publicités, miniatures et
  vidéos de fond écartées. Sélection manuelle et **verrouillage** depuis le téléphone.

### Bibliothèque de sites
- 40 profils déclaratifs (39 plateformes + générique) avec domaines, capacités, sélecteurs, langues, version et statut de
  validation honnête. Aucun code exécuté depuis un profil ; profils invalides écartés.
- Serveurs auto-hébergés (Jellyfin, Emby, Plex, PeerTube) détectés par marqueurs de page.

### Automatisation
- Épisodes automatiques liés au **lecteur ciblé** uniquement (fin de pub / aperçu / autre onglet ignorée), une seule
  fois, détection de l'enchaînement natif du site, bouton « épisode suivant » du site puis secours calibré V1.2.
- **Génériques** : passage automatique (désactivable) uniquement via le bouton « Passer l'intro / le récapitulatif » du
  site ; jamais de saut à l'aveugle ; « Ignorer la publicité » jamais cliqué. Bouton manuel affiché seulement s'il existe.
- Minuteur : 15/30/45/60/**90** min et **fin de l'épisode** ; annule la transition en attente, met en pause le seul
  lecteur ciblé, bloque la relance automatique du site, suspend les épisodes auto jusqu'à la prochaine action.

### Télécommande mobile V2
- Titre, saison/épisode, temps écoulé, durée, **temps restant**, barre de progression interactive (interpolée entre
  deux synchronisations), état chargement/LIVE, vitesse, volume du lecteur + volume Windows, sélection du lecteur,
  mode de contrôle affiché, mode nuit.

### Application Windows
- Onglets Accueil / Navigateurs (assistant d'extension) / Bibliothèque (recherche) / Calibration (F8 inchangée) /
  Paramètres / Diagnostic. Réduction dans la zone de notification (option).

### Distribution
- Exécutable autonome (PyInstaller, sans Python), installateur par utilisateur sans administrateur (Inno Setup),
  version portable, extension versionnée à identifiant fixe. Exécutables **non signés**.

### Sécurité
- Canal extension réservé à l'identifiant officiel de l'extension + boucle locale ; page web tierce refusée (Origin),
  anti DNS-rebinding (Host), limitation des requêtes et blocage après jetons faux, validation stricte des valeurs,
  jeton de 128 bits pour les nouvelles installations, révocation par nouveau jeton.

### Compatibilité V1.2
- Configuration migrée sans modification (jeton, port, calibrations, profils) + copie `config.v1-backup.json`.
- L'ancienne extension reste acceptée jusqu'à la connexion de la V2, puis la route V1.2 est fermée automatiquement.
- Tous les tests V1.2 passent sur la V2.

## 1.2 — minuteur, épisode suivant auto (extension), reconnexion, profils de calibration, démarrage Windows.
