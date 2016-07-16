# collaborativeRdf
Construire son petit BigData Rdf pour faciliter la collaboration

mettre en place un serveur en temps reel basé sur le chat de socket.io

recuperer le repertoire "chat" du repertoire example de socket.io 
modifier la ligne 
var io = require('../..')(server);
en 
var io = require('socket.io')(server);
dans index.js


