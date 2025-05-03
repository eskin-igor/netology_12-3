# netology_12-3
# Домашнее задание к занятию «SQL. Часть 1»

Задание можно выполнить как в любом IDE, так и в командной строке.

## Задание 1
Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

## Решение 1

```
SELECT DISTINCT district
FROM address
WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
```
![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-1-0.JPG)

![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-1-1.JPG)

## Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

## Решение 2

```
SELECT payment_date, amount
FROM payment
WHERE amount > 10 AND payment_date BETWEEN '2005-06-15 00:00:00' AND '2005-06-18 23:59:59';
```
![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-2-1.JPG)

![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-2-2.JPG)

## Задание 3

Получите последние пять аренд фильмов.

## Решение 3

```
SELECT rental_date
FROM rental
ORDER BY rental_date DESC
LIMIT 5;
```
![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-3-1.JPG)

![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-3-2.JPG)

## Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie.  
Сформируйте вывод в результат таким образом:  
* все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
* замените буквы 'll' в именах на 'pp'.

## Решение 4

```
SELECT CONCAT((REPLACE(LOWER(first_name), 'll', 'pp')), " ", LOWER(last_name)) AS 'Имя и фамилия' , active
FROM customer
WHERE active = 1 AND first_name IN ('Kelly', 'Willie');
```

![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-4-1.JPG)

![](https://github.com/eskin-igor/netology_12-3/blob/main/12-3/12-3-4-2.JPG)
