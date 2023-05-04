# Patika_SQL_Odev_Tekrar
## [academy.Patika.dev](https://academy.patika.dev/)

### 1. film tablosundan 'K' karakteri ile başlayan en uzun ve replacemet_cost u en düşük 3 filmi sıralayınız.
`SELECT title,length,  replacement_cost FROM film`<br>
`WHERE title LIKE 'K%'`<br>
`ORDER BY length DESC ,  replacement_cost ASC`<br>
`LIMIT 3`

 
### 2. film tablosunda içerisinden en fazla sayıda film bulunduran rating kategorisi hangisidir?
`SELECT rating, COUNT(*) FROM film`<br>
`GROUP BY rating`<br>
`ORDER BY COUNT(*) DESC`<br>
`LIMIT 1;`

### 3. customer tablosunda en çok alışveriş yapan müşterinin adı nedir?
`SELECT customer.first_name, SUM(payment.amount)  FROM customer`<br>
`JOIN payment ON customer.customer_id = payment.customer_id`<br>
`GROUP BY customer.first_name`<br>
`ORDER BY SUM(amount) DESC`<br>
`LIMIT 1;`

### 4. category tablosundan kategori isimlerini ve kategori başına düşen film sayılarını sıralayınız.
`SELECT  COUNT(*), category.name FROM category`<br>
`JOIN film_category ON category.category_id=film_category.category_id`<br>
`JOIN film ON film.film_id = film_category.film_id`<br>
`GROUP BY category.name;`

### 5. film tablosunda isminde en az 4 adet 'e' veya 'E' karakteri bulunan kaç tane film vardır?
`SELECT COUNT(*) FROM film` <br>
`WHERE title ILIKE '%e%e%e%e%';`
