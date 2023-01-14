```C#
Range method
List<int> temp2 = new () { 2,3,4,5,6,7 };
var result = Enumerable.Range(4, 6);
// result {4,5,6,7,8,9}

Repeat method
var result = Enumerable.Repeat(new Person("Pavel",3),3);
//Pavel 3
//Pavel 3
//Pavel 3
```
![[Операторы генерации.png]][[Linq]]