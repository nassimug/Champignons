# Ce champignon est-il comestible ?
<p><strong> L'objectif de ce projet est d'apprendre, grâce au machine learning, à reconnaître si un champignon est comestible ou toxique en fonction de sa couleur, de sa forme et de la texture de sa cuticule. Pour ce faire, nous nous baserons sur le site : <br> https://ultimate-mushroom.com/. </strong></p> <br/>

## Collecte de données avec Python
<p>Pour la première partie, nous allons collecter toutes les données du site <strong>Ultimate Mushroom</strong> et les sauvegarder dans un fichier CSV. Pour cela, j'ai créé le fichier Python ShroomLearning.py qui va parcourir la page principale du site, analyser chaque lien, et collecter les données nécessaires pour l'apprentissage, avant de les sauvegarder dans data/champignons.csv</p> <br/>

## Manipulation des données
<p>Dans cette partie, nous allons convertir les données CSV dans un format compatible avec notre modèle d'IA, afin de faciliter son apprentissage. Nous utiliserons la bibliothèque <i>'pandas'</i> en Python pour manipuler nos données en utilisant un DataFrame. Tout d'abord, nous configurerons notre DataFrame et effectuerons des calculs préliminaires pour garantir l'exactitude des données. Ensuite, nous convertirons les descriptions de couleur en codes RGB et catégoriserons toutes les formes et textures en utilisant un encodage binaire (0 ou 1), afin de préparer les données selon les exigences du modèle. Le script <strong>2ejalon.ipynb</strong> est chargé de réaliser ces opérations.</p> <br/>

## Apprentissage et optimisation
<p>Enfin, nous entamerons le processus d'entraînement en utilisant la bibliothèque scikit-learn. Nous testerons deux types de modèles : <strong>Support Vector Machine (SVM)</strong> et <strong>Arbre de Décision</strong>. Pour chaque modèle, nous effectuerons des sessions d'entraînement avec et sans mise à l'échelle pour comparer les différences de prédictions à l'aide de scores de précision et de matrices de confusion. Cette approche nous aidera à comprendre l'importance d'éviter le surapprentissage de nos modèles. Le même fichier mentionné précédemment, <strong>2ejalon.ipynb</strong>, est chargé de ce processus d'apprentissage. Après avoir terminé l'entraînement, nous utiliserons la bibliothèque <i>'joblib'</i> pour sauvegarder nos modèles entraînés pour une utilisation future.</p> <br/>

## Lancement et test de l'application
<p>Nous commençons par configurer un <strong>framework Node.js Express</strong> et créons une page web simple avec un formulaire HTML <strong>formulaire.html</strong>. Nous utilisons ensuite le fichier <strong>index.js</strong> pour gérer les requêtes serveur et implémenter le code <strong>script/predict.py</strong> pour générer des prédictions à l'aide de l'un des deux modèles.</p> <br/>

## Comment tester le projet
<ol> <li>Clonez ou téléchargez le fichier zip depuis le dépôt git.</li> <li>Installez Node.js sur votre appareil</li> <li>Ouvrez un terminal dans le répertoire du ProjetExpress</li> <li>Pour lancer le serveur local, tapez : "node index.js"</li> <li>Allez sur votre navigateur préféré et entrez le lien suivant : http://localhost:8080/form</li> <li>Remplissez les informations du champignon que vous souhaitez tester</li> <li>Soumettez et découvrez le résultat</li> </ol> <strong>Il est important de noter que les résultats peuvent ne pas être toujours précis, car le modèle d'IA utilisé dans ce processus est relativement basique.</strong>


