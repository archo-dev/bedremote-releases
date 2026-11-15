# BedRemote — téléchargements officiels / official downloads

Ton téléphone devient la télécommande des médias de ton PC Windows : vidéos de Chrome et Edge, Spotify, Lecteur multimédia, VLC. 100 % local : pas de compte, pas de cloud, pas d'abonnement.

**Site officiel : https://bedremote.vercel.app** · [English below](#english)

Ce dépôt ne contient **pas** le code source de BedRemote. Il sert uniquement à distribuer les versions officielles, leurs notes et leurs sommes de contrôle, et à héberger le canal de mises à jour signé.

## Télécharger (dernière version)

| Fichier | Usage |
|---|---|
| [BedRemote-Setup.exe](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Setup.exe) | Installateur Windows. Installation pour l'utilisateur, sans droits administrateur. |
| [BedRemote-Portable.zip](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Portable.zip) | Version portable : extraire puis lancer `BedRemote.exe`. |
| [BedRemote-Chrome-Extension.zip](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Chrome-Extension.zip) | Extension Chrome, installation manuelle. **Recommandé : [Chrome Web Store](https://chromewebstore.google.com/detail/bedremote-universal/hdcomibojibjfngfgnhdmmfjeogiobjj)**. |
| [BedRemote-Edge-Extension.zip](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Edge-Extension.zip) | Même extension pour Edge, installation manuelle. |
| [SHA256SUMS.txt](https://github.com/archo-dev/bedremote-releases/releases/latest/download/SHA256SUMS.txt) | Sommes de contrôle SHA-256. |

Toutes les versions : https://github.com/archo-dev/bedremote-releases/releases

### Avertissement Windows
Les exécutables **ne sont pas signés numériquement**. Windows SmartScreen peut afficher « Windows a protégé votre ordinateur ». Vérifie d'abord la provenance (cette page) et l'empreinte SHA-256, puis décide. **Ne désactive jamais SmartScreen ni Defender.**

Vérifier une empreinte dans PowerShell :
```powershell
Get-FileHash .\BedRemote-Setup.exe -Algorithm SHA256
```

### Extension
**Chrome :** installe « BedRemote Universal » depuis le [Chrome Web Store](https://chromewebstore.google.com/detail/bedremote-universal/hdcomibojibjfngfgnhdmmfjeogiobjj). BedRemote 3.0.1 la reconnaît automatiquement (avec la 3.0.0 : onglet **Appareils** → Extensions de navigateur → sélectionne-la → **Autoriser**).

**Edge (ou installation manuelle) :**
1. Extraire `BedRemote-Chrome-Extension.zip` dans un dossier que tu conserves.
2. Ouvrir `chrome://extensions` (ou `edge://extensions`), activer le **mode développeur**.
3. **Charger l'extension non empaquetée** → choisir le dossier extrait.
4. Sur la page qui s'ouvre, autoriser l'accès aux sites (tous ou site par site).

L'extension ne fonctionne qu'avec l'application Windows BedRemote installée sur le même PC.

## Documentation
- [LISEZMOI.md](LISEZMOI.md) — installation et dépannage
- [CHANGELOG.md](CHANGELOG.md) — notes de version
- [COMPATIBILITE.md](COMPATIBILITE.md) — sites et applications, avec leur niveau de validation
- [CONFIDENTIALITE.md](CONFIDENTIALITE.md) — politique de confidentialité (aussi sur https://bedremote.vercel.app/privacy/)
- [CONDITIONS.md](CONDITIONS.md) — conditions d'utilisation
- [SECURITY.md](SECURITY.md) — mises à jour signées et signalement de vulnérabilité

## Support
Questions, problèmes : [Issues](https://github.com/archo-dev/bedremote-releases/issues). N'y publie jamais ton jeton d'appairage, ton adresse IP ou des captures montrant des données personnelles.

---

## English

BedRemote turns your phone into a remote for media on your Windows PC: Chrome and Edge videos, Spotify, Windows Media Player, VLC. Fully local: no account, no cloud, no subscription. **Website: https://bedremote.vercel.app**

This repository does **not** contain BedRemote's source code. It only distributes official builds, release notes and checksums, and hosts the signed update channel.

**Downloads (latest version):**
- [Windows installer](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Setup.exe)
- [Portable](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Portable.zip)
- [Chrome extension](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Chrome-Extension.zip)
- [Edge extension](https://github.com/archo-dev/bedremote-releases/releases/latest/download/BedRemote-Edge-Extension.zip)
- [SHA-256 checksums](https://github.com/archo-dev/bedremote-releases/releases/latest/download/SHA256SUMS.txt)

The executables are **not code-signed**, so SmartScreen may warn you. Check the SHA-256 and keep SmartScreen and Defender enabled.

Chrome extension: [Chrome Web Store](https://chromewebstore.google.com/detail/bedremote-universal/hdcomibojibjfngfgnhdmmfjeogiobjj) — recognized automatically by BedRemote 3.0.1 (with 3.0.0, approve it once in the "Appareils" tab). Edge: load the extracted ZIP in developer mode. The app's documentation is in French. Privacy policy: https://bedremote.vercel.app/en/privacy/
