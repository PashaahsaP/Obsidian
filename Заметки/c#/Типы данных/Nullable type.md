Это тип допускающий null, может представлять все допустимые значения в основе типа плюс значение Null. К примеру nullable bool тип может иметь три значения true,false и null.
Может обозначаться в кода двумя способами:
```C#
 bool? a; 
 Nullable<bool>a;
```
Есть еще два оператора для облегченной проверки на null и присвоения дефотного значени называеться операции объединения с null:
```C#
	string text = null;
	string name = text ?? "Tom";
```
Оператор ?? возращает левый операнд если он не равен null  иначе правый. Есть еще один оператор для более короткой и иной записи:
```C#
	string text = null;
	text ??= "Tom";
```

[[Struct]][[Null]]