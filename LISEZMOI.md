# BedRemote 3.0 Universal Media Remote

Votre téléphone devient la télécommande des médias de votre PC : vidéos de Chrome/Edge, Spotify, Lecteur multimédia,
VLC… 100 % local : pas de compte, pas de cloud, pas d'abonnement. Le média reste sur le PC.

## Installer (3 minutes)
1. Lancez **BedRemote-Setup.exe** (pas besoin d'être administrateur).
   Le logiciel n'est pas signé numériquement : Windows peut afficher « Windows a protégé votre ordinateur » →
   **Informations complémentaires → Exécuter quand même**. Ne désactivez jamais SmartScreen ou Defender.
   *Sans installation :* décompressez **BedRemote-Portable.zip** et lancez `BedRemote.exe`.
2. Onglet **Accueil** : scannez le **QR code** avec le téléphone (même Wi-Fi que le PC). Le code est à usage unique :
   un nouveau QR s'affiche pour le téléphone suivant. iPhone : Safari → Partager → « Sur l'écran d'accueil ».
3. **Vidéos du navigateur (facultatif)** : onglet **Navigateur**, suivez les 3 étapes pour ajouter l'extension, puis
   cliquez « Autoriser sur tous les sites » sur la page qui s'ouvre. *Spotify et les applications Windows n'en ont pas besoin.*
4. **VLC (facultatif)** : onglet **Médias** → « Configurer VLC… » (active son interface locale protégée, avec votre accord).

Lancez un média : BedRemote le trouve seul. Plusieurs médias ouverts ? Touchez la source voulue en haut du téléphone.

## Si ça ne marche pas
- **« PC injoignable »** : même Wi-Fi ? Réseau Windows en « Privé » ? Sinon Réglages → **Autoriser pare-feu**.
- **Rien n'est détecté** : onglet **Diagnostic**, il explique pourquoi (extension, autorisation des sites, application…).
- **« Code expiré »** sur le téléphone : rescannez le QR code affiché sur le PC.
- **Un bouton ne fait rien sur un site** : le mode « clic calibré » (onglet Calibration, F8) reste disponible.

## Partager avec un ami
Envoyez-lui `BedRemote-Setup.exe` (ou le .zip portable) et le dossier `Extension` si besoin. Son installation crée ses
propres secrets et son propre QR code : vos téléphones ne peuvent pas piloter son PC, et inversement.

## Vie privée et sécurité
BedRemote ne lit que l'état des lecteurs (position, durée, pause, titre, artiste) et ne l'envoie qu'à votre téléphone,
sur votre réseau local. Aucun cookie, identifiant, historique ou flux vidéo n'est lu ; aucune télémétrie.
La liaison téléphone ↔ PC est en **HTTP local non chiffré** : utilisez-la sur un réseau privé de confiance.
Détails : CONFIDENTIALITE.md. Téléphones et extensions appairés : onglet **Appareils** (révocation un par un).
