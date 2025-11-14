<h2> Vérification du bon fonctionnement : </h2>

Depuis l'hôte en passsant par le proxy :
-> Curl [IP_Conteneur_Proxy]:80/health ->
Renvoie 
*"db	"reachable" status	"ok"*
si correct.

Depuis une autre machine en passant par la VM Docker :
-> Navigateur : http://[IP_Machine_Docker]:8080/health ->
Affiche 
*"db	"reachable" status	"ok"*
si correct.

**Problème en accèdant à la base de données :** error "'cryptography' package is required for sha256_password or caching_sha2_password auth methods" status "error"
Solution : dans le compose.yml : command: --default-authentication-plugin=mysql_native_password
Explication : PyMySQL ne supporte pas nativement le plugin par défaut de MySQL 8

**Problème en accèdant à la base de données :** Erreur de connexion (2003) Connection refused
Solutions : Ajouter un sleep dans le docker-compose.yml pour attendre MySQL (command: sh -c "sleep 15 && python app.py")
Explication : Flask démarre avant que MySQL soit prêt.

<h3>Hub docker :</h3>
-> https://hub.docker.com/r/wilmew/tp-networks-app









