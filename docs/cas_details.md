# Spécifications détaillées — 5 cas d'utilisation

## CU-01 — Rechercher un cours et vérifier l’éligibilité
**Acteur principal** : Étudiant  
**Préconditions** : Index à jour (synchro OK)  
**Déclencheur** : L’étudiant saisit une requête/mots-clés ou filtre  
**Scénario nominal** :  
1. Saisie de la requête ou des filtres (cycle, crédits, session)  
2. Interrogation de l’index interne + récupération pré/co-requis via Planifium  
3. Calcul et affichage de l’**éligibilité explicable** (règle/raison)  
4. Ouverture de la fiche du cours  
**Alternatives** :  
- A1 : Aucun résultat → suggestions voisines  
- A2 : Planifium indisponible → cache + avertissement  
**Postconditions** : Liste triable/filtrable avec statut d’éligibilité

## CU-02 — Consulter la fiche d’un cours (agrégats + avis)
**Acteur principal** : Étudiant  
**Préconditions** : Agrégats (résultats + avis n ≥ 5) disponibles  
**Scénario nominal** :  
1. Résumé officiel (code, crédits, description, horaires récents)  
2. Résultats agrégés par session (moyenne, inscrits, échecs)  
3. Synthèse des avis (difficulté, charge médiane, mots-clés)  
4. Actions : ajouter au comparateur / plan de session  
**Alternative** : A1 : n < 5 → masquer la section et indiquer la raison  
**Postconditions** : Fiche consolidée prête à comparer/planifier

## CU-03 — Comparer plusieurs cours et estimer la charge
**Acteur principal** : Étudiant  
**Préconditions** : ≥ 2 cours dans le comparateur  
**Scénario nominal** :  
1. Tableau comparatif (charge, difficulté, moyenne, taux d’échec)  
2. Calcul de la **charge combinée hebdo** (médianes + pénalité conflits d’horaires)  
3. Mise en évidence des **combinaisons à risque** (seuils configurables)  
4. Enregistrement d’un brouillon de plan de session  
**Alternative** : A1 : Données manquantes → estimation partielle + avertissements  
**Postconditions** : Décision éclairée

## CU-04 — Personnaliser son profil et recommandations
**Acteur principal** : Étudiant  
**Préconditions** : Utilisateur identifié ou stockage local  
**Scénario nominal** :  
1. Saisie préférences, contraintes, objectifs  
2. Sauvegarde du profil et **pondérations** calculées  
3. Application des pondérations à la recherche, fiches et comparateur  
**Alternative** : A1 : Invité → sauvegarde locale, effacée à la déconnexion  
**Postconditions** : Profil influe présentation et recommandations

## CU-05 — Ingestion synchronisée des données
**Acteur principal** : Système (cron)  
**Acteurs externes** : Planifium API, dépôt CSV résultats, bot Discord  
**Préconditions** : Connecteurs configurés, accès autorisés  
**Scénario nominal** :  
1. **Extraire** : Planifium, CSV, JSON d’avis  
2. **Valider** : schémas, sessions, doublons; appliquer seuil n ≥ 5  
3. **Transformer/Indexer** : normaliser codes/sessions; calculer métriques  
4. **Charger** : base analytique + index; journaliser l’état  
**Alternative** : A1 : Échec partiel → rollback segmenté + alerte  
**Postconditions** : Données fraîches/anonymisées prêtes (API/UI)
