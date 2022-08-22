Существует два типа кортеже ссылочный и значимый.
В основном нужны для более удобного возращения группы значений из метода вместо использования модификатора Out, также позволяет группировать слабосвязные типы данных.

Добавляеться возможность применять отбрасывание по возращаемому типу из метода
```C#
(int,int) Add(params int[] values)
{
    int result = 0, count = 0;
    foreach (var item in values)
    {
        result += item;
        count++;
    }
    return (result, count);
}

var (resutl, _) = Add(3, 4, 5, 6, 7);
Console.WriteLine(resutl);
```
Также добавилась возможность обменна переменными что может использоваться в сортировках
```C#
int i =3,j=4
(i,j)=(j,i)//i=4, j=3
```

https://stackoverflow.com/questions/41084411/whats-the-difference-between-system-valuetuple-and-system-tuple - Различия между system.tuple and system.valueTuple[[DataStructure]]