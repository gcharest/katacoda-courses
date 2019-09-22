Les commandes ci-dessous vous permettront de travailler avec des images.

1) Liste des images

`docker image ls`{{execute}}

2) Tirez l'image hello-world du registre d'images de conteneurs (dans ce cas, Docker Hub)

`docker image pull hello-world`{{execute}}

3) Tirez la dernière image Alpine du registre d'images d6) Énumérer à nouveau les images. Notez que Alpine n'est plus listée conteneurs

`docker image pull alpine:latest`{{execute}}

4) Lister les images sur la machine locale

`docker image ls`{{execute}}

5) Supprimer les images stockées localement

`docker image rmi alpine:latest`{{execute}}

6) Énumérer à nouveau les images. Notez que Alpine n'est plus listé

`docker image ls`{{execute}}
