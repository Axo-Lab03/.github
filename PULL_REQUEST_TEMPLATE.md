<!--
Merci pour votre contribution. Remplissez ce template aussi complètement que pertinent.
Les sections marquées « obligatoire » doivent être renseignées pour que la PR soit revue.
-->

## Contexte et motivation *(obligatoire)*

<!-- Pourquoi cette PR existe-t-elle ? Quel problème résout-elle ? Quel besoin couvre-t-elle ? -->

## Issue liée

<!-- Si applicable, lier l'issue avec une mot-clé : "Closes #123", "Fixes #456", "Refs #789" -->

Closes #

## Type de changement *(obligatoire)*

<!-- Cocher au moins une case -->

- [ ] 🐛 `fix` — Correction de bug
- [ ] ✨ `feat` — Nouvelle fonctionnalité
- [ ] 💥 Breaking change (changement qui casse la compatibilité)
- [ ] 🔧 `chore` — Maintenance, outillage, configuration
- [ ] ♻️ `refactor` — Refactoring sans changement de comportement
- [ ] 📝 `docs` — Documentation seule
- [ ] 🧪 `test` — Ajout ou modification de tests
- [ ] 🎨 `style` — Formatage seul
- [ ] ⚡ `perf` — Amélioration de performance
- [ ] 🚀 `ci` / `build` — CI/CD, build, dépendances

## Détail des changements *(obligatoire)*

<!-- Liste claire de ce qui a été modifié -->

-
-
-

## Comment tester ? *(obligatoire pour fix/feat)*

<!--
Étapes précises pour valider la modification en local.
Inclure les commandes exactes, les URLs à visiter, les conditions à reproduire.
-->

```bash

```

## Captures d'écran *(si modification UI)*

| Avant | Après |
|---|---|
| | |

## Checklist *(obligatoire)*

### Qualité

- [ ] Le code suit les conventions du projet (lint passe localement)
- [ ] La vérification de types passe (`tsc --noEmit`)
- [ ] Les tests unitaires existants passent
- [ ] Les tests E2E passent (le cas échéant)
- [ ] J'ai ajouté des tests pour le nouveau code (le cas échéant)
- [ ] Le build de production réussit

### Documentation

- [ ] J'ai mis à jour le `README.md` si nécessaire
- [ ] J'ai documenté les nouvelles variables d'environnement dans `.env.example`
- [ ] J'ai mis à jour le `CHANGELOG.md` si le repo en utilise un
- [ ] Les commentaires de code expliquent le **pourquoi** des choix non évidents

### Sécurité

- [ ] Aucun secret, clé API ou mot de passe n'est commité
- [ ] Les nouvelles dépendances ont été vérifiées (poids, mainteneur, alternatives)
- [ ] Les inputs utilisateur sont validés et échappés
- [ ] Les permissions et accès sont correctement vérifiés côté serveur

### Compatibilité

- [ ] Mes changements ne cassent pas les fonctionnalités existantes
- [ ] Les migrations de schéma (si présentes) sont rétro-compatibles ou documentées comme breaking
- [ ] J'ai testé sur les navigateurs cibles du projet (Chromium, Firefox, Safari, mobile)

### Conventional Commits

- [ ] Le titre de cette PR suit [Conventional Commits](https://www.conventionalcommits.org/fr)
- [ ] Si breaking change, le `!` est présent dans le titre et un footer `BREAKING CHANGE:` explique l'impact

---

## Notes pour le reviewer

<!-- Points d'attention spécifiques, choix à valider, dette technique assumée, etc. -->

## Déploiement

<!-- Si applicable : actions à effectuer côté production avant ou après merge -->

- [ ] Aucune action particulière requise
- [ ] Migration de base à exécuter
- [ ] Variable d'environnement à ajouter
- [ ] Cache à invalider
- [ ] Autre :
