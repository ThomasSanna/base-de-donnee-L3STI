|Nom Attribut|Description|Type|Contrainte|
|---|---|---|---|
|**num_commande**|Numéro de la facture|integer|Clé primaire|
|date_commande|Date de la facture|date||
|montant_commande|Montant de la facture|decimal||
|qte|Quantité d'un des plusieurs articles achetés|integer||
|**num_client**|Numéro du client|integer|Clé primaire|
|nom_client|Nom du client|varchar||
|prenom_client|Prénom du client|varchar||
|adresse_client|Adresse du client|varchar||
|ville_client|Ville du client|varchar||
|code_postal_client|Code postal du client|varchar||
|tel_client|Téléphone du client|varchar||
|**num_article**|Numéro de l'article|integer|Clé primaire|
|designation_article|Désignation de l'article|varchar||
|prix_u_article|Prix unitaire de l'article|decimal||
|**num_facture**|Numéro de la facture|integer|Clé primaire|
|date_facture|Date de la facture|date||
|montant_facture|Montant de la facture|decimal||