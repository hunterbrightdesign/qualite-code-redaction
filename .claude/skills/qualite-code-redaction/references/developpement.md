# Conception et développement

Pars du parcours utilisateur, de l’entrée applicative et des conventions du dépôt. En conception, relie chaque choix important à une contrainte métier et décris le comportement en cas d’échec. Réutilise une abstraction existante lorsqu’elle préserve le contrat attendu.

Avant d’ajouter une dépendance, retrouve le projet officiel, le nom distribué et les versions compatibles et maintenues. Confirme les signatures d’API dans le code installé ou la documentation correspondante. Si la vérification échoue, explicite l’incertitude et cherche une option déjà disponible.

Suis les changements de contrat jusqu’aux consommateurs et aux données déjà créées. Valide les entrées à la frontière du système, contrôle les droits sur chaque ressource côté serveur et applique le traitement adapté au contexte de sortie. Paramètre les requêtes SQL. Utilise le mécanisme de secrets du projet et vérifie les données visibles dans les logs.

Pour les opérations qui peuvent être rejouées ou interrompues, formule la propriété à garantir. Exemple : deux confirmations simultanées d’un paiement produisent un seul crédit. Vérifie les écritures et le solde après les deux traitements. Pour une migration, exerce le parcours avec des données antérieures.

Avant une action destructive, vérifie la cible et l’autorisation déjà accordée. Teste le scénario touché par le point d’entrée habituel et précise exactement ce qui a été observé.
