Les commandes ci-dessous fonctionnent avec les images pour créer et lister les conteneurs.

1) Faire l'inventaire des images et des conteneurs actuels

`docker image ls`{{execute}}

`docker container ls`{{execute}}

1) Exécuter l'image hello-world

`docker container run hello-world`{{execute}}

> Notez que l'image n'avait pas besoin d'être téléchargée puisque nous l'avons déjà téléchargée à l'étape 2.

3) Et si nous supprimions l'image hello-world de la machine locale?

`docker image rmi -f hello-world`{{execute}}

4) Essayez maintenant d'exécuter à nouveau le conteneur hello-world, cette fois en définissant le nom hello-world.

`docker run --name hello-world hello-world`{{execute}}

Remarquez comment l'image est automatiquement téléchargée à partir du registre d'images du conteneur.

Regardez les conteneurs en cours d'exécution `docker container ls`{{execute}} Le conteneur hello-world n'est pas listé parce qu'il a été executé jusqu'au bout.

Regardez tous les conteneurs, y compris ceux qui se sont arrêtés `docker container ls -a`{{execute}} Maintenant nous voyons hello-world listé comme un conteneur stoppé et est nommé "hello-world" parce que nous avons défini ce nom de conteneur au moment de l'exécution.

Affichez toutes les informations sur un conteneur. Dans ce cas, allons inspecter hello-world. `docker container inspect hello-world`{{execute}} Cette commande affiche des informations détaillées sur le conteneur. Prenez le temps d'y jeter un coup d'œil.

D'autres commandes de conteneur :

a) Énumérer les conteneurs en exécution

`docker container ps`{{execute}}

b)  Énumérer tout les conteneurs

`docker container ps -a`{{execute}}

c) Énumérer les 2 conteneurs les plus récents

`docker container ps -n 2`{{execute}}

d) Énumérer le dernier conteneur a avoir été executé

`docker container ps -l`{{execute}}
