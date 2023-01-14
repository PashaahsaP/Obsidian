```C#
List<int> temp2 = new () { 2,3,4,5,6,7 };

var result = temp2.Aggregate((x,y) => x + y);//27
```
![[Операторы агрегации.png]]
[[Linq]]