# Voici une petite aide d'utilisation simple de la commande git stash. 

## Git stash ?
Git stash permet de stocker, de mettre de côté des modifications afin de potentiellement passer d'une branche à l'autre par exemple. 
Ces modifications ne sont donc pas supprimés et peuvent être récupérées. 

Pour cela voici la marche à suivre : 
	
Pour savoir quel "stash" nous souhaitons récupérer nous pouvons regarder la liste de nos stash via la cmd suivante git stash list.
	
Ensuite nous pouvons donc récupérer le stash via l'identifiant stash@{integer}
	
Puis nous pouvons appliquer notre stash en faisant soit la commande ```git stash apply stash@{integer}``` soit ```git stash pop stash@{integer}```
	
## Différence entre apply et pop : 
### Apply : 
Cette option va nous permettre de récupérer notre stash mais de la maintenir dans la liste de sauvegarde. 
		
### Pop : 
Cette option va récupérer notre stash mais le supprimer de la liste de sauvegarde. 
		
## Cleaner notre liste de stash : 
Pour cleaner notre liste de sauvegarde nous utiliserons la cmd :

```git stash clear```
	
Mais nous pouvons également choisir de supprimer un fichier de sauvegarde particulier et dans ce cas nous utiliserons la cmd :

```git stash drop stash@{integer}```
