Jetons maintenant un coup d'œil à quelques journaux de conteneurs. C'est un autre bon moyen de dépanner les problèmes de conteneurs.

Exécutons à nouveau le conteneur NGINX et regardons les journaux :

`docker container run -p 80:80 -d --rm --name nginx nginx`{{execute}}

`docker container ps`{{execute}}

`docker container logs nginx`{{execute}}

`docker container logs -f nginx`{{execute}}

En utilisant le commutateur -f, nous sommes maintenant en train de suivre les journaux en direct. Visitez la page NGINX ici et vous verrez la mise à jour des logs. https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/
