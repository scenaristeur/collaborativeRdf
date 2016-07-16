# collaborativeRdf
Construire son petit BigData Rdf pour faciliter la collaboration
Voir le graphe RDF du projet
----------------------------
+ téléchargez [l'ontologie du projet](https://github.com/scenaristeur/collaborativeRdf/blob/master/ontologies/dreamcatcher.owl) et gardez-la dans un coin (ce fichier est facilement modifiable avec [Protege Desktop](http://protege.stanford.edu/) 
+ rendez-vous sur [DreamcatcherAlpha](http://smag-smag0.rhcloud.com/DreamCatcher/)
+ cliquez dans le graphe pour l'activer et appuyez sur la touche "B", pour réinitialiser le graphe ([liste des commandes de dreamcatcherBeta](http://smag-smag0.rhcloud.com/DreamCatcher/help.html) )
+ sur la gauche, en dessous de "Charger un fichier" cliquez sur le bouton "Select fichiers", et llez chercher l'ontologie précédemment téléchargée. Pour naviguer dans le graphe, utilisez les flèches comme décrit dans la [liste des commandes de dreamcatcherBeta](http://smag-smag0.rhcloud.com/DreamCatcher/help.html)

Mettre en place un serveur en temps reel
----------------------------------------


+ recuperez le repertoire "chat" du repertoire example de [socket.io](https://github.com/socketio/socket.io/tree/master/examples/chat)

+ dans index.js, modifiez la ligne *var io = require('../..')(server);* en *var io = require('socket.io')(server);*
+ verifiez le fonctionnement du serveur en temps reel comme préconisé sur la page de l'exemple [socket.io](https://github.com/socketio/socket.io/tree/master/examples/chat): 
> cd chat
> npm install
> node .

+ A ce stade vous devriez avoir un serveur de chat opérationnel, on va maintenant le modifier pour qu'il accepte les triplets Rdf

Modification du serveur de chat pour traitement de triplets RDF
---------------------------------------------------------------



 


