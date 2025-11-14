Vérification du bon fonctionnement :

Depuis l'hôte en direct sur l'application :
-> Curl [IP_Conteneur_APP]:5000/health ->
Renvoie 
"db	"reachable" status	"ok" 
si correct.

Depuis l'hôte en passsant par le proxy :
-> Curl [IP_Conteneur_Proxy]:80/health ->
Renvoie 
"db	"reachable" status	"ok" 
si correct.

Depuis une autre machine en passant par la VM Docker :
-> Navigateur : http://[IP_Machine_Docker]:8080/health ->
Affiche 
"db	"reachable" status	"ok" 
si correct.

hub docker : https://hub.docker.com/r/wilmew/tp-networks-app



