# Redis: Base de dades en memòria

<img src="Imatges/1Redis2.png" alt="" width="1200">


## Índex

1. [Descripció de Redis](#descripció-de-redis)
2. [Història](#història)
3. [Suport](#suport)
4. [Casos d'ús](#casos-dús)
5. [Diferents versions de la Base de Dades REDIS](#diferents-versions-de-la-base-de-dades-redis)
6. [Comparativa](#comparativa-amb-altres-bases-de-dades)
7. [Instalació de la Base de Dades REDIS](Instalacion_redis.md)
8. [Demostración](https://github.com/amartinez14-sapa/BBDD-Redis/blob/main/Demostraci%C3%B3.md)

# Descripció de Redis
Redis és una base de dades NoSQL, per tant, no segueix el model relacional típic de les bases de dades. En lloc d'això, Redis es basa en un model de dades de clau-valor, semblant a com funcionen els objectes JSON. Cada entrada a Redis s'emmagatzema amb una clau única associada a un valor. Aquesta estructura de dades simple i flexible permet un accés ràpid i eficient a les dades.

Aquest enfocament de clau-valor permet un ràpid accés a les dades, especialment útil per a casos dús que requereixen alta velocitat i baixa latència, com emmagatzematge en memòria cau, sessions dusuari, sistemes de missatgeria en temps real, entre altres.

Redis funciona de la següent Forma: 
 1.  Mira la Cache
 2.  Si no té la informació la demana a la BBDD principal, pot ser postgressql, MariaDB o qualsavol altre motor de Base De dades
 3.  Mostra la informació que té a la caché
<img src="https://github.com/amartinez14-sapa/BBDD-Redis/blob/main/Imatges/1Diagrama_Redis.png?raw=true" alt="" width="500">

## Història

Salvatore Sanfilippo, un desenvolupador italià de 33 anys conegut com a "Antirez", va iniciar el projecte Redis el 2009 amb l'objectiu de millorar els sistemes empresarials italians i aportar innovació en el camp de la tecnologia. Inicialment, va crear un prototip anomenat Redis en el llenguatge de programació C i després el va integrar a la comunitat Ruby. A través de la col·laboració i un enfocament en el desenvolupament àgil, aquesta comunitat ha contribuït significativament al creixement i l'adopció de Redis.

La plataforma de desenvolupament GitHub ha tingut un paper clau en la difusió de Redis, adoptada per empreses com Instagram. Aquesta adopció primerenca ressalta el rendiment i l'escalabilitat de Redis i demostra la seva capacitat per resoldre desafiaments empresarials a escala.

Els patrocini de Pivotal Software el 2013 i Redis Labs el 2015 van accelerar encara més el desenvolupament de Redis en proporcionar recursos addicionals i suport tècnic. El llançament de Redis 5.0 el 2018 va marcar un hito amb la introducció de Redis Streams, una estructura de dades sofisticada que amplia la funcionalitat de Redis per a casos d'ús avançats, com el maneig de fluxos de dades en temps real. Finalment, Salvatore Sanfilippo va dimitir com a administrador únic de Redis el 2020 i va ser substituït per Yossi Gottlieb i OranAgra. Aquest canvi en el lideratge del projecte reflecteix la maduresa i l'evolució contínua de Redis com a plataforma líder de gestió de dades en memòria.

### Bibliografia
- Stefano Bernardi, (2011). Entrevista amb Salvatore Sanfilippo creador de Redis. Entrevista amb Salvatore Sanfilippo, creador de Redis, que treballa a Sicília / (eu-startups.com)
- Wikipedia
- Redis - Wikipedia, l'enciclopèdia lliure.

## Suport

- **Redis Labs:** És l'empresa que dona suport oficialment al desenvolupament del software Redis de codi obert i ofereix diverses alternatives per ajudar i mantenir el funcionament de Redis.
- **Comunitat:** Brinda suport segons el Codi de Conducta del Pacte del Col·laborador, mitjançant Discord, llista de correu i Stack Overflow.
- **Amazon Web Services (AWS):** Ofereix suport per configuracions i problemes relacionats amb ElastiCache.
- **Microsoft Azure:** Proporciona suport tècnic mitjançant Azure Cache.
- **Google Cloud Platform (GCP):** Ofereix suport tècnic a través de Cloud Memorystore per a configuracions i problemes.
- **Serveis de Suport de Codi Obert:** Companyies pertanyents com percona i 2ndQuadrant també ofereixen suport tècnic a Redis.

## Casos d'ús

Redis és una base de dades ideal per a casos d'ús que requereixin alta velocitat, cau en memòria, emmagatzematge de sessions, missatgeria en espera i anàlisi en temps real.

### Exemples:

- Segmentació en temps real en xarxes socials.
- Emmagatzematge de dades de sessions en aplicacions mòbils.
- Gestió d'inventaris en el comerç electrònic.
- Sistemes de missatgeria en temps real en aplicacions de xat, entre d'altres.

## Diferents versions de la Base de Dades REDIS

- **Community Edition:** És gratuïta i de codi obert, adequada per a projectes petits o mitjans amb funcionalitats bàsiques.
- **Enterprise Edition:** Inclou versió comercial amb funcions avançades i suport. També totes les funcions de gestió, seguretat millorada, escalabilitat empresarial i suport prèmium.
- **Redis Cloud:** Serveis gestionats al núvol per a escalabilitat i manteniment automatitzat.

Redis Cloud és utilitzat per diverses plataformes al núvol, per exemple: Amazon ElastiCache, Microsoft Azure Cache for Redis, Google Cloud Memorystore.

## Comparativa amb altres bases de dades

En comparació amb altres bases de dades de la indústria, Redis destaca com a una base de dades en memòria per damunt d'altres opcions, a causa de la seva velocitat excepcional i la seva capacitat de gestionar una àmplia varietat de tipus de dades. A diferència de les bases de dades tradicionals que emmagatzemen dades en disc, Redis opera completament en la memòria, la qual cosa garanteix temps d'accés ultraràpids. A més, la seva capacitat de persistència opcional ofereix un avantatge sobre altres bases de dades en memòria, ja que permet que les dades s'emmagatzemin  en disc segons sigui necessari, proporcionant una major seguretat i flexibilitat.

En termes d'escalabilitat, Redis sobresurt en poder distribuir-se en clústers per gestionar grans volums de dades i càrregues de treball intensives. Aquesta capacitat d'escalar horitzontalment el diferencia de moltes bases de dades en memòria i el fa ideal per a aplicacions que requereixen creixement futur.

Redis també destaca com a solució d'emmagatzematge en caché. En reduir la necessitat d'accedir constantment a bases de dades més lentes o sistemes externs, millora significativament el rendiment de les aplicacions.

Un altre avantatge clau de Redis és el seu suport per a operacions atòmiques, garantint la coherència i seguretat de les dades en entorns distribuïts. Aquesta característica és especialment important en aplicacions on es requereixen operacions segures i consistents.

En resum, Redis ofereix una combinació única de velocitat, versatilitat, escalabilitat i fiabilitat que el distingeix com una millor opció  en comparació amb altres bases de dades, especialment per a aplicacions que valoren el rendiment i la capacitat d'escalar eficientment.

### Membres del Grup
- Antonio Encarnación Montero.
- Manuel Antonio Alvarez Lopez.
- Alex Martinez Rubio.
