Чтобы использовать неявную типизацию можно использовать ключевое слово var. Но нельзя объявить var в параметрах метода или конструктора и обозначить возращаемый тип или в качестве поля класса. Также должно присваивать изначальное значение при объявлении переменной.
Неявно типизированная переменная в результате дает явно типизированные данные т.е при повторное присваивании значения это переменной не соответствующая типу при первичном присваивании то произойдет ошибка на этапе компиляции.
 ```C#
var t = 34; t = "string";// будет ошибка 
```
Одно из основных применений это как переменная принимающая результат linq запроса.
Также может использоваться в анонимном типе:
```C#
var anon = new {Age = 34, Name = "Pavel"};
```
[[Типизация]][[Linq]]