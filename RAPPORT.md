Difficultés Rencontrées

-Préparation des Données
Parsing du format JSONL: Le fichier train.jsonl contenait des commentaires avec "\" qui causaient des erreurs de parsing. Il a fallu implémenter un système de filtrage pour ignorer ces lignes.
- Installation de ChromaDB: Des problèmes d'installation de ChromaDB sont survenus car les outils de build Microsoft C++ devaient être installés au préalable, ce qui a nécessité une étape supplémentaire de configuration.

Améliorations Possibles

- Chunking adaptatif: Implémenter un système qui ajuste dynamiquement la taille des chunks selon le contenu plutôt qu'une taille fixe.
- Reranking: Ajouter une étape de reranking des documents après la recherche initiale pour améliorer la pertinence.
- Requêtes multi-étapes: Décomposer les questions complexes en sous-questions pour obtenir des réponses plus complètes.