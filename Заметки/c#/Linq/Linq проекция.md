```C#
var companies = new List<Company>

{

    new Company("Microsoft", new List<Person> {new Person("Tom"), new Person("Bob")}),

    new Company("Google", new List<Person> {new Person("Sam"), new Person("Mike")}),

};

var result = companies.SelectMany(c => c.Staff);
//{"Tom","Bob","Sam","Mike"}

var employees = companies.SelectMany(c => c.Staff,
(c, emp) => new { Name = emp.Name, Company = c.Name });
//{"Tom","Microsoft",
// "Bob","Microsoft",
// "Sam","Google",
// "Mike","Google"}   
 

record class Company(string Name, List<Person> Staff);

record class Person(string Name);
```
![[Операторы проекции.png]][[Linq]]