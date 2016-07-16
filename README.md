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

+ dans *chat/public/*, transformez la ligne *<input class="inputMessage" placeholder="Type here..."/>* en 
> <input class="sujetInput" placeholder="Sujet here..."/>

> <input class="objetInput" placeholder="propriete here..."/>

> <input class="proprieteInput" placeholder="Objet here..."/>

* attention , petite modif, placez ces trois lignes avant la fermeture du </div>*, ce qui devrait vous donner 
```
      <div class="chatArea">
        <ul class="messages"></ul>
		<input class="sujetInput" placeholder="Sujet here..."/>
		<input class="objetInput" placeholder="propriete here..."/>
		<input class="proprieteInput" placeholder="Objet here..."/>
      </div>
```



+ par la même occasion, modifiez le fichier style.css pour faire entrer nos trois nouveaux champs
```
.sujetInput {
  border: 10px solid #000;
  bottom: 0;
  height: 60px;
 /* left: 0;*/
  outline: none;
  padding-left: 10px;
 /* position: absolute;*/
 /* right: 0;*/
  width: 30%;
}

.proprieteInput {
  border: 10px solid #000;
  bottom: 0;
  height: 60px;
 /* left: 0;*/
  outline: none;
  padding-left: 10px;
 /* position: absolute;*/
 /* right: 0;*/
  width: 30%;
}

.objetInput {
  border: 10px solid #000;
  bottom: 0;
  height: 60px;
 /* left: 0;*/
  outline: none;
  padding-left: 10px;
 /* position: absolute;*/
 /* right: 0;*/
  width: 30%;
}
```




 



