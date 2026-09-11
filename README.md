
  # Module Terraform EC2 Server

  Ce module crée un serveur EC2 et son Security Group.

  ## Ressources créées

  - une instance EC2 ;
  - un Security Group ;
  - une règle SSH limitée au CIDR administrateur ;
  - des règles TCP pour les ports demandés.

  ## Entrées principales

  - `name` : nom logique du serveur ;
  - `ami_id` : identifiant de l’image ;
  - `instance_type` : type EC2, `t3.micro` par défaut ;
  - `key_name` : clé SSH enregistrée dans AWS ;
  - `admin_cidr` : adresse autorisée pour SSH ;
  - `open_ports` : ports TCP ouverts publiquement ;
  - `tags` : tags supplémentaires.

  ## Sorties

  - `public_ip` ;
  - `instance_id` ;
  - `security_group_id`.

  ## Sécurité

  La valeur `admin_cidr` doit être un CIDR valide.
  La valeur `0.0.0.0/0` est interdite pour SSH.
