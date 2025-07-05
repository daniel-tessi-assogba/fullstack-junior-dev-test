# Contexte
Pour évaluer vos aptitutes de développeur fullstack Java Spring Boot + Angular, 
nous vous proposons de concevoir un projet kata réaliste et court (3 à 5 heures),
inspiré directement des besoins métiers clés de notre plateforme e-learning de skolae.

# Besoin Metier
SKOLAE est composé d'un réseaux d'écoles (GES & EDUCTIVE) et fait partie des plus importants réseaux d’enseignement supérieur privé. 
Ses établissements de Bac à Bac+5 délivrent des titres reconnus par l’État niveaux 5, 6 et 7 ainsi que des titres RNCP et préparent à certains diplômes d’État.
Avec ses 23 écoles accessibles en alternance et plus de 50 ans d’expertise pédagogique, SKOLAE a besoin d'enrichir et d'assouplir son processus d'inscription. 
Pour ce faire le site de formation en ligne de skolae a besoin de mettre en place un Back For Front (BFF) pour la gestion de la phase de pre-inscription.

# fiche Fonctionnelle
A cette phase de pre-inscriptemandeur une école peut s'inscrire comme un tenant sur la plateforme multi tenant de Sokolae.
L'école fournit ses données légales (nom de l'établissement, pôle de formation, format d'enseignement, année d'immatriculation, adresse du siège, pièces justificatives, nom du representant, prenom du representant, telephone, email)
les ecole proposent des "Cours en ligne animés par un instructeur" ou des "Formations en classe".

# fiche Techniaue
Fonctionnalités à implémenter

1. Backend de Préinscription d'une école avec téléversement du justificatif d'établissement

  Backend (Java 17+, Spring Boot 3+)
  
  - Developer les opératiosn CRUD pour l'enregistrement en base d'une école
  - Stockage des fichiers dans un dossier local (ou dossier simulé cloud)
  - Retour d'un statut "en attente de validation".
  - Mettre en place au moins les tois cas de tests TDD suivants pour assurer un bon fonctionnement du microservice:
    T001 : Envoi d’une préinscription complète et valide avec toutes les données et des fichiers (PDF, PNG, etc.) ⇒ Attente HTTP 201
    T002 : Envoi d'un champ vide mais obligatoire ⇒ HTTP 400
    T020: Préinscription avec un email ou nom_etablissement déjà soumis ⇒ HTTP 409

Vous trouverez à la racine de ce dossier le repertoire pre-registration-service qui est un projet springboot maven avec des dependances repondant aux exigences technique,
mais vous pouvez genener un projet maven ou gradle selon votre convenance.
Un établissement scolaire a les caractéristiques suivantes :

  ``` typescript
  class Ecole {
    id: uuid;
    nom_etablissement: string;
    pole_formation: string;
    annee_immatriculation: string;
    adresse_siege: string;
    nom_representant: string;
    prenom_representant: number;
    telephone: number;
    types_formation: string;
    createdAt: Datetime;
    updatedAt: datetime;
  }
  ```


2. Frontend de Préinscription d'une ecole avec téléversement du justificatif d'établissement

  Frontend (Angular 17+)
  
  Formulaire : nom de l'établissement, pôle de formation, format d'enseignement, etc...
  Upload d'un fichier PDF (Justificatif d'etablissement)
  Appel à l'API backend et affichage des ecole preinscrites en attente de validation

  Ce projet Frontend pre-registration-frontend (à la racine de ce dossier) est un dashbord à moitié dévelopé. Votre tache consiste à faire communiquer le backend et le frontend, ajouter, modifier et supprimer 
  un établissement scolaire à partir du front.

# Specifications API
Les specifications API sont disponibles dans le document skolae-pre-registration-specification.yaml à la racine du dossier.

## Ce qui est attendu
- Developer les tâches attendues côté bckend en suivant les specifications.
- Developer les tâches attendues côté frontend en l'adatant aux specifications du backend.
  (A rendre sous 2 jours à compter de la date de reception)

