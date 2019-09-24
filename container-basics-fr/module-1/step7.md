Dans cette section, nous apprendrons comment arrêter, démarrer et enlever des conteneurs.

1) Exécutez un docker Ubuntu:16.04 en mode détaché à l'aide de la fonction sommeil.

`docker run -idt --name sleepy ubuntu:16.04 sleep 60m`{{execute}}

`docker container ps`{{execute}}

2) Interagissons maintenant avec le terminal du conteneur sleepy :

`docker container exec -it sleepy bash`{{execute}}

3) Créez un fichier et sortez du terminal de conteneurs :

`touch TEST.txt && ls`{{execute}}

`exit`{{execute}}

4) Arrêtez le conteneur sleepy et redémarrez-le :

`docker container stop sleepy`{{execute}}

`docker container ls`{{execute}}

`docker container start sleepy`{{execute}}

5) Interagissons de nouveau avec le terminal du conteneur sleepy :

`docker container exec -it sleepy bash`{{execute}}

`ls`{{execute}}

`exit`{{execute}}

Notez que le fichier TEST.txt est toujours là. C'est parce que nous nous avons seulement arrêté et démarré et que nous interagissons avec le même conteneur que celui sur lequel nous avons créé le fichier.

Maintenant, arrêtons-nous et enlevons le conteneur sleepy :

`docker container stop sleepy`{{execute}}

`docker container ps`{{execute}}

`docker container ps -a`{{execute}}

`docker container rm sleepy`{{execute}}

`docker ps -a`{{execute}}
