# collaborativeRdf
* for collaborative version see [source](https://scenaristeur.github.io/dreamcatcherAutonome/) 
+ [Documentation](https://github.com/scenaristeur/dreamcatcherAutonome/blob/master/README.md)
+ Construire son petit BigData Rdf pour faciliter la collaboration.
+ Evolution : ajout de la visualisation du graphe RDF [CollaborativeRDFWithGraph](https://github.com/scenaristeur/collaborativeRDFWithP5JSGraph) (basé sur p5js, mais d'autres librairies peuvent être utilisées  : Three.js, D3.js, arbor.js...)

Voir le graphe RDF du projet
----------------------------
+ téléchargez [l'ontologie du projet](https://github.com/scenaristeur/collaborativeRdf/blob/master/ontologies/dreamcatcher.owl) et gardez-la dans un coin (ce fichier est facilement modifiable avec [Protege Desktop](http://protege.stanford.edu/) 
+ rendez-vous sur [DreamcatcherAlpha](http://smag-smag0.rhcloud.com/DreamCatcher/)
+ cliquez dans le graphe pour l'activer et appuyez sur la touche "B", pour réinitialiser le graphe ([liste des commandes de dreamcatcherBeta](http://smag-smag0.rhcloud.com/DreamCatcher/help.html) )
+ sur la gauche, en dessous de "Charger un fichier" cliquez sur le bouton "Select fichiers", et llez chercher l'ontologie précédemment téléchargée. Pour naviguer dans le graphe, utilisez les flèches comme décrit dans la [liste des commandes de dreamcatcherBeta](http://smag-smag0.rhcloud.com/DreamCatcher/help.html)


Installer un simple serveur prêt pour la collaboration lors de l'elaboration de graphes RDF : 
=====================================================
```
git clone https://github.com/scenaristeur/collaborativeRdf.git collabRDF
cd collabRDF
cd chat
npm install
node .

```
+ rendez-vous ensuite à l'adresse [http://127.0.0.1:3000](http://127.0.0.1:3000)
+ vous pouvez aussi vous connecter depuis un ordinateur présent sur votre réseau via http://adresse-ip:3000



Detail des modifications apportees au serveur de chat proposé par socket.io
===========================================================================
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

+ Dans *chat/public/*, remplacez la ligne
> <input class="inputMessage" placeholder="Type here..."/>

par 

> <input class="sujetInput" placeholder="Sujet here..."/>

> <input class="proprieteInput" placeholder="propriete here..."/>

> <input class="objetInput" placeholder="Objet here..."/>

*attention , petite modif, placez ces trois lignes avant la fermeture du </div>*, ce qui devrait vous donner 
```
      <div class="chatArea">
        <ul class="messages"></ul>
		<input class="sujetInput" placeholder="Sujet here..."/>
		<input class="objetInput" placeholder="propriete here..."/>
		<input class="proprieteInput" placeholder="Objet here..."/>
      </div>
```



+ par la même occasion, modifiez le fichier style.css pour faire entrer nos trois nouveaux champs sur une seule ligne
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

+ Vous devriez maintenant voir quelque chose de ce style


![apercu rdf socket chat](https://raw.githubusercontent.com/scenaristeur/collaborativeRdf/master/images/socket%20rdf%20chat%20dreamcatcher.png)

+ On va maintenant modifier la fonction d'envoi des informations vers le serveur
++ dans main.js trouvez les references à  inputMessage (comme var $inputMessage = $('.inputMessage'); // Input message input box)
et modifiez les pour prendre en compte les nouveaux champs de saisie (sujetInput, proprieteInput et objetInput)
```
	// var $inputMessage = $('.inputMessage'); // Input message input box
	var $sujetInput = $('.sujetInput'); // Sujet input box
	var $proprieteInput = $('.proprieteInput'); // propriete input box
	var $objetInput = $('.objetInput'); // Objet input box
```
	
+ par la même occasion , on va modifier le serveur pour recevoir ce nouveau type d'information
+ Attention, pour que les modifications de index.js (fichier serveur) soient prises en compte, il faut redemarrer le serveur


![apercu rdf socket chat](https://raw.githubusercontent.com/scenaristeur/collaborativeRdf/master/images/rdf%20subject%20predicat%20object%20socket%20chat.png)

![apercu rdf socket chat](https://github.com/scenaristeur/collaborativeRdf/blob/master/images/rdf%20owl%20ontology%20chat%20socket%20simple.png)
 


