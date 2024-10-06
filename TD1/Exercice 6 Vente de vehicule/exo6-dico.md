|Nom Attribut|Description|Type|Contrainte|
|---|---|---|---|
|**id_depot**|Identifiant unique du dépôt|integer|Clé primaire|
|nom_depot|Nom du dépôt|varchar||
|adresse_depot|Adresse du dépôt|varchar||
|ville_depot|Ville du dépôt|varchar||
|code_postal_depot|Code postal du dépôt|varchar||
|**id_marque**|Identifiant unique de la marque|integer|Clé primaire|
|nom_marque|Nom de la marque|varchar||
|**id_client**|Identifiant unique du client|integer|Clé primaire|
|nom_client|Nom du client|varchar||
|prenom_client|Prénom du client|varchar||
|adresse_client|Adresse du client|varchar||
|ville_client|Ville du client|varchar||
|code_postal_client|Code postal du client|varchar||
|**id_attache_comm**|Identifiant unique de l'attaché commercial|integer|Clé primaire|
|nom_attache_comm|Nom de l'attaché commercial|varchar||
|adresse_attache_comm|Adresse de l'attaché commercial|varchar||
|**id_resp_comm**|Identifiant unique du responsable commercial|integer|Clé primaire|
|nom_resp_comm|Nom du responsable commercial|varchar||
|adresse_resp_comm|Adresse du responsable commercial|varchar||
|**id_type_vehi**|Identifiant unique du type de véhicule|integer||
|libelle_type_vehi|Libellé du type de véhicule|varchar||
|prix_type_vehi|Prix du type de véhicule|decimal||
|puiss_fisc_type_vehi|Puissance fiscale du type de véhicule|integer||
|**id_vehi**|Identifiant unique du véhicule acheté|integer||
|date_achat_vehi|Date d'achat du véhicule|date||
