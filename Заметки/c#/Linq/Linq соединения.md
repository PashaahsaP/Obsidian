join
```C#
Person[] people =
{
    new Person("Tom", "Microsoft"), new Person("Sam", "Google"),
    new Person("Bob", "JetBrains"), new Person("Mike", "Microsoft"),
};
Company[] companies =
{
    new Company("Microsoft", "C#"),
    new Company("Google", "Go"),
    new Company("Oracle", "Java")
};
var employees = people.Join(companies,  p => p.Company, c => c.Title,  (p, c) => new { Name = p.Name, Company = c.Title, Language = c.Language }); // результат

//Tom - Microsoft (C#)
//Sam - Google (Go)
//Mike - Microsoft (C#)

var employees = from p in people
		        join c in companies on p.Company equals c.Title
	            select new { Name = p.Name, Company = c.Title, Language = c.Language };//нужно выбрать общее свойство у двух коллекций по которым будет объединение

record class Person(string Name, string Company);
record class Company(string Title, string Language);
```
GroupJoin группирует коллекции по свойству
zip
```C#
var courses = new List<Course> { new Course("C#"), new Course("Java") };
var students = new List<Student> { new Student("Tom"), new Student("Bob") };

var enrollments = courses.Zip(students);
foreach (var enrollment in enrollments)

    Console.WriteLine($"{enrollment.First} - {enrollment.Second}");//сопостовляет первый элемент первой колл. с первым элементов второй коллекции и т.д

record class Course(string Title);  
record class Student(string Name);  
```
![[Операторы  соединения.png]][[Linq]]