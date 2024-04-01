# Descripcio Base de Dades
Redis és una base de dades NoSQL, cosa que significa que no segueix el model relacional típic de les bases de dades SQL tradicionals. En lloc d'això, Redis es basa en un model de dades de clau-valor, semblant a com funcionen els objectes JSON. Cada entrada a Redis s'emmagatzema amb una clau única associada a un valor. Aquesta estructura de dades simple i flexible permet un accés ràpid i eficient a les dades.


La captura que proporciones mostra una operació a Redis que il·lustra aquest model de dades. En aquesta captura, s'està realitzant una operació GET a Redis amb la clau "username:1000", i el resultat és el valor associat a aquesta clau, que sembla un objecte JSON amb múltiples camps, com "username", "email" , "password", etc.

Aquest enfocament de clau-valor permet un ràpid accés a les dades, especialment útil per a casos dús que requereixen alta velocitat i baixa latència, com emmagatzematge en memòria cau, sessions dusuari, sistemes de missatgeria en temps real, entre altres.

En resum, Redis és una base de dades NoSQL que utilitza un model de dades de clau-valor, semblant a com es treballaria amb un objecte JSON, proporcionant flexibilitat i rendiment per a una varietat d'aplicacions i casos d'ús.
