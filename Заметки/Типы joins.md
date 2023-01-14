![[joins.png]]
- Inner join - возращает все записи из левой таблицы имеющие соответствующий записи в правой. ```sql
```SQL
SELECT product.name,product_type.type 
FROM product JOIN product_types 
ON products.typeID = product_type.id
```
- left outer join(левостронне внешнее объединение) вернет все записи из левой таблицы, независимо от того имеються ли соотве-е записи в правой 
```SQL
SELECT product.name,product_type.type 
FROM product LEFT OUTER JOIN product_types 
ON products.typeID = product_type.id
```
- right outer join(левостронне внешнее объединение) вернет все записи из правой таблицы, независимо от того имеються ли соотве-е записи в левой 
```SQL
SELECT product.name,product_type.type 
FROM product LEFT OUTER JOIN product_types 
ON products.typeID = product_type.id
```
-  full outer join(полное внешнее объединение) вернет все записи из левой таблицы и правой таблицы, независимо от того имеються ли соотве-е записи в таблицах. Сначала выводяться данные для которых есть соответствия потом остальное. 
```SQL
SELECT product.name,product_type.type 
FROM product FULL OUTER JOIN product_types 
ON products.typeID = product_type.id
```
- left excluding join(левостронне исключающее объединение) вернет записи только левой таблицы, не имеющие совпадения по ключу с правой
```SQL
SELECT * FROM Table_A A LEFT JOIN Table_B B ON A.Key = B.Key WHERE B.Key IS NULL
```
- right excluding join(правосторонне исключающее объединение) вернет записи только левой таблицы, не имеющие совпадения по ключу с правой
```SQL
SELECT * FROM Table_A A RIGHT JOIN Table_B B ON A.Key = B.Key WHERE A.Key IS NULL
```
 
 - Cross join(перекрестное  объединение) вернет объединения всех строк из одной таблицы с каждой строкой из другой таблицы
```SQL
SELECT product.name,product_type.type 
FROM product CROSS JOIN product_types 
```