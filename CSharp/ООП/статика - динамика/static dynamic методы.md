Если метод в классе является статическим, то мы можем в нем обращаться только к статическим полям, и он вызывается от самого класса.

Если метод является динамическим, то мы можем в нем обращаться как к статическим полям, так и динамическим, и он вызывается от конкретного экземпляра класса.

```cs
public class Point2D
{
	public float X;
	public float Y;
	public static float Z = 0;
	
	public void MoveX(float deltaX) // динамический метод
	{
		X += deltaX;
	}

	public static void MoveX(Point2D point, float deltaX) // статический метод
	{
		point.X += deltaX;
	}
	
	public static void ChangePlane(float newPlane) // статический метод
	{
		Z = newPlane;
	}
}

var point = new Point2D();
point.MoveX(0.1f);
Point2D.MoveX(point, 0.1f);
Point2D.ChangePlane(12f);
```

Как видно из примера из динамического метода можно сделать статический метод. Причём такую зависимость можно сделать всегда. Динамические методы являются синтаксическим сахаром, которые просто упрощают написание кода.

Из статического метода также можно сделать динамический, однако данную реализацию не рекомендуется использовать по той причине, что статический метод мог работать с статическими полями, и не всегда понятно, какой из объектов должен вызывать полученный динамический метод.

В памяти динамические и статические методы хранятся в единственном экземпляре.

#CSharp 
