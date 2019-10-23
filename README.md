BrowserQuest
============

Ce sont les trois partis majeur:

* Le serveur marche avec Node.js
* Le client utilise le javascript du navigateur
* La base de donné est directement stocké sur le Raspberry

Navigateur Supporté
---------------

* Firefox - Marche correctement.
* Chrome - Marche correctement.
* Chromium - Marche correctement.
* Opera 15.x - Marche correctement.
* Opera 12.16 - La musique de fond ne se joue pas.  Sinon tout marche (Très lent).
* Safari 6.x - La musique de fond ne se joue pas.  Sinon tout marche.
* IE 10.x - Ne marche pas.  Autre version pas testé.

Comment avoir ce qui faut
-------------------

Pour monter votre serveur et le faire fonctionner c'est simple. Vous avez besoin de suivre ces installations:

* Node.js ← Versions 0.8.x-0.10.x marche.  **N'utilisez pas 0.6.x, ceci [ne fonctionne pas](https://github.com/senchalabs/connect/issues/858).**
* gcc-c++ ← optionnel.  
* GNU make ← optionnel.  
* Memcached ← optionnel. Ceci est nécessaire pour faire fonctionner metrics.
* zlib-devel ← C'est le nom du package Fedora/RHEL, d'autre peuvent etre legerement different. 
* Redis server ← C'est necessaire pour que le jeu se connecte a la base de donné.

Raspberry
------

    $ sudo apt-get update
    $ sudo apt-get upgrade
    $ sudo apt-get install g++ make memcached libncurses5 redis-server git -y
    $ curl -sL https://deb.nodesource.com/setup | sudo bash -
    $ sudo apt-get install nodejs

Clonez ce repo github:

    $ git clone git://github.com/browserquest/BrowserQuest.git
    $ cd BrowserQuest

Quand c'est installé les package Node.js doivent etre installé:

    $ npm config set registry http://registry.npmjs.org/
    $ npm install -d

Quand c'est installé lancé le serveur:

    $ node server/js/main.js

Le serveur BrowserQuest demarre, il est censé vous affiché ca:

    $ node server/js/main.js
    This server can be customized by creating a configuration file named: ./server/config_local.json
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Starting BrowserQuest game server...
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world1 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world2 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world3 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world4 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world5 created (capacity: 200 players).
    [Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Server (everything) is listening on port 8000

Si ca vous affiche ca c'est bon.  Il ne devrait y avoir aucun avertissement ou erreur.

Utilesez votre navigateur, connectez vous au port 8000 du serveur entré ci-dessus. La page
de debut de BrowserQuest devrait s'afficher, et le jeu fonctionner.

License
-------

Creer/Traduit par Famalo

