# TP Keycloak

## Partie 1: Configuration de Keycloak

#### 1. Télécharger Keycloak 19
Téléchargez Keycloak depuis le site officiel : Keycloak Téléchargement

#### 2. Démarrer Keycloak
Extrayez l'archive téléchargée et suivez les instructions de démarrage disponibles dans la documentation officielle de Keycloak.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/3f023c56-e8a1-4921-b57c-e6f99ae4080a)

#### 3. Créer un compte Admin
Accédez à l'interface d'administration de Keycloak (par défaut: http://localhost:8080/auth/admin). Créez un compte administrateur pour accéder à la console d'administration.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/2c33bff9-4019-4c44-a21f-125d50d7d969)


#### 4. Créer une Realm
Dans la console d'administration, créez une nouvelle "Realm" pour regrouper vos applications. Choisissez un nom significatif et appuyez sur "Create".
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/ae12abc4-6852-42b0-b09e-de6937837ba1)

#### 5. Créer un client à sécuriser
Ajoutez un nouveau client dans votre Realm pour représenter votre application. Configurez les détails du client, y compris les URL de redirection et les paramètres appropriés.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/31b9095c-cb9e-4647-b5eb-20e191629d1b)

#### 6. Créer des utilisateurs
Ajoutez des utilisateurs à votre Realm à l'aide de la fonction "Users" dans la console d'administration. Attribuez-leur un nom d'utilisateur et un mot de passe.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/8e3b1738-4ee1-4c76-b175-41a70f81395c)

#### 7. Créer des rôles
Créez des rôles pour définir les autorisations des utilisateurs. Utilisez la fonction "Roles" dans la console d'administration pour définir des rôles significatifs.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/a8cb436f-f712-4a80-93b7-db99869d9163)

#### 8. Affecter les rôles aux utilisateurs
Attribuez les rôles créés aux utilisateurs dans la section "Role Mappings" de chaque utilisateur.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/fddbff78-81df-413c-b923-6d0aafd38aba)

#### 9. Tester avec Postman
Utilisez Postman pour effectuer les tests suivants :

 - Authentification avec le mot de passe.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/6f40aacd-2824-45eb-94e1-3018b7e3bc47)

 - Analyse des contenus des JWT Access Token et Refresh Token.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/dda6be0f-7e37-4e91-9cc6-10b6630e2e75)

 - Authentification avec le Refresh Token.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/4685b832-3ebd-49fc-9714-afc4cfb89e55)

 - Authentification avec Client ID et Client Secret.
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/cde62a9d-5912-499a-ab8f-6b4bf2a5a345)
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/b1ba3b68-9d77-49ef-9076-0c76e608c988)


## Partie 2: Sécuriser les Applications
Dans cette partie, nous avons étendu l'utilisation de Keycloak pour sécuriser deux types d'applications : le frontend Products-App utilisant Thymeleaf et le microservice backend Supplier-service. Voici un résumé des étapes et des concepts clés :
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/3c765b51-c4b2-452a-b130-a768e7d6457a)
![image](https://github.com/salma-SABROU/Keycloak_TP/assets/129564311/235ed0ed-de77-40aa-93d6-29506f274b6a)

### Pour Products-App (Frontend avec Thymeleaf) :
 
 1- Configuration du Client Keycloak :
  - Création d'un client Keycloak pour représenter Products-App.
  - Configuration des détails du client, y compris les URL de redirection et les paramètres nécessaires.

 2- Intégration de Keycloak dans l'Application :
  - Utilisation de la bibliothèque Keycloak Adapter for Spring Security dans l'application Spring Boot.
  - Configuration des propriétés dans le fichier application.properties pour spécifier le Realm, l'URL du serveur d'authentification, le client ID, etc.

 3- Sécurisation des Pages avec des Rôles :
  - Définition des rôles dans Keycloak reflétant les autorisations requises pour accéder aux pages de Products-App.
  - Utilisation d'annotations ou de configurations pour restreindre l'accès aux pages en fonction des rôles.


### Pour Supplier-service (Microservice Backend) :

 1- Configuration du Client Keycloak :
  - Création d'un nouveau client Keycloak pour représenter Supplier-service.
  - Configuration des détails du client, tels que les URL de redirection et les paramètres nécessaires.

 2- Intégration de Keycloak dans le Microservice :
  - Utilisation de la bibliothèque Keycloak Adapter pour Java dans le microservice.
  - Configuration du client dans le microservice pour communiquer avec le serveur Keycloak.

 3- Validation des Tokens JWT :
  - Configuration du microservice pour valider les tokens JWT émis par Keycloak, assurant que seules les demandes authentifiées avec un token valide sont autorisées.

 4 -Gestion de l'Authentification et de l'Autorisation :
  - Implémentation de la gestion de l'authentification et de l'autorisation dans le microservice en utilisant les informations extraites des tokens JWT.


