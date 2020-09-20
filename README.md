# angular-spring-Interview-Questions
## angular
Angular Interview Questions + notes in english/frensh
### Guards
goals==> proteger les routes.<br>
<br>
Une guard est **un service** qu'Angular exécutera au moment où l'utilisateur essaye de naviguer vers la route sélectionnée. Ce service implémente l'interface canActivate, et donc doit contenir une méthode du même nom qui prend les arguments ActivatedRouteSnapshot et RouterStateSnapshot (qui lui seront fournis par Angular au moment de l'exécution) et retourne une valeur booléenne, soit de manière synchrone (boolean), soit de manière asynchrone (sous forme de Promise ou d'Observable).
# Angular Doc:
Use route guards to prevent users from navigating to parts of an app without authorization. The following route guards are available in Angular:
- CanActivate
- CanActivateChild
- CanDeactivate
- Resolve
- CanLoad
### Lazy loading                             https://angular.io/guide/router#lazy-loading
You can configure your routes to lazy load modules, which means that Angular only loads modules as needed, rather than loading all modules when the app launches. Additionally, you can preload parts of your app in the background to improve the user experience.

unsubscribe observable ==> onDestroy

NgInx serveur front, il faut copier notre packaging dans cette serveur (www/html/).

### notes NgMorocco  https://www.youtube.com/watch?v=q-VUkCtp_Ck&ab_channel=NgMorocco
@Injectable(): Decorator that marks a class as available to be injected as a dependency. 
ex:
```
@Injectable   // Please inject serviceB 
class ServiceA{
   constructor(private serviceB :ServiceB){}
}
```

## spring
swagger: specification qui permet de definir la documentation d'un api  https://swagger.io/

la partie de documentation est obligatoire.

## docker
### notes zakria:
un conteneur peut necessite une ou plusieurs images docker
une image docker est une templete pret a l'emploi avec des instructions du creation des conteneurs
image docker peut etre cree 
- a partir d'un docker file
- a partir d'une image existente, il va etre recuperer a partir d'un register docker (comme repo maven, npm),
le register par default s'appel docker hub

docker file, ce lui qui va permettre le build image docker

run image ===> l'instanciation d'un container  ==> on peut executer notre app

container est notre envirenement de devlopement qui va contenir notre app et ces dependances( java 8,...) qui sont decrites dans docker file


command:

$ docker build -t nameImage:version  path_docker_file       :lire docker file, executer step by step, cree l'image dans le repo local  (**)



$ docker run             : l'instanciation container


---
DockerFile doit etre dans la racine de notre project

pour tager une image au moment de build : docker tag ===>version   (voir **)


### notes mohamed youssfi:

Docker permet de creer des environnements ( appelees containers) de maniere a isoler des applications.

il permet de packager une application ainsi que les dependances necessaires dans un conteneur virtuel isole qui pourra etre execute sur n'importe qulle machine supportant docker

Dockerfile : decrit les dependances que notre applications a besions 

le dev cree un fichier Dockerfile conteneant les commandes que docker va executer pour construire une image docker de cette application.
 
 
 The Difference Between Ubuntu Desktop and Ubuntu Server:
 
 The main difference in Ubuntu Desktop and Ubuntu Server is the desktop environment. While Ubuntu Desktop includes a graphical user interface, Ubuntu Server does not.

This is because most servers run headless. But what does this mean? Well, they run without a traditional keyboard, mouse, and monitor setup to interact with the machine. Instead, servers are usually remotely managed using SSH. While SSH is built into Unix-based operating systems, it's pretty simple to use SSH on Windows as well.


nginx est un serveur web tres connu

$ sudo docker run -d  -p 8082:80  nginx       


-d      on arriere plan
-p     on mappe les ports   8082 le port externe , nginx quand il demerre, il utilse 80, si vous etes en dohrs du conteneur nous utilse 8082


to delete image : stop all containers that used this same image, delete theme, then delete image


EXEC Command

permet d executer une commande dans un container demarre 
ex:
demarrer un container MySQL


