Is оператор используеться для проверки выражения на совместимость с данным типом, проверки на null и можно использовать для сопоставления элементов списка или массива
```C#
if(emp is Employee) 
	(Employee)emp;
```
С версии с# 7 можно упростить данную конструкцию, убрав явное приведение:
```C#
if(emp is Employee newEmp)
	Console.WriteLine(newEmp);
```
Также можно использовать отбрасывание
```C#
 if(emp is Employee _)
```

As  оператор явно преобразует выражение в указанный тип и если преобразование невозможно то возращает null не вызывает исключений.
```C#
Hexagon h = item as Hexagon
if(h!=null)
...
```
[[null]]