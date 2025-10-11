# Exigences fonctionnelles (FR)

- **FR-1** : Recherche par code/titre/mots-clés + filtres (cycle, crédits, session).
- **FR-2** : Éligibilité explicable (pré/co-requis, cycle, statut programme).
- **FR-3** : Résultats agrégés par session (moyenne, inscrits, échecs).
- **FR-4** : Avis agrégés (n ≥ 5) : difficulté perçue, charge médiane, mots-clés.
- **FR-5** : Comparateur de N cours + estimation de charge combinée; surbrillance des combinaisons à risque.
- **FR-6** : Profil utilisateur influençant tri/filtrage/recommandations.
- **FR-7** : Ingestion planifiée (Planifium/CSV/Discord) avec validation/normalisation.
- **FR-8** : API REST en lecture pour toutes les vues (recherche, fiche, comparaison, profil).

## Critères d'acceptation (extraits)
- **CA-1** : La recherche renvoie des résultats pertinents en < 300 ms (P95) pour 10k cours (scénario nominal).
- **CA-2** : L’éligibilité affiche la raison (pré-requis manquant, cycle inadéquat, etc.).
- **CA-3** : Les avis ne s’affichent pas tant que `n < 5`.
- **CA-4** : Le comparateur calcule la charge combinée et signale les conflits d’horaires.
- **CA-5** : Les résultats agrégés présentent au minimum : moyenne, inscrits, échecs par session.
