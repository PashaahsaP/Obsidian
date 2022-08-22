Record ссылочный тип ключевая особенность в возможности предоставления immutable типа.Могут быть record class and record struct. Чтобы сделать тип неизменяемым(для полной записи) нужно set использовать Init. Дает возможность  для сравнения (equals) по значению а не по ссылке. Также есть инициализация с оператором with позволяет создать одну record но основе другой.
 ```C#
	 var tom = new Person ("Tom",37);
	 var sam = tom with {Name="Sam"};
```
 
Record удобны для создания dto объектов, более коротка форма записи, при помощи позиционных параметров.

```C#
 public record Person(string Name, int Age);
```
 [[Class]][[Struct]][[Immutable]]