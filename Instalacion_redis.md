# Documentació per a la instal·lació de Redis a Linux

## Índex

1. [Requisits](#requisits)
2. [Instal·lació](#installaci%C3%B3)
3. [Protecció  de la Instal·lació](#Protecci%C3%B3-de-la-installaci%C3%B3)
4. [Gestió del Servei](#gestió-del-servei)
5. [Configuració i Localització d'Arxius](#configuraci%C3%B3-i-localitzaci%C3%B3-darxius)
6. [Canvi de Port](#canvi-de-port)
7. [Connexió a la Base de Dades](#connexió-a-la-base-de-dades)
8. [Demostracion](Demostració.md)
9. [Atras](README.md)

## Requisits

Abans de començar amb la instal·lació, assegureu-vos de tenir els paquets instal·lats següents:

```bash
sudo apt install lsb-release curl gpg
```

A més, afegirem la clau d'autenticació i el repositori Redis al nostre sistema:

```bash
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list
```

## Instal·lació

Un cop configurats els repositoris, actualitzem la llista de paquets disponibles i instal·lem Redis:

```bash
sudo apt update
sudo apt install redis
```

Amb aquests passos, Redis hauria d'estar instal·lat a la màquina Linux.

## Protecció de la Instal·lació

Per defecte, Redis bloqueja l'accés remot a la base de dades. Per permetre-ho, modifiquem el fitxer de configuració `/etc/redis/redis.conf` canviant la línia `bind 127.0.0.1` a `bind 0.0.0.0`. A més, desactivem el mode protegit a `redis-cli` amb les següents ordres:
  
  1. 
```bash
redis-cli
```
  2.
```bash
CONFIG SET protected-mode no
```
![Securitzacio](Imatges/1Securitzacio.png)

## Gestió del Servei

Per gestionar el servei de Redis al sistema operatiu, utilitzem les ordres següents:

- **Arrancar el servei:**

```bash
sudo systemctl start redis
```

- **Verificar l'estat del servei:**

```bash
sudo systemctl status redis
```

- **Apagar el servei:**

```bash
sudo systemctl stop redis
```

## Configuració i Localització d'Arxius

- **Fitxer de Configuració:**
  El fitxer de configuració de Redis es troba a `/etc/redis/redis.conf`.
  ![Archivo_Configuracion](Imatges/1Archivo_Configuracion.png)

- **Dades Físiques:**
  Redis no utilitza emmagatzematge al disc; les dades es mantenen a la memòria RAM.

## Canvi de Port

El port per defecte on Redis escolta és `6379`. Per canviar-lo, es modifica el fitxer de configuració `/etc/redis/redis.conf`.
  ![Canvi de Port](Imatges/1(Puerto).png)


## Connexió a la Base de Dades

Per connectar-vos a la base de dades Redis, podeu fer servir eines de gestió com Redis Insight o programes que admetin connexions a Redis.
  ![Canvi de Port](Imatges/1Comprovación_Conexion_BBDD_redis-insight.png)

### Membres del Grup
- Antonio Encarnación Montero.
- Manuel Antonio Alvarez Lopez.
- Alex Martinez Rubio.
