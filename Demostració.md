## Demostració

Hem creat un petit codi en Python que comptabilitza quant temps es triga a fer una SELECT directament a PostgreSQL. Després, fent diferents operacions, ho guarda a la base de dades Redis. I torna a fer la mateixa consulta mostrant el resultat nou. Com es pot veure en aquesta captura i en el següent gràfic, la velocitat que te Redis és una autèntica passada. Fent el SELECT en PostgreSQL triga 2.588432788848877, mentre que utilitzant REDIS, Triga 0.003871917724609375 segons.
                                                                                    
  ![Grafic](Imatges/1Grafico.png)
  ![Temps](Imatges/1Temps.png)
## Codi utilitzat
```python
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
```

### Membres del Grup
- Antonio Encarnación Montero.
- Manuel Antonio Alvarez Lopez.
- Alex Martinez Rubio.

