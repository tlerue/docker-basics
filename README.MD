# Docker Commandes

Node.js Hello World on CentOS using [docker][].

## Sources

- [Commandes de bases][https://www.docker.com/tryit]

## Liste des commandes de bases

-   Recherche d'images

        docker search <string>
		# docker search tutorial

-   Récupérer l'image

        docker pull <repository_name>
		# docker pull learn/tutorial

-   Lancer une commande dans le conteneur

        docker run <repository_name> <command>
		# docker run learn/tutorial echo "hello world"

-   Installer des packages dans l'image

        docker run <repository_name> apt-get install -y <package>
		# docker run learn/tutorial apt-get install -y ping
		
-   Trouvez l'ID du contener créé en installant le package

        docker ps -l		
		
-   Enregistrer les changements

        docker commit <ID_du_conteur_créé> <nouveau_repository_name>
		# docker commit 698 learn/ping	

		
-   Tester le package installé

        Docker commit <nouveau_repository_name> <commande_installée>	
		# docker run learn/ping ping google.com

-   Voir la liste de tous les conteneurs qui tournent

        docker ps
		
-   Inspecter les conteneurs

        docker inspect <ID_du_conteur>
		

-   Envoyer les images sur le Hub docker

        docker push <nouveau_repository_name>
		
## Liste des commandes de bases depuis un DockerFile

-   A partir du repertoire ou est situé le DockerFile

        sudo docker build -t <your username>/centos-node-hello .

-   Lister les images

        sudo docker images

-   Lancer l'image 

        sudo docker run -p 49160:8080 -d <your username>/centos-node-hello
		-d : le conteneur tourne en detached mode, en background
		
-   Get container ID

        sudo docker ps

-   Print app output

        sudo docker logs <container id>		