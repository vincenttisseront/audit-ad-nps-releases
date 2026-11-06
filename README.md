# Audit AD NPS — versions publiées

Ce dépôt contient uniquement les **versions compilées** de l'application *Audit AD · AD CS · NPS · GPO*
(client lourd Windows d'audit Active Directory, en lecture seule par défaut). Le code source est privé.

## Installation

1. Ouvrir la page [Releases](https://github.com/vincenttisseront/audit-ad-nps-releases/releases) et télécharger
   `AuditAdNps-win-x64-vX.Y.Z.zip`.
2. Vérifier l'empreinte avant d'extraire :
   ```powershell
   (Get-FileHash .\AuditAdNps-win-x64-vX.Y.Z.zip -Algorithm SHA256).Hash
   ```
   Elle doit correspondre au contenu de `AuditAdNps-win-x64-vX.Y.Z.zip.sha256` (aussi rappelé dans les notes de version).
3. Extraire l'archive entière et lancer `AuditAdNps.exe` (autonome : aucun runtime .NET à installer, aucune élévation demandée).

## Mises à jour

L'application vérifie elle-même ce dépôt (au démarrage et via le bouton **Mises à jour**) :
- téléchargement par l'API GitHub en HTTPS, sans jeton ;
- **installation refusée si l'empreinte SHA-256 est absente ou différente** ;
- nouvelle version extraite dans un dossier voisin `AuditAdNps-win-x64-vX.Y.Z`, la version en cours n'est pas modifiée ;
- la nouvelle version n'est jamais lancée automatiquement.

## Contenu d'une version

| Fichier | Rôle |
|---|---|
| `AuditAdNps-win-x64-vX.Y.Z.zip` | Application publiée (dossier autonome win-x64) |
| `AuditAdNps-win-x64-vX.Y.Z.zip.sha256` | Empreinte SHA-256 de l'archive |
