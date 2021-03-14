# À propos :
* [Le projet](#Le-projet)
* [Ce repository](#Ce-repository)


## Le projet :

Partant sur la base de mon dernier projet de formation, pour lequel on me demandait de réaliser le MVP d'un réseau social d'entreprise – voir mon [portfolio](https://portfolio-christophe-bouriel.netlify.app/#projet-5) – j'ai décidé de continuer à le développer afin de pratiquer, d'intégrer peu à peu des connaissances qui me manquent encore... et parce que je suis curieux et que j'aime coder !  

Le site a été déployé en utilisant les services cloud suivant : Netlify pour ce front-end, Heroku pour le back-end, Cloudinary pour stocker les images car le précédent ne me permet pas de conserver les fichiers créés entre deux démarrages, et enfin ClearDB pour la base de données MySQL. Vous pouvez y accéder en cliquant [ici](https://shareplace-evo.netlify.app).

On peut également accéder au repository pour faire fonctionner l'application avec Docker en cliquant [ici](https://github.com/ChristopheBouriel/SharePlace-Evo-Docker).  
Toutes les informations sont dans le README, notamment les noms d'utilisateur et mots de passe pour se connecter sans avoir à créer de profil ou essayer le mode « Modérateur » – lors de la création du container MySQL, des données sont insérées pour permettre une démonstration immédiate.  

Les fonctionnalités déjà implémentées sont détaillée dans le document **wiki** du repository du front-end.  

Vous pourrez trouvez plus d'informations sur le projet initial et cette version améliorée en consultant mon portfolio :
https://portfolio-christophe-bouriel.netlify.app  


## Ce repository :

### L'API
Ce repository concerne le back-end de l'application, développé avec **Node.js** et **Express**, et vous pouvez trouver le front-end développé avec **Angular** en suivant [ce lien](https://github.com/ChristopheBouriel/SharePlace-Evolution-UI.git).  

Afin d'avoir un back-end aussi sécurisé que possible compte tenu de mes connaissances actuelles, j'ai essayé de suivre les recommandations de l'OWASP concernant les points sur lesquels le développeur peut intervenir.  
J'ai donc installé des packages téléchargés depuis le registre npm, j'ai écrit mes propres middlewares pour la validation des entrées de l'utilisateur, mais j'ai également ajouté des vérifications sur la plupart des routes en fonction du type de requête : par exemple, afin d'être sûr que l'utilisateur le souhaite modifier ou supprimer une publication, un commentaire ou un profil, c'est le même qui l'a créé.  

 #### Les packages pour la sécurité :
 * [express-rate-limit](https://www.npmjs.com/package/express-rate-limit)
 * [bcrypt](https://www.npmjs.com/package/bcrypt)
 * [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)
 * [xss-filters](https://www.npmjs.com/package/xss-filters)
 * [helmet](https://www.npmjs.com/package/helmet)


### Installation :
Pour installer l'API sur votre ordinateur, exécutez les instructions suivantes :

1. Lancer une instance sur un serveur MySQL local et créez la base de données. Pour ceci, toutes les instructions se trouvent dans le fichier sample.sql dans le dossier racine du projet.
2. Clonez le repository :  
	`git clone https://github.com/ChristopheBouriel/SharePlace-Evolution-API.git`
2. Entrez dans le répertoire racine du projet :  
	`cd SharePlace-Evolution-API`
4. Créez un fichier .env et copiez les variables d'environnement suivantes avant d'enregistrer :

		DB_USER='votre nom d'utilisateur'
		DB_PASS='votre mot de passe'
		DB_NAME=shareplacevolution
		DB_TOK='votre chaine de caractère pour le token'
3. Installez le projet :  
	`npm install`
4. Lancez le serveur :  
	`node server`  

Celui-ci devrait fonctionner à l'adresse `http://localhost:3000`
