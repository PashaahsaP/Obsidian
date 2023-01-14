```C#
Person[] people =
{
    new Person("Tom", "Microsoft"), new Person("Sam", "Google"),
    new Person("Bob", "JetBrains"), new Person("Mike", "Microsoft"),
    new Person("Kate", "JetBrains"), new Person("Alice", "Microsoft"),
};

var result = from human in people
             group human by human.Company;

foreach (var item in result)
{
    Console.WriteLine(item.Key);
    foreach (var item2 in item)
    {
        Console.WriteLine("  " +item2.Name);
    }
}
public record Person(string Name,string Company);
/*
Microsoft
  Tom
  Mike
  Alice
Google
  Sam
JetBrains
  Bob
  Kate
*/
```
![[Операторы группирования.png]][[Linq]]