## Demostración 
Hem fet un petit codi en pyton que el que fa es comptar cuans segons tarda en fer un **SELECT** directament al postgres i després fent diferents operacions el fica a la Base de dades Redis,
Com es pot comprovar en aquesta captura i en el següent grafic, fent només el **SELECT** en postgres tarda 3.3808646202087402 segundos i en canvi utlitzant la cache tarda 0.0044786930084228516 una autentica pasada

## Explicació Codi
```
python
import psycopg2
import redis
import time
import matplotlib.pyplot as plt

start_time_pg = time.time()
pg_conn = psycopg2.connect(
    dbname="Redis", user="postgres", password="P@ssw0rd", host="192.168.56.110"
)
end_time_pg = time.time()
pg_connection_time = end_time_pg - start_time_pg

start_time_redis = time.time()
redis_conn = redis.Redis(host='192.168.56.110', port=6379, db=0)
end_time_redis = time.time()
redis_connection_time = end_time_redis - start_time_redis
```
Primer de tot importemt les llibrererias neceserias i fem la conexió tant a postgres com a redis

start_time_query_pg = time.time()
pg_cursor = pg_conn.cursor()
pg_cursor.execute("SELECT * FROM public.Redis")
resultado = pg_cursor.fetchall()
end_time_query_pg = time.time()
pg_query_time = end_time_query_pg - start_time_query_pg


start_time_redis_op = time.time()
redis_conn.set('clave_ejemplo', 'valor_ejemplo')
valor = redis_conn.get('clave_ejemplo')
end_time_redis_op = time.time()
redis_op_time = end_time_redis_op - start_time_redis_op
print("Postgres:", end_time_query_pg - start_time_query_pg, "segundos")
print("Redis:", end_time_redis_op - start_time_redis_op, "segundos")
# Gráfico de barras
operations = ['Consulta en PostgreSQL', 'Operaciones en Redis']
times = [pg_query_time, redis_op_time]

plt.bar(operations, times)
plt.xlabel('Operaciones')
plt.ylabel('Tiempo (segundos)')
plt.title('Redis I Postgres')
plt.xticks(rotation=45)
plt.show()
