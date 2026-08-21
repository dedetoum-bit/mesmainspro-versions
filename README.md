# Mes Mains Pro — canal de mise à jour

Ce dépôt est le **canal officiel de mise à jour** de l'application Mes Mains Pro.

- **`update.token`** (racine, branche `main`) — le manifeste de la dernière version,
  **signé Ed25519** par l'éditeur. Format : `payload.signature` (base64url).
  Le payload contient `{version, url, sha256, notes, date}`.
- **Releases** — les installateurs Windows (`MesMainsPro_Setup_<version>.exe`).

## Sécurité

L'application n'exécute **jamais** un fichier provenant d'ici sans avoir vérifié :

1. la **signature Ed25519** du manifeste (clé publique embarquée dans l'app) ;
2. l'empreinte **SHA-256** de l'installateur téléchargé, re-vérifiée juste avant le lancement ;
3. **HTTPS obligatoire**, redirections re-validées à chaque saut.

Un fichier modifié par un tiers (même dans ce dépôt) est donc simplement **refusé** par
l'application. Seul le détenteur de la clé privée peut publier une mise à jour acceptée.

## Site

https://mesmains.pro
