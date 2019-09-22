Jusqu'à présent, tous les conteneurs que nous avons utilisés ont exécuté une commande et sont sortis. Nous allons maintenant gérer les conteneurs de manière interactive. Nous explorerons également l'immuabilité.

1) Créer un conteneur à l'aide de l'image Ubuntu 16.04 et le connecter au terminal

`docker run -it ubuntu:16.04 bash`{{execute}}

Cette commande exécute le conteneur, s'attache au flux d'entrée standard et obtient un pseudo-terminal. Pour le processus du conteneur, nous spécifions bash pour obtenir le terminal.

1)  Créer un fichier avec la command touch:

`touch test && ls`{{execute}}

2) Vous devriez voir le fichier créé dans le répertoire racine du conteneur. Maintenant, sortez : `exit`{{execute}}

3) Exécutez le conteneur de nouveau:

`docker run -it ubuntu:16.04 ls`{{execute}}

Notez que le fichier a disparu. C'est parce que chaque fois que vous utilisez la commande run contre une image, elle crée un nouveau conteneur à partir de l'image. Toute modification apportée à un conteneur sur la base d'une image n'est pas automatiquement enregistrée dans l'image.

C'est ce qu'on appelle l'immuabilité. C'est l'un des principes clés des conteneurs, ils sont immuables. Une fois construit, il est immuable, et si vous voulez faire des changements, vous obtiendrez ainsi une nouvelle image.
