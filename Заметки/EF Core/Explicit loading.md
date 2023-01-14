Можно загрузить связанные данные с помощью явной загрузки, для коллекции метод `Collection()`, для одиночной сущности `Property()`
```C#
using (var context = new BloggingContext()) 
{ 
var blog = context.Blogs .Single(b => b.BlogId == 1); context.Entry(blog) .Collection(b => b.Posts) .Load(); 
context.Entry(blog) .Property(b => b.Owner) .Load();
context.Entry(blog) .Reference(b => b.HXOwner) .Load();
}
```