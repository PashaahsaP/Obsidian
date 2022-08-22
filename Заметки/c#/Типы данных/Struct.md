Неявно наследуеться от system.ValueType, это означает что не требуеться выделять память в кучи для структуры. Как и с примитивами при присвоении значения будет копироваться структура. 
У конструктора не может отсутствовать параметры или полям должны быть присвоенны значения по умолчанию.
Структура не может быть бызовым элементом и структура может реализовать только класс.
Также могут быть record и readonly struct(неизменяемые и только для чтения)
Можно использовать выражение с with для копирования новой переменной структуры.

Нужно использовать когда нужно оптимизировать работу приложения так как значимый тип.

При копировании одной структуры в другой с ссылочными полями происходит поверхностно копирование ссылок т.е
```C#
var p1 = new Point("FirstPoint", 1, 4);
var p2 = p1;
p2.info._name ="SecondPoint";//If want rename need 
create new object
p1.Display();//SecondPoint
p2.Display();//SecondPoint
Console.ReadLine();

struct Point 
{
     int _x=2, _y=3;
    public Info info;
    public Point(string pointName,int x,int y)
    {
        info = new Info(pointName);
        _x = x;
        _y = y; 
    }
    public void Display()
    {
        Console.WriteLine($"x:{_x} y:{_y} PointName:
         {info._name}");
    }

}
public class Info
{
   public string _name;
    public Info(string name)
    {
        _name = name;
    }
}
```
[[ValueType]]