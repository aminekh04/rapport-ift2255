# Cadre du projet

## Description
Plateforme web (API REST + UI) aidant les étudiants du DIRO à choisir leurs cours de façon éclairée, en combinant données **officielles** (Planifium, résultats agrégés CSV) et **informelles** (avis Discord).

## Utilisateurs visés (acteurs)
- **Étudiant** (acteur principal unique).
- **Acteurs secondaires (optionnels)** : TGDE (consultation), Professeur (consultation).

## Objectifs
- Offrir une recherche/filtrage des cours avec **éligibilité explicable**.
- Centraliser résultats académiques agrégés et **avis (n ≥ 5)**.
- Comparer plusieurs cours pour **estimer la charge combinée**.
- Personnaliser selon **profil** (préférences, contraintes).
- API REST documentée + interface simple, accessible et responsive.

## Contraintes
- **Loi 25 (QC)** : consentement explicite, anonymisation, minimisation, chiffrement en transit/au repos, journalisation.
- Agrégation d’avis : n ≥ 5 avant tout affichage.
- Données hétérogènes (CSV, JSON, API).
- Accessibilité : API + UI web.

