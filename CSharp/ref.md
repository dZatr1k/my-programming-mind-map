ref - это ключевое слово, использующееся для получения ссылки на переменную.

Как это работает с точки зрения value type:
```cs
public static void Test(int x)
{
	x = 10;
}

public static void Test(ref int x)
{
	x = 10;
}

public static void Main()
{
	int x = 0;
	Test(x);
	Console.WriteLine(x); //0
	
	Test(ref x);
	Console.WriteLine(x); //10
}
```
Таким образом, передавая в метод ref переменную, мы не копируем значение этой переменной, а передаём ссылку на эту переменную, а потом работаем с ней так, будто контекст не менялся.


Как это работает с точки зрения reference type:
```cs
class Point1D
{
	public double X;
}

...

public static void Test(Point1D p)
{
	p = new Point1D();
}

public static void Test(ref Point1D p)
{
	p = new Point1D();
}

public static void Main()
{
	var p = new Point1D();
	p.X = 10;
	Test(p);
	Console.WriteLine(p.X);//10
	
	Test(ref p);
	Console.WriteLine(p.X);//0
}
```
В случае с reference type мы передаём ссылку на ссылку, поэтому переопределяя объект мы меняем ссылку внутри ссылки.

#Доработать #CSharp 