# Merge/Rebase ? 

Dans git il y a 2 solutions pour rapporter notre branche de travaille à la branche principale : 

- Merge 
  
- Rebase
	
Les deux commandes arrivent à peu près au même résultat, c'est à dire une mise à jour de la branche souhaitée,  mais le fonctionnement et la finalité diffèrent un peu. 

Pour commencer prenons l'exemple d'une branche principale nommée main. De cette branche nous allons travailler sur une nouvelle feature donc nous allons créer une nouvelle branche. 
Cependant dans le contexte d'un travail en équipe il est possible que la branche main évolue également. 
Nous aurions alors un historique de commit dit forké comme ceci : 

![image](https://user-images.githubusercontent.com/95683483/217848195-c8ba8eab-e4a8-4687-b6fd-50431dd0a62e.png)

Enfin supposons que certaines fonctionnalités dans les commits de main nous sont utiles dans notre branche feature nous aurons donc besoin de les récupérer. C'est à ce moment qu'interviens alors notre merge ou notre rebase. 

## Merge : 
La solution la plus simple est d'utiliser un git merge. 
2 possibilités pour merger des commits de main dans feature : 

```
Git checkout feature
Git merge main
```

Ici on se place dans la branche cible puis on merge les commits venant de la branche source. 
		
```
Git merge feature main
```

Ou ici nous faisons la même chose mais en une commande. 
		
### Que fait merge ?  
Avec ces actions nous allons donc avoir un commit de merge agissant pour fusionner les données de nos branches. 
	
![image](https://user-images.githubusercontent.com/95683483/217849435-55259bda-b621-439a-a612-33c823493bb2.png)
	
L'avantage est que les branches ne sont pas altérées (dans ce cas la branche main).
Cependant si une branche main est particulièrement active alors il y aura un certains nombre de commit de merge pouvant polluer notre branche feature

## Rebase : 
La seconde solution est donc le rebase. 
Au lieu de créer un commit de merge les branches sont en quelques sortes fusionnées et une seule branche existe après un rebase. 
En rentrant ces commandes du coup :

```
Git checkout feature
Git rebase main 
```
	
De ce fait rebase déplace la branche feature à la pointe de la branche main. On réécris donc l'historique du projet, de la branche main. 
	
![image](https://user-images.githubusercontent.com/95683483/217850534-2acb9c77-e1cd-4967-a0e0-f50a7c7ddcf1.png)
	
L'avantage est d'avoir un historique bien plus propre qu'avec des merge qui génèrent des commit de merge. 
De plus l'historique est linéaire. 
En revanche si on ne suit pas la règle d'or du rebase, le rebase peut vite devenir dangereux et réécrire tout le projet, ce qui peut poser de sérieux problème dans un projet en collaboration. 
	 
### Règle d'or du Rebase : 

Celle-ci est plutôt simple il ne faut jamais rebase une branche public, il ne faut donc jamais rebase main sur une autre branche. Car dans ce cas nos commit créés sur main après la création de notre branche locale seront rebaser sur notre branche feature. 
	
![image](https://user-images.githubusercontent.com/95683483/217850805-65e5e046-c678-494a-a3e3-78f2d50371c0.png)

Et feature deviendra alors main. 


#### Source des images

https://www.atlassian.com/fr/git/tutorials/merging-vs-rebasing
