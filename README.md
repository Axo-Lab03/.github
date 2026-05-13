# Axo-Lab · `.github`

Repo spécial GitHub contenant la **vitrine publique de l'organisation Axo-Lab03** et les **fichiers communautaires par défaut** appliqués à tous les repos de l'organisation qui ne fournissent pas leur propre équivalent.

> 📖 GitHub documentation officielle : [Creating a default community health file](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)

---

## Contenu

### Vitrine publique

| Fichier | Rôle |
|---|---|
| [`profile/README.md`](./profile/README.md) | Affiché en page d'accueil de l'organisation sur [github.com/Axo-Lab03](https://github.com/Axo-Lab03) |

### Fichiers communautaires (community health files)

Appliqués automatiquement à tout repo public de l'organisation qui ne fournit pas son propre fichier équivalent.

| Fichier | Rôle |
|---|---|
| [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md) | Code de conduite (Contributor Covenant v2.1 traduit) |
| [`CONTRIBUTING.md`](./CONTRIBUTING.md) | Conventions de contribution (branches, commits, PR) |
| [`SECURITY.md`](./SECURITY.md) | Politique de divulgation responsable des vulnérabilités |
| [`SUPPORT.md`](./SUPPORT.md) | Canaux d'assistance et de contact |
| [`PULL_REQUEST_TEMPLATE.md`](./PULL_REQUEST_TEMPLATE.md) | Template par défaut des PR |
| [`ISSUE_TEMPLATE/`](./ISSUE_TEMPLATE/) | Templates d'issues (bug, feature, config) |
| [`FUNDING.yml`](./FUNDING.yml) | Sponsorship (désactivé, entité commerciale) |

### Templates partageables

| Fichier | Rôle |
|---|---|
| [`dependabot.yml`](./dependabot.yml) | Configuration Dependabot standard à copier dans `.github/` de chaque repo |
| [`workflows/reusable-node-ci.yml`](./workflows/reusable-node-ci.yml) | Workflow CI réutilisable pour les projets Node.js / TypeScript |

---

## Cascade d'application des fichiers communautaires

GitHub applique les fichiers selon l'ordre de priorité suivant (le premier trouvé gagne) :

1. Fichier dans le repo concerné (à la racine, dans `docs/`, ou dans `.github/`)
2. Fichier dans ce repo `Axo-Lab03/.github`
3. Aucun fichier appliqué

→ Pour personnaliser un fichier sur un repo spécifique, créer simplement un fichier de même nom dans ce repo.

---

## Comment utiliser ce repo

### Pour la vitrine

Modifier [`profile/README.md`](./profile/README.md). Tout changement mergé sur `main` est immédiatement visible sur la page d'accueil de l'organisation.

### Pour les fichiers communautaires

Modifier le fichier concerné sur la branche `develop`, ouvrir une PR vers `main`, vérifier le rendu (notamment pour les liens externes et les badges) avant merge.

### Pour Dependabot

Copier [`dependabot.yml`](./dependabot.yml) dans le `.github/` de chaque nouveau repo Node/TS. Adapter le champ `package-ecosystem` et les répertoires selon le stack.

### Pour le workflow CI réutilisable

Dans le workflow CI d'un repo, appeler le workflow depuis ce repo :

```yaml
jobs:
  ci:
    uses: Axo-Lab03/.github/.github/workflows/reusable-node-ci.yml@main
    with:
      node-version: '22'
      run-e2e: true
```

---

## Branches

- `main` : production, affiché publiquement, protégé
- `develop` : intégration, base des PR

---

## Licence

Le contenu de ce repo est utilisé exclusivement pour la configuration publique de l'organisation Axo-Lab03 sur GitHub. Aucune licence open source explicite n'est attachée. Les fichiers basés sur des standards (Contributor Covenant notamment) restent sous leur licence d'origine.

---

## Contact

✉️ [contact@axo-lab.fr](mailto:contact@axo-lab.fr) · 🌐 [axo-lab.fr](https://axo-lab.fr)

**AXO-LAB SASU** · SIRET 103 310 017 00019 · 03000 Avermes
