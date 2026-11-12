# Sécurité / Security

## Mises à jour signées
BedRemote vérifie chaque mise à jour **avant** de l'analyser :
- Le manifeste (`updates/stable.json`) est signé en **Ed25519**. La signature (`stable.json.sig`) est vérifiée avec la clé publique intégrée à l'application :
  ```
  /DOFEoLFbZBJhb/BxrRzRpioMWIdXeCgZiH4a5mBP9c=
  ```
- La clé privée correspondante n'est **jamais** publiée. Elle n'est pas dans ce dépôt, ni dans un service d'intégration continue, ni chez un hébergeur. La signature se fait hors ligne, sur le poste de publication.
- L'application refuse :
  - une signature invalide ;
  - un retour en arrière (version ou date déjà vues) ;
  - une version inférieure ou égale à celle installée ;
  - un fichier dont la taille ou le SHA-256 diffère du manifeste ;
  - toute redirection vers un autre hôte.
- Le canal est publié sur GitHub Pages : `https://archo-dev.github.io/bedremote-releases/updates/`. Les fichiers sont servis par le même hôte que le manifeste.

BedRemote 3.0.0 n'a pas d'adresse de mise à jour configurée. Le canal sert aux versions suivantes.

## Signaler une vulnérabilité
Ouvre un ticket **sans détail exploitable** en demandant un contact privé, ou utilise « Report a vulnerability » (GitHub private vulnerability reporting) si le bouton est disponible sur ce dépôt.

---

Updates are verified before they are parsed: an Ed25519-signed manifest (public key above), anti-rollback, and size and SHA-256 checks on every file. The private key is never published and signing happens offline. To report a vulnerability, use GitHub private vulnerability reporting, or open an issue without exploitable details.
