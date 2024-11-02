

---

# Mini Application de Chat

## Objectif du Projet

L’objectif de ce TP est de concevoir et développer une application de chat en temps réel avec une interface utilisateur dynamique et intuitive. Les fonctionnalités d’un système de messagerie instantanée seront mises en œuvre en respectant les principes de conception modernes, en utilisant des technologies adaptées comme Firebase pour la gestion des messages en temps réel, RecyclerView pour l'affichage dynamique des messages et des utilisateurs, Glide pour le chargement d'avatars en forme circulaire, et une navigation fluide entre les différentes interfaces via des fragments. L'architecture MVVM sera adoptée pour garantir une organisation claire et maintenable du code. Ce projet vise à renforcer les compétences dans la création d’applications Android modernes, en suivant les standards de conception actuels et en mettant en pratique des technologies pertinentes pour un système de chat.

## Concepts Liés au Projet

- **Firebase Realtime Database** : Utilisé pour stocker et synchroniser les messages en temps réel.
- **RecyclerView** : Employé pour afficher les messages sous forme de liste défilante ainsi que la liste des utilisateurs de chat.
- **Glide** : Intégré pour charger et afficher les avatars en forme circulaire.
- **MVVM (Model-View-ViewModel)** : Adopté pour une séparation nette entre la logique, les données et l’interface utilisateur.
- **Navigation entre Fragments** : Mise en place pour gérer la transition entre différentes interfaces.

## Fonctionnalités Principales

### Chat en Temps Réel
- Les messages sont envoyés et reçus instantanément grâce à Firebase.
- Une liste dynamique de messages est générée avec RecyclerView.

### Affichage d'Images Circulaires
- Les images des utilisateurs sont chargées à partir d’URLs à l’aide de Glide et affichées sous forme circulaire.

### Navigation entre Fragments
- Les fragments sont utilisés pour organiser différentes parties de l’application, telles que l’écran principal et l’espace de chat.

### Interface Utilisateur Simplifiée
- Des bulles de message sont employées (messages envoyés à droite et messages reçus à gauche).
- Une zone de saisie est fournie en bas avec un bouton d’envoi facilement accessible.

## Implémentation

### Structure Hiérarchique du Projet

#### Paquetage `entity`
- **User** : Classe représentant un utilisateur avec des attributs comme l'ID, le nom, l'email, etc. Mappée dans la base de données pour stocker les informations des utilisateurs.
- **Message** : Classe représentant un message échangé entre utilisateurs, incluant l'ID, le contenu, l'expéditeur, le destinataire, et la date/heure d'envoi. Mappée à une table dans la base de données.

#### Paquetage `adapter`
- **MessageAdapter** : Adaptateur pour afficher les messages dans un RecyclerView. Gère l'affichage dynamique des messages, optimisant le rendu et la performance.
- **UserChatAdapter** : Adaptateur pour afficher les utilisateurs dans un RecyclerView, gérant la liste des utilisateurs disponibles pour le chat.

#### Paquetage `MVVM`
- **AppViewModel** : Cœur du modèle MVVM, agissant comme intermédiaire entre la vue et les données. Récupère les données via les repositories et notifie la vue des changements.

#### Classe Utilitaire
- **Utils** : Contient des constantes et des méthodes utilitaires utilisées à travers l'application (clés de préférence partagée, codes d'erreur, etc.).

#### Classe `SignIn`
- Gère l'authentification des utilisateurs.

#### Classe `SignUp`
- Gère la création de nouveaux comptes d'utilisateur.

#### Paquetage `fragment`
- **SettingFragment (Fragment de Profil)** :
  - **But** : Afficher et gérer les informations personnelles (nom, photo de profil, etc.).
  - **Fonctionnalités** : Modifier le profil, supprimer son compte ou se déconnecter.

- **HomeFragment (Fragment Principal)** :
  - **But** : Afficher la liste des utilisateurs disponibles pour discuter.
  - **Fonctionnalités** : Voir les contacts et accéder à une conversation en cliquant sur un utilisateur.

- **FragmentChat (Fragment de Chat)** :
  - **But** : Gérer les conversations entre utilisateurs (envoi et réception de messages).
  - **Fonctionnalités** : Afficher les messages et permettre l’envoi de nouveaux messages.

## Description des Interfaces Utilisateur (XML)

### Interface de Connexion (Login)
- **Organisation** : Formulaire centré verticalement.
- **Composants** :
  - Champs pour le nom d’utilisateur/email et mot de passe.
  - Bouton de connexion et lien hypertexte pour créer un compte.
- **Interactions** : Validation avec alerte d’erreur pour champs vides ou identifiants incorrects, redirection vers l’interface principale en cas de succès.

### Interface d’Inscription (Sign Up)
- **Organisation** : Formulaire vertical.
- **Composants** :
  - Champs pour le nom d’utilisateur, email, mot de passe.
  - Bouton pour choisir une photo de profil et bouton de validation.
  - Lien hypertexte pour se connecter.
- **Interactions** : Vérification de la disponibilité du nom d’utilisateur, alerte de confirmation en cas de succès.

### Interface Principale (HomeFragment)
- **Organisation** : Liste verticale (RecyclerView) affichant les utilisateurs.
- **Composants** :
  - Barre de recherche et RecyclerView avec photo de profil et nom de l’utilisateur.
- **Interactions** : Clic sur un utilisateur pour ouvrir l’interface de chat.

### Interface de Discussion (FragmentChat)
- **Organisation** : Liste verticale de messages avec barre de saisie.
- **Composants** :
  - RecyclerView pour afficher les messages, champ de texte pour saisir un message, bouton d’envoi.
- **Interactions** : Envoi de message avec affichage immédiat et indicateurs de réception.

### Interface de Profil (SettingFragment)
- **Organisation** : Affichage vertical avec informations utilisateur et bouton de modification.
- **Composants** :
  - ImageView pour la photo de profil, TextView pour le nom, boutons pour modifier et supprimer le compte.
- **Interactions** : Modification des informations utilisateur et confirmation avant suppression.

## Licence

Ce projet est sous la licence [MIT](https://opensource.org/licenses/MIT). Vous pouvez librement utiliser, modifier et distribuer le code, à condition d'inclure le droit d'auteur et la licence dans toutes les copies ou portions substantielles du logiciel.




---

N'hésitez pas à me faire savoir si vous avez besoin d'autres ajouts ou modifications !
