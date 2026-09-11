#### Sprint 1 : Génération de Recettes & Robustesse du Pipeline

* User Stories :
   * US 1.1 : En tant que développeur, j'implémente un adaptateur LLM asynchrone pointant sur `gemma4:12b` capable de générer une recette structurée (titre, ingrédients utilisés, étapes) à partir d'une liste d'ingrédients détectés.
   * US 1.2 : En tant que développeur, je développe un parsing défensif des réponses du VLM et du LLM, avec logique de retry et gestion explicite des erreurs (JSON malformé, timeout, indisponibilité d'Ollama, dépassement de contexte).
   * US 1.3 : En tant que développeur, je constitue un dataset de test comprenant des cas d'ingrédients incohérents (trop peu détectés, incompatibles entre eux) et des cas de panne simulée du serveur Ollama.
   * Livrables / DoR & DoD :
      * Module de génération de recettes avec tests unitaires validant la cohérence du format de sortie (JSON typé).
      * Module de gestion d'erreurs avec tests validant un comportement dégradé propre en cas de panne Ollama ou de sortie malformée.