```C#
List<int> temp2 = new() { 1,2,3 };
List<int> temp1 = new() { 2,3,4,5 };
var result = temp1.Union(temp2);///{1,2,3,4,5}

List<int> temp2 = new() { 1,2,3 };
List<int> temp1 = new() { 2,3,4,5 };
var result = temp1.Intersect(temp2);//{2,3}

List<int> temp2 = new() { 1,2,3 };
List<int> temp1 = new() { 2,3,4,5 };
var result = temp1.Except(temp2);//{4,5}
```
intersect
except
![[Операторы работы с множествами.png]][[Linq]]