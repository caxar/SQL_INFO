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



 




