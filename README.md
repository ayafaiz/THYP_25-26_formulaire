# THYP_25-26_formulaireProjet



##  Liens

- Formulaire :[Lien Google Form](https://forms.gle/xn75ezMgWPH2jMib9)

Titre du projet :
Plateforme intelligente de gestion des inscriptions universitaires basée sur l’intelligence artificielle

Description du projet :
Ce projet a pour objectif de concevoir et développer une plateforme web intelligente dédiée à la gestion des inscriptions universitaires.
Elle permet aux étudiants de s’inscrire en ligne, de déposer leurs documents et de suivre l’état d’avancement de leur dossier.
Grâce à l’intégration de techniques d’intelligence artificielle, la plateforme vise à rendre le processus d’inscription plus rapide, plus fiable et plus personnalisé.

Cette application s’adresse à deux types d’utilisateurs :
	•	Les étudiants, qui peuvent créer un compte, remplir leurs informations, soumettre leurs documents et obtenir des recommandations de filières adaptées à leur profil.
	•	L’administration universitaire, qui peut gérer, valider et analyser les inscriptions à travers un tableau de bord intelligent.

Objectif général :
Développer une application web intelligente permettant d’automatiser, d’optimiser et de personnaliser le processus d’inscription universitaire à l’aide de l’intelligence artificielle.

Objectifs spécifiques :
	•	Digitaliser le processus d’inscription pour faciliter les démarches étudiantes.
	•	Automatiser la vérification des documents à l’aide d’un module OCR (reconnaissance de texte).
	•	Proposer aux étudiants des filières recommandées selon leur profil académique grâce à un système de recommandation basé sur l’IA.
	•	Fournir à l’administration un tableau de bord complet pour le suivi, la validation et l’analyse des inscriptions.
	•	Intégrer un chatbot intelligent capable de répondre automatiquement aux questions les plus fréquentes.
	•	Utiliser des modèles prédictifs pour analyser les tendances et anticiper le nombre d’inscriptions futures.

Technologies utilisées :
	•	Frontend : React, HTML, CSS, JavaScript
	•	Backend : php
	•	Base de données : MySQL 
	•	Intelligence artificielle : Python, scikit-learn, OCR (Tesseract), NLP pour le chatbot
	•	Outils : GitHub, Mermaid, VS Code




   ```mermaid
erDiagram

    ETUDIANT {
        int id_etudiant PK
        string nom
        string prenom
        string email
        string mot_de_passe
        date date_naissance
        string adresse
        string niveau
        string filiere_recommandee
    }

    INSCRIPTION {
        int id_inscription PK
        date date_inscription
        string statut
        string annee_universitaire
        int id_etudiant FK
        int id_filiere FK
    }

    FILIERE {
        int id_filiere PK
        string nom_filiere
        string description
        string responsable
    }

    ADMINISTRATEUR {
        int id_admin PK
        string nom
        string prenom
        string email
        string mot_de_passe
        string role
    }

    DOCUMENT {
        int id_document PK
        string type_document
        string url_document
        string statut_validation
        int id_etudiant FK
    }

    RECOMMANDATION {
        int id_recommandation PK
        string type_modele
        float score
        string suggestion
        int id_etudiant FK
    }

    STATISTIQUE {
        int id_stat PK
        string annee
        int nb_inscriptions
        int nb_etudiants
        string tendance
    }

    CHATBOT {
        int id_chat PK
        string question
        string reponse
        int id_etudiant FK
    }

    HISTORIQUE_CONNEXION {
        int id_connexion PK
        datetime date_connexion
        string adresse_ip
        string navigateur
        int id_etudiant FK
    }

    ETUDIANT ||--o{ INSCRIPTION : "soumet"
    ETUDIANT ||--o{ DOCUMENT : "téléverse"
    ETUDIANT ||--o{ RECOMMANDATION : "reçoit"
    ETUDIANT ||--o{ CHATBOT : "interagit avec"
    ETUDIANT ||--o{ HISTORIQUE_CONNEXION : "se connecte"
    FILIERE ||--o{ INSCRIPTION : "contient"
    ADMINISTRATEUR ||--o{ STATISTIQUE : "génère"
    ADMINISTRATEUR ||--o{ INSCRIPTION : "valide"

```

