# Politique de sécurité

Axo-Lab prend très au sérieux la sécurité de ses produits et de son écosystème. Si vous découvrez une vulnérabilité, merci de suivre la procédure ci-dessous.

---

## Signaler une vulnérabilité

### Méthode privilégiée : Private Vulnerability Reporting de GitHub

Pour les repos qui ont activé cette fonctionnalité (la plupart de nos repos publics) :

1. Aller sur l'onglet **Security** du repo concerné
2. Cliquer sur **Report a vulnerability**
3. Remplir le formulaire confidentiel

Ce canal permet une discussion privée entre vous et les mainteneurs, sans exposer la vulnérabilité publiquement.

### Méthode alternative : email

Si le repo n'a pas activé Private Vulnerability Reporting, ou si la vulnérabilité concerne plusieurs repos / l'infrastructure :

📧 **contact@axo-lab.fr**

Merci d'inclure dans votre signalement :

- Description de la vulnérabilité
- Repo, fichier, ligne ou endpoint concerné
- Étapes de reproduction
- Impact estimé (confidentialité, intégrité, disponibilité)
- Version concernée
- Votre identité (optionnel) pour le credit dans le correctif

### Ce qu'il NE faut PAS faire

- ❌ Ne pas ouvrir d'issue publique sur GitHub
- ❌ Ne pas publier la vulnérabilité sur les réseaux sociaux ou en conférence avant un correctif coordonné
- ❌ Ne pas tester la vulnérabilité contre des données ou systèmes qui ne vous appartiennent pas

---

## Notre engagement

| Étape | Délai indicatif |
|---|---|
| Accusé de réception du signalement | 72 heures ouvrées |
| Évaluation initiale et qualification | 7 jours ouvrés |
| Plan de correction communiqué | 14 jours ouvrés |
| Correctif déployé (vulnérabilités critiques / hautes) | 30 jours ouvrés |
| Correctif déployé (vulnérabilités moyennes / basses) | 90 jours ouvrés |

Ces délais sont indicatifs et peuvent varier selon la complexité du problème. Nous communiquerons régulièrement sur l'avancement.

---

## Divulgation coordonnée

Nous suivons le principe de **divulgation coordonnée** (responsible disclosure) :

1. Vous nous signalez la vulnérabilité de manière privée
2. Nous reproduisons, qualifions, corrigeons
3. Nous coordonnons avec vous une date de divulgation publique
4. La vulnérabilité est divulguée (advisory GitHub, CVE si applicable) avec votre crédit si vous le souhaitez

Délai par défaut entre correctif et divulgation publique : **30 jours**, pour permettre aux utilisateurs de mettre à jour.

---

## Périmètre

### Inclus

- Tous les repos publics de l'organisation [Axo-Lab03](https://github.com/Axo-Lab03)
- Le site [axo-lab.fr](https://axo-lab.fr) et ses sous-domaines techniques (`umami.axo-lab.fr`, etc.)
- Les images Docker publiées sur `ghcr.io/axo-lab03/*`

### Exclu

- Les repos privés (couverts par les accords contractuels avec nos clients)
- Les services tiers (Supabase, OVHcloud, GitHub, Cal.com, etc.) — à signaler directement à ces fournisseurs
- Les vulnérabilités déjà connues et listées dans les advisories GitHub du repo

---

## Versions supportées

Pour chaque repo public, seules certaines versions reçoivent des correctifs de sécurité. La règle générale :

| Version | Support sécurité |
|---|---|
| Dernière version majeure (`main`) | ✅ Oui |
| Avant-dernière version majeure | ✅ 6 mois après sortie de la suivante |
| Versions antérieures | ❌ Non |

Le `README.md` ou un fichier `SECURITY.md` propre au repo peut préciser cette règle.

---

## Reconnaissance

Nous remercions publiquement les personnes qui contribuent à la sécurité de nos projets, sauf demande contraire de leur part. Ce remerciement peut prendre la forme :

- Mention dans le changelog ou la release notes
- Crédit dans l'advisory GitHub
- Crédit dans le commit du correctif

Axo-Lab n'opère pas de programme de bug bounty payant à ce jour.

---

## Confidentialité

Toutes les communications de sécurité sont traitées de manière confidentielle. Les signalements ne sont partagés en interne qu'avec les personnes strictement nécessaires à la résolution.

---

## Coordonnées

📧 **contact@axo-lab.fr**
🌐 [axo-lab.fr](https://axo-lab.fr)

**AXO-LAB SASU** · SIRET 103 310 017 00019
Le Point Commun, 03000 Avermes, France
