# extension_v1

#!/bin/python3

                         #############
##########################EXPLICATION##########################
                         #############

"""

version : 2e version du code
but : liste les extentions des fichiers se trouvant dans un repertoire indiqué en amont

"""

# On importe le module os, qui permet d'interagir avec le système d'exploitation
import os 

chemin_repertoire = "/home/875larz/Pictures"



                         ######
##########################CODE#########################
                         ######


def find_extension(chemin_repertoire):
   
    # On liste tous les éléments (fichiers et dossiers) dans le répertoire spécifié
    liste_fichiers = os.listdir(chemin_repertoire)
    # On affiche cette liste pour voir ce qu'il y a dans le répertoire
    print(liste_fichiers) 

    extensions = []  # On initialise une liste vide pour stocker les extensions des fichiers
    

    # Pour chaque élément de la liste, on vérifie si c'est bien un fichier (et non un dossier)
    for fichier in liste_fichiers:
        # Si c'est un fichier, on récupère son extension en séparant le nom sur le dernier point
        if os.path.isfile(os.path.join(chemin_repertoire, fichier)):
            extension = fichier.split(".")[-1]
            extensions.append(extension)  # On ajoute l'extension à notre liste d'extensions
    
    return extensions  # La fonction retourne la liste des extensions trouvées



                         ###########
##########################AFFICHAGE##########################
                         ###########

extensions = find_extension(chemin_repertoire)
print(extensions)  # On affiche la liste des extensions de fichiers trouvées
