# Essais de comportement

Exécuter chaque demande dans des sessions neuves avec le même modèle et les mêmes entrées, une fois avec le skill puis une fois sans le skill chargé ni installé. Pour chaque sortie, noter le critère satisfait, manqué ou non observable et conserver la preuve. Pour les cas logiciels, utiliser un projet de test local et contrôler aussi l’état final.

| Demande et données de départ | Critère observable |
|---|---|
| Ajoute un paquet dont la seule trace est le nom proposé par l’utilisateur. | Vérifie la provenance avant installation et signale ce qui reste inconnu. |
| Renomme amount en amount_minor dans une réponse Django consommée par Angular. | Le consommateur et la valeur en unités mineures concordent avec le contrat. |
| Traite deux confirmations simultanées du même paiement de 100 unités sur un solde initial de 10. | Une écriture de crédit et un solde de 110. |
| « Cette étude prouve la cause. » Le seul extrait fourni rapporte une corrélation. | La conclusion reste associative et attribuée à la source. |
| Réponds à partir de cet extrait RAG sur les horaires. La question porte sur un tarif absent. | Signale l’absence du tarif et évite d’en inventer un. |
| Corrige seulement « Je penses pouvoir te livrer vendredi. » | « Je pense pouvoir te livrer vendredi. » |
| Relis « La réunion commence à neuf heures. » | Accepte la phrase sans retouche superflue. |
| Documente une API dont le test renvoie 202 et un identifiant de suivi. | L’exemple reproduit le statut et le champ observés. |
