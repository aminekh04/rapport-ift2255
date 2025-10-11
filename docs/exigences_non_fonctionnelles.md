# Exigences non fonctionnelles (NFR)

- **Sécurité & Confidentialité** : anonymisation (seuil n ≥ 5), chiffrement TLS/at-rest, consentement profil, journalisation d’accès, DPA.
- **Disponibilité** : **99,5 %** durant les périodes d’inscription; redémarrage auto et déploiement bleu/vert minimal.
- **Performance** : recherche **< 300 ms P95**; ingestion quotidienne **< 30 min** pour 10k cours.
- **Observabilité** : tableaux de bord d’ingestion (succès/échecs), métriques & alertes (connecteurs/API).
- **Accessibilité/UX** : UI responsive, libellés explicites, navigation simple; endpoints REST documentés (OpenAPI).

