DAC/ACL : Groupe 3
Guide (readme)
Etape 1 : ouvrir le terminal sur Ubuntu en combinant les touches
		Ctrl + Alt + T
Etape 2 : Création le dossier autoecole avec la commande 
		sudo mkdir  autoecole
Etape 3 : accéder au dossier avec la commande 
		cd autoecole
Etape 4 : création des utilisateur moniteur, apprenant et administrateur avec la commande
		sudo adduser moniteur
		sudo adduser apprenant
		sudo adduser administrateur
Etape 5 : création  des groupes gmoniteur, gapprenant et gadministrateur avec la commande
		sudo groupadd gmoniteur
		sudo groupadd gapprenant
		sudo groupadd gadministrateur
Etape 6 : ajoutons les utilisateurs à leur groupe respectif avec la commande
		sudo adduser moniteur gmoniteur
		sudo adduser apprenant gapprenant
		sudo adduser administrateur gadministrateur
Etapes 7 : création des fichier cours et planning avec les commandes
		touch planning
		touch cours
	Ensuite taper la commande ls pour afficher les fichier crée.




Etape 8 : attribution les accès au fichier en fonction des qualité.
•	Pour le groupe des moniteurs gmoniteur on leur accordent les accès en lecture et en écriture grâce au lettre rw au fichier cours et en lecture au fichier planning

sudo seftacl -m g :gmoniteur : rw cours

sudo seftacl -m g :gmoniteur : r planning


•	Pour le groupe des apprenant gapprenant on leur accordent les accès en lecture grâce au lettre r au fichier cours et planning 

sudo seftacl -m g :gapprenant : r cours

sudo seftacl -m g :gapprenant: r planning


•	Pour le groupe des administrateur gadministrateur on leur accordent les accès en lecture, écriture et exécution grâce au lettre rwx au fichier cours et planning 


sudo seftacl -m g :gadministrateur : rwx cours

sudo seftacl -m g :gadministrateur : rwx planning

Etape  9 : Maintenant vérifions si nos commande on marcher. Pour cela tapons la commande 

		sudo getfacl cours
		sudo getfacl planning

Le résultat nous montre les diffèrent accès des groupes au fichier.

Merci ! abonne toi et partage
