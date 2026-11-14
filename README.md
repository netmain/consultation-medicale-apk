# La Consultation Médicale — APK

Ce dépôt public ne contient **aucun code source** : uniquement les APK publiés
et leurs sommes de contrôle. Le code reste privé, ce qui permet à l'application
de vérifier les mises à jour sans jeton.

## Télécharger

Ouvrir [Releases](../../releases) et prendre le dernier fichier :

| Canal | Fichier | Usage |
|---|---|---|
| stable | `CONSULTATION-<version>-<code>-release.apk` | usage courant |
| test | `CONSULTATION-<version>-<code>-debug.apk` | diagnostic |

Les deux canaux portent l'identifiant `com.net.consult` et la même clé de
signature : ils s'installent l'un par-dessus l'autre, sans perte de données.
Android refusera en revanche un APK signé avec une autre clé — c'est voulu.

## Installer

1. Télécharger l'APK sur le téléphone.
2. Ouvrir le fichier, autoriser « installer des applications inconnues » pour
   le navigateur ou le gestionnaire de fichiers.
3. Confirmer l'installation.

Depuis l'application : **Paramètres → Mises à jour**, choisir le canal,
vérifier, installer. Le téléchargement est vérifié par SHA-256 avant d'être
proposé à l'installateur.

## Vérifier un fichier

`SHA256SUMS.txt` est joint à chaque release, et les empreintes sont recopiées
dans les notes. Sous Windows :

```powershell
Get-FileHash .\CONSULTATION-*.apk -Algorithm SHA256
```

La valeur doit correspondre, octet pour octet, à la ligne du même fichier.

## Anciennes versions

Aucune release n'est supprimée ni remplacée : chaque build crée une nouvelle
version, les précédentes restent téléchargeables.
