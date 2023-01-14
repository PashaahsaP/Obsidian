Чтобы получить связанные данные с сущностью исп-ся:
```C#
using (var context = new BloggingContext()) 
{
var blogs = context.Blogs .Include(blog => blog.Posts); 
}
```
Можно включить связанные данные из нескольких отношений
```c#
using (var context = new BloggingContext()) 
{
var blogs = context.Blogs .Include(blog => blog.Posts)
						  .Include(blog => blog.Owner); 
}
```
Можно получить связанные данные из полученных связных данных можно исп-ть `ThenInclude`
```C#
using (var context = new BloggingContext()) 
{ 
var blogs = context.Blogs .Include(blog => blog.Posts) 
                          .ThenInclude(post => post.Author) .ToList(); }
```
Можно использовать сколько угодно вложенностей
Есть возможность фильтрации связанных данных.
Поддерживаются следующие операции: `Where`, `OrderBy`, `OrderByDescending`, `ThenBy`, `ThenByDescending`, `Skip`, и `Take`.
```C#
using (var context = new BloggingContext()) 
{
var filteredBlogs = context.Blogs.Include( blog => 
            blog.Posts 
        .Where(post => post.BlogId == 1) 
        .OrderByDescending(post => post.Title)
        .Take(5)) .ToList(); 
}
```
