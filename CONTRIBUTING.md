# Contribuer aux projets Axo-Lab

Merci de votre intérêt pour les projets Axo-Lab. Ce document décrit nos conventions communes pour contribuer aux repos de l'organisation, qu'il s'agisse d'une contribution interne (équipe, freelance partenaire) ou externe (contribution open source spontanée).

> **Note importante** : la plupart de nos projets clients sont **privés**. Les contributions externes ne sont possibles que sur les repos explicitement marqués `public` et n'ayant pas de mention contraire dans leur `README.md`.

---

## Avant de commencer

1. Lisez le [Code de conduite](./CODE_OF_CONDUCT.md).
2. Vérifiez que votre contribution s'inscrit dans la portée du projet (lire le `README.md` du repo concerné).
3. Pour toute contribution non triviale, **ouvrez une issue avant de commencer** afin d'aligner sur l'approche.

---

## Workflow Git

### Branches

| Branche | Rôle |
|---|---|
| `main` | Production. Protégée. Aucun commit direct. |
| `develop` | Intégration continue. Base des branches feature. |
| `feature/<nom-court>` | Nouvelle fonctionnalité. Branchée depuis `develop`. |
| `fix/<nom-court>` | Correction de bug. Branchée depuis `develop` (ou `main` pour un hotfix). |
| `chore/<nom-court>` | Maintenance, outillage, refactoring. |
| `docs/<nom-court>` | Documentation seule. |

### Cycle de vie d'une contribution

```
develop ──> feature/ma-feature ──> PR vers develop ──> merge
                                                          │
                                                          ▼
                                            release PR develop ──> main
```

1. `git checkout develop && git pull`
2. `git checkout -b feature/<nom-court>`
3. Commits atomiques (voir conventions ci-dessous)
4. `git push -u origin feature/<nom-court>`
5. Ouvrir une Pull Request vers `develop`
6. Attendre la CI verte et au moins une revue approuvée
7. Squash & merge (par défaut) ou rebase & merge selon le repo

---

## Conventions de commits

Nous utilisons [Conventional Commits](https://www.conventionalcommits.org/fr).

Format :

```
<type>(<scope>): <description courte>

<corps optionnel>

<footer optionnel>
```

### Types autorisés

| Type | Quand l'utiliser |
|---|---|
| `feat` | Nouvelle fonctionnalité visible utilisateur |
| `fix` | Correction de bug |
| `chore` | Outillage, configuration, tâches de maintenance |
| `refactor` | Refactoring sans changement de comportement |
| `perf` | Amélioration de performance |
| `docs` | Documentation seule |
| `test` | Ajout ou modification de tests |
| `style` | Formatage, point-virgules, indentation (jamais de logique) |
| `ci` | Modifications de la CI/CD |
| `build` | Modifications du système de build ou des dépendances |
| `revert` | Annulation d'un commit antérieur |

### Exemples

```
feat(contact): ajouter validation email côté serveur
fix(auth): corriger expiration du token refresh
docs(readme): mettre à jour les prérequis Node
chore(deps): bump next from 16.0.1 to 16.0.2
ci(release): déclencher build Docker sur tag v*
```

### Règles

- Description en français ou anglais selon le repo (anglais préféré pour les repos publics, français pour les repos clients internes francophones)
- Ligne sujet : 72 caractères maximum
- Pas de point final sur la ligne sujet
- Verbe à l'infinitif (« ajouter », « corriger »), pas au passé
- Corps du message optionnel mais recommandé pour expliquer le **pourquoi**, pas le **quoi**

### Breaking changes

Indiquer par `!` après le type ou via le footer `BREAKING CHANGE:` :

```
feat(api)!: passer la route /v1/users en POST exclusivement
```

---

## Conventions de Pull Request

### Titre

Suivre les Conventional Commits (le titre devient le message de merge en mode squash).

### Description

Utiliser le [template de PR](./PULL_REQUEST_TEMPLATE.md). Remplir au minimum :

- Contexte et motivation
- Liste des changements
- Captures d'écran si UI
- Comment tester

### Taille

Privilégier les PR **petites et focalisées** (< 400 lignes diff hors lockfiles). Une grosse PR est presque toujours plusieurs petites PR cousues, et est plus risquée à revoir.

### Revues

- 1 reviewer minimum sur tous les repos
- 2 reviewers sur les chemins critiques (authentification, paiement, sécurité) si applicable
- Les commentaires « blocking » doivent être résolus avant merge
- L'auteur de la PR résout les conversations qu'il a traitées ; le reviewer résout celles qui répondent à ses questions

---

## Qualité du code

### Pré-requis CI

Toute PR doit passer **avant merge** :

- ✅ Lint (`npm run lint`)
- ✅ Vérification de types (`tsc --noEmit`)
- ✅ Tests unitaires (`npm run test`)
- ✅ Tests E2E le cas échéant (`npx playwright test`)
- ✅ Build réussi (`npm run build`)

### Style de code

- Configuration ESLint + Prettier au niveau du repo (ne pas overrider localement)
- TypeScript strict (`"strict": true` dans `tsconfig.json`)
- Pas d'`any` sauf justification explicite en commentaire
- Pas de `console.log` en production (utiliser un logger)

### Tests

- Tout nouveau code doit avoir des tests (unitaires a minima, E2E si visible utilisateur)
- Couverture minimale visée : 70 % statements sur `lib/` et utilitaires
- Les tests existants ne doivent jamais être désactivés sans justification écrite dans la PR

---

## Sécurité

**Ne jamais commiter** :

- Clés API, secrets, tokens, mots de passe
- Fichiers `.env`, `.env.local`, `.env.production`
- Données personnelles ou clients

Si un secret a été commité par erreur, contacter immédiatement le mainteneur. Voir [SECURITY.md](./SECURITY.md).

---

## Documentation

- Toute modification d'API publique doit s'accompagner d'une mise à jour du `README.md` ou de la documentation dédiée
- Toute nouvelle variable d'environnement doit être documentée dans le `README.md` et ajoutée à `.env.example`
- Les décisions architecturales notables vont dans `ARCHITECTURE.md` quand il existe

---

## Licence des contributions

En soumettant une contribution sur un repo public d'Axo-Lab, vous acceptez que celle-ci soit publiée sous la licence du repo concerné (voir `LICENSE` du repo). Pour les repos privés, les conditions sont celles du contrat de prestation applicable.

---

## Questions

Pour toute question sur ces conventions, ouvrir une issue ou contacter [contact@axo-lab.fr](mailto:contact@axo-lab.fr).
