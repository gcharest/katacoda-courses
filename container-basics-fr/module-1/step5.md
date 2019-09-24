Dans cette section, nous allons apprendre comment interagir avec un conteneur Docker déjà en cours d'exécution et forcer les conteneurs à continuer à fonctionner en arrière-plan.

1) Exécutez l'image NGINX (un serveur web qui gère les requêtes http externes à l'hôte) et connectez-vous à STDIN et à un terminal :

`docker container ls`{{execute}}

`docker container run -it --rm --name nginx nginx`{{execute}}

Remarquez que vous êtes déposé dans une borne interactive, mais que vous ne pouvez rien faire. Appuyez sur ctrl+c pour quitter.

2) Maintenant, lancez l'image NGINX en mode détaché en utilisant le commutateur -d :

`docker container ls`{{execute}}

`docker container run -p 80:80 -d --rm --name nginx nginx`{{execute}}

`docker container ls`{{execute}}

Notez que le mappage de port - port 80 dans le conteneur a été mappé au port 80 sur l'hôte.
Aller au serveur https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/ et consultez la page d'accueil de NGINX.

3) Accédez au conteneur détaché par le terminal :

`docker container exec -it nginx bash`{{execute}}

`exit`{{execute}}

`docker container ls`{{execute}}

4) Vous pouvez également exécuter des commandes et transmettre le résultat à la console sans l'attacher à un terminal dans le conteneur :

`docker container exec -it nginx cat /etc/issue`{{execute}}. Nous pouvons voir que cette commande nous montre quelle version de linux le conteneur est en cours d'exécution. Si nous lançons `cat /etc/issue`{{execute}} dans notre terminal, nous pouvons voir que notre OS hôte est différent de celui du conteneur.

5) Arrêtons le conteneur `docker kill nginx`{{execute}}

Maintenant que nous avons arrêté le conteneur, il ne s'affiche pas non plus lorsque nous exécutons `docker container ps -a`{{execute}}. C'est parce que nous avons utilisé l'argument --rm dans la commande d'exécution originale qui supprime complètement le conteneur quand il s'arrête.

Vous utiliseriez les commandes interactives pour dépanner ou déboguer les conteneurs
