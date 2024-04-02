## Demostració

Hem creat un petit codi en Python que compta quant temps tarda a fer una SELECT directament a PostgreSQL i després, fent diferents operacions, ho guarda a la base de dades Redis. Com es pot veure en aquesta captura i en el següent gràfic, només fent el SELECT en PostgreSQL tarda 3.3808646202087402 segons, mentre que utilitzant la caché, només tarda 0.0044786930084228516 segons. És una autèntica passada.

## Codi utilitzat
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

# Gráfico de barras
operations = ['Consulta en PostgreSQL', 'Operaciones en Redis']
times = [pg_query_time, redis_op_time]

plt.bar(operations, times)
plt.xlabel('Operaciones')
plt.ylabel('Tiempo (segundos)')
plt.title('Redis I Postgres')
plt.xticks(rotation=45)
plt.show()
