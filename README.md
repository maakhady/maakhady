# Projet YAKAR - Système de Surveillance de Température et d'Humidité

## Équipe de développement
- **Fatoumata Hawa Ndiongue** - Développeuse Full Stack
- **Mame Khady Laye Diaw** - Développeuse Full Stack
- **Mouhamed Antoine Sylva** - Développeur Full Stack
- **Anta Maguette Faye** - Développeuse Full Stack
- **Ahmadou Bamba Fary Diop** - Développeur Full Stack

## Description du Projet
YAKAR est un système de surveillance de température et d'humidité pour un magasin de stockage de produits locaux. Le système permet de :
- Surveiller la température et l'humidité en temps réel
- Collecter des données à des heures spécifiques (10h, 14h, 17h)
- Gérer automatiquement la ventilation
- Générer des alertes en cas de dépassement de seuil
- Visualiser les données via une interface web

## Technologies Utilisées
### Backend
- Node.js
- Express.js
- MongoDB
- JWT pour l'authentification

### Frontend (Interface Web)
- Angular
- Bootstrap pour le design

### Hardware
- Arduino Mega
- Capteur DHT11 (Température et Humidité)
- LED Rouge et Verte
- Ventilateur
- Buzzer
- Écran LCD

## Installation et Configuration

### Prérequis
- Node.js (v14 ou supérieur)
- MongoDB
- Arduino IDE
- npm ou yarn

### Installation Backend
```bash
# Cloner le projet
git clone [url-du-projet]

# Aller dans le dossier backend
cd yakar-backend

# Installer les dépendances
npm install

# Créer le fichier .env
cp .env.example .env

# Configurer les variables d'environnement dans .env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/yakar
JWT_SECRET=votre_secret_jwt

# Démarrer le serveur
npm run dev
```

### Installation Arduino
1. Ouvrir le fichier .ino dans Arduino IDE
2. Installer les bibliothèques requises :
   - DHT Sensor Library
   - LiquidCrystal I2C
3. Connecter l'Arduino selon le schéma de câblage
4. Téléverser le code

## Structure du Projet

### Backend
```
backend/
├── config/          # Configuration
├── controllers/     # Contrôleurs
├── middleware/      # Middleware
├── models/         # Modèles Mongoose
├── routes/         # Routes API
└── utils/          # Utilitaires
```

### Routes API

#### Authentification
```
POST /api/auth/inscription            # Inscription utilisateur
POST /api/auth/connexion/email       # Connexion par email
POST /api/auth/connexion/code        # Connexion par code secret
GET  /api/auth/profil                # Profil utilisateur
```

#### Mesures
```
POST /api/mesures                    # Créer une mesure
GET  /api/mesures/derniere           # Dernière mesure
GET  /api/mesures/heures-specifiques/:date  # Mesures par heures
GET  /api/mesures/statistiques/jour/:date   # Statistiques journalières
POST /api/mesures/ventilateur/controle      # Contrôle ventilateur
```

## Fonctionnalités

### Système de Surveillance
- Mesure de température et d'humidité en temps réel
- Collecte automatique aux heures spécifiques
- Alertes sonores et visuelles en cas de dépassement

### Gestion des Utilisateurs
- Deux types d'utilisateurs : administrateur et utilisateur simple
- Authentification double (email/mot de passe ou code secret)
- Gestion des droits d'accès

### Contrôle Environnemental
- Activation automatique du ventilateur si T° > 27°C
- Contrôle manuel possible par les administrateurs
- Système d'alertes en cas de conditions critiques

### Statistiques et Rapports
- Moyennes journalières de température et humidité
- Suivi des alertes et du fonctionnement du ventilateur
- Historique des mesures aux heures spécifiques

## Tests
```bash
# Démarrer les tests
npm test
```

## Sécurité
- Authentification JWT
- Validation des données
- Gestion des sessions
- Protection contre les accès non autorisés

## Documentation API
Pour plus de détails sur les routes API, consultez la documentation Postman :
[Lien vers la documentation Postman]

## Contribution
1. Fork le projet
2. Créer une branche (`git checkout -b feature/AmazingFeature`)
3. Commit les changements (`git commit -m 'Add AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrir une Pull Request

## Contact
Pour toute question ou suggestion, contactez l'équipe de développement :
Mame Khady: makhadypro@gmail.com
Fatoumata Hawa: hawa.ndiongue@gmail.com
Antoine Sylva: sylvaantoine21@gmail.com
Ahmadou Bamba:eggastro1@gmail.com
Anta Maguette:antamaguettefaye@gmail.com
