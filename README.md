# collaborativeRdf
Construire son petit BigData Rdf pour faciliter la collaboration

Mettre en place un serveur en temps reel
----------------------------------------


+ recuperer le repertoire "chat" du repertoire example de [socket.io](https://github.com/socketio/socket.io/tree/master/examples/chat)

+ dans index.js, modifier la ligne *var io = require('../..')(server);* en *var io = require('socket.io')(server);*
+ verifier le fonctionnement du serveur en temps reel comme préconisé sur la page de l'exemple [socket.io](https://github.com/socketio/socket.io/tree/master/examples/chat): 
> cd chat
> npm install
> node .

+ A ce stade vous devriez avoir un serveur de chat opérationnel, on va maintenant le modifier pour qu'il accepte les triplets Rdf

Modification du serveur de chat pour traitement de triplets RDF
---------------------------------------------------------------



 


