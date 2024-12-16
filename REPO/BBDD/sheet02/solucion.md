# Sakila
 
## Nivel Básico

### Selecciona todos los registros de una tabla


**Consulta todos los datos de la tabla film** 

SOL:
`SELECT * FROM film;`

### Filtrado de datos

**Encuentra todas las películas con una duración ( length ) mayor a 120 minutos**

SOL: `SELECT * FROM film WHERE length > 120;`

**Busca clientes cuyo apellido sea "Smith" en la tabla customer**

SOL: `SELECT * FROM customer WHERE last_name = "Smith";`

### Ordenar datos

**Ordena las películas de film alfabéticamente por el título.**

SOL: `SELECT * FROM film ORDER BY title ASC ;`

**Ordena las películas por duración de mayor a menor.**

SOL: `SELECT * FROM film ORDER BY length DESC ;`

### Usar funciones agregadas

**Cuenta cuántos actores hay en la tabla actor**

SOL: `SELECT COUNT(*) FROM actor ;`

**Encuentra la duración promedio de las películas en la tabla film**

SOL: `SELECT AVG(length) FROM film ;`

### Filtrar con operadores

**Encuentra todas las películas con una clasificación ( rating ) de 'PG' o 'R'**

SOL: `SELECT * FROM film WHERE rating = "PG" OR rating = "R";`

**Muestra los clientes con last_name que terminen en "FORD"**

SOL: `SELECT * FROM customer WHERE last_name LIKE "%FORD";`

## Nivel Intermedio

### JOIN Simple

**Muestra el nombre completo de los actores y los títulos de las películas en las que han actuado (usa las tablas actor , film_actor y film )**

SOL: `SELECT title, first_name, last_name FROM film_actor JOIN film ON film_actor.film_id = film.film_id JOIN actor ON film_actor.actor_id = actor.actor_id;`

### Filtrar con JOIN

**Encuentra los títulos de películas alquiladas por el cliente con el nombre "MARY SMITH"**

SOL: `SELECT title, first_name, last_name FROM rental JOIN customer on rental.customer_id = customer.customer_id JOIN inventory ON rental.inventory_id = inventory.inventory_id JOIN film ON inventory.film_id = film.film_id WHERE first_name ="Mary" AND last_name = "Smith";`


### Subconsultas

**Encuentra los clientes que hayan alquilado más de 20 películas.**

SOL: `SELECT first_name, rental.customer_id, COUNT(rental.customer_id) FROM rental JOIN customer ON rental.customer_id = customer.customer_id  GROUP BY rental.customer_id HAVING COUNT(*) > 20;`


### Agrupacion y agregacion

**Encuentra todas las películas con una clasificación ( rating ) de 'PG' o 'R'**

SOL: ``

**Muestra los clientes con last_name que terminen en "FORD"**

SOL: ``

### Consultas multiples con JOIN

**Encuentra todas las películas con una clasificación ( rating ) de 'PG' o 'R'**

SOL: ``

**Muestra los clientes con last_name que terminen en "FORD"**

SOL: ``