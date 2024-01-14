# Информация о SQL

## SELECT 
   - Полная выборка данных из таблицы `customers`. <br>
     Пример: `SELECT * FROM customers;` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/367278ae-a703-46b5-ae89-48714f3088e9)

## DISTINCT используется для удаления дубликатов из результирующего набора оператора SELECT.
  - Вывод строк без ипользование `DISTINCT` из таблицы `customers` значений `91`<br> 
    Пример: `SELECT country FROM customers;` <br><br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/9ac2841d-da85-463a-bb8c-5ec1f907b97d)
  - Вывод строк c ипользование `DISTINCT` из таблицы `customers`  значений `21` <br>
    Пример: `SELECT DISTINCT country FROM customers;` <br><br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/2cdc594d-91c2-4ae4-9d16-8477083ba3fd)

## COUNT вывод количество результирующих строк
  - Пример: `SELECT COUNT(country) FROM customers;` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/bfc3d16e-0add-4f0b-b9a3-2bf03e82b36a)
  - Пример: `SELECT COUNT( DISTINCT country) FROM customers;` без дубликатов ипользуем `DISTINCT` <br><br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/203c2278-8ddc-467b-a312-93960a297276)

## WHERE фильтрация данных результирующих наборов 
  - Пример: `SELECT * FROM products WHERE unit_price = '18';` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/4e965768-4cd3-4d89-9e85-42f3e248fc2b)
    
## AND и OR логиеческие операторы для комбинирование условий
  - Пример: `SELECT * FROM orders WHERE ship_via = 2 AND freight < 5;` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/ccfa0dbc-21b6-4385-ae19-9f8a3693d9c9)
  - Пример: `SELECT * FROM orders WHERE ship_via = 2 OR freight < 5;` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/9bce0229-b7fb-4dfb-9dd2-ff08ac7bab8d)

## BETWEEN вывод результирующих наборов между 2 условиями
  - Пример: `SELECT * FROM orders WHERE freight BETWEEN 40 AND 60;` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/ce21fd62-fd9a-4f9f-9c55-ac5215513004)
    
## IN, NOT IN вывод результирующих наборов в которые есть или нет в условии 
  - Пример: `SELECT * FROM customers WHERE city IN ('London');` вывод набора где город `London` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/ff27331a-c8e0-4ad4-9fc3-007660dceae2)
  - Пример: `SELECT * FROM customers WHERE city NOT IN ('London');` вывод набор где нет города `London` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/16a19c46-4fd8-4d0b-88f6-6a652f300746)
    
## ORDER BY упорядочивание результатов
  - Пример: `SELECT DISTINCT country FROM customers ORDER BY country DESC;` вывод данных сортировка с конца или `ASC` с начала <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/394e2989-bc5b-41d0-be60-5009efba2c11)

## MIN, MAX, AVG для вычисления скалярных функций 
  - Пример: `SELECT MIN(unit_price) FROM products;` вывод минимального значения из атрибута `unit_price` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/73efd7f5-cc89-4727-a4fd-9e512ba6de38)
  - Пример: `SELECT MAX(unit_price) FROM products;` вывод максимального значения из атрибута `unit_price` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/1a29430e-9f54-45be-abef-de848d46b5c9)
  - Пример: `SELECT AVG(unit_price) FROM products;` вывод среднего значения из атрибута `unit_price` <br> <br>  ![image](https://github.com/caxar/SQL_INFO/assets/45434213/d2993e4b-0b17-4f65-b7a4-0d29e61b4204)

## LIKE паттерн совпадения 
  - Пример: `SELECT * FROM customers WHERE contact_title LIKE '_w%';` вывод данных где пропущена буква первая есть буква `w` и остальное без разницы `%`  <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/39bdc626-6791-46e0-bead-c65361ef782d)

## IS NULL, IS NOT NULL проверка результирующего набора данных на `NULL`
  - Пример: `SELECT ship_address, ship_city, ship_region FROM orders WHERE ship_region IS NULL;` вывод данных где значения `NULL` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/fb8bb955-f966-4f72-808d-a074d515f449)
  - Пример: `SELECT ship_address, ship_city, ship_region FROM orders WHERE ship_region IS NOT NULL;` вывод данных где значения не `NULL` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/9016307d-b644-44d8-8669-d0396cd2ab5e)

## GROUP BY граппировка результирующих наборов 
  - Пример: `SELECT ship_country, COUNT(*) FROM orders WHERE freight > 50 GROUP BY ship_country;` группировка данных по `ship_country` <br> <br>![image](https://github.com/caxar/SQL_INFO/assets/45434213/d3be20e0-ad2c-4269-bb31-237bd019411e)


## HAVING пост фильтрация
  - Пример: `SELECT category_id, SUM(unit_price * units_in_stock) 
FROM products 
WHERE discontinued <> 1 
GROUP BY category_id 
HAVING SUM(unit_price * units_in_stock) < 5000;` вывод данных с постфиксной фильтрацией где `SUM` < 5000 <br><br>![image](https://github.com/caxar/SQL_INFO/assets/45434213/84dc56a7-e005-4c65-8681-b58d24e0e13d)


## UNION, INTERSECT, EXCEPT - объединения, пересечения, иключения
  - Пример: `SELECT country FROM customers 
         UNION 
SELECT country FROM employees;` вывод стран откуда `customers` и `employees` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/8701d80e-2750-4670-8a21-9a112d1f3543)

  - Пример: `SELECT country FROM customers 
         INTERSECT 
SELECT country FROM employees;` вывод стран тоkько те страны из которых `customers` так и `employees` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/5155e19c-8fc3-4b6e-bcda-915850e87b5b)

  - Пример: `SELECT country FROM customers 
         EXCEPT 
SELECT country FROM employees;` вывод стран где живут `customers` но не живут `employees` <br> <br> ![image](https://github.com/caxar/SQL_INFO/assets/45434213/a5f99b18-a79b-497c-9732-1855bcc2707a)














 




