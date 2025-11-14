Vérification du bon fonctionnement :

Depuis l'hôte en direct sur l'application :
-> Curl [IP_Conteneur_APP]:5000 
Renvoie "Hello from app!" si correct.

Depuis l'hôte en passsant par le proxy :
-> Curl [IP_Conteneur_Proxy]:80
Renvoie "Hello from app!" si correct.

Depuis une autre machine en passant par la VM Docker :
-> Navigateur : http://[IP_Machine_Docker]:8080
Affiche "Hello from app!" si correct.
