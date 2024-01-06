Если класс является статическим, то:
1. Мы не можем создать объект этого класса.
2. Все поля и методы в этом классе тоже являются статическими

```cs
public static Math
{
	public static float PI = 3.14f;
	
	public static float CalculateCircleArea(float radius)
	{
		return PI*radius*radius;
	}
}

var radius = Math.PI + 1;
var area = Math.CalculateCircleArea(radius);
```

Если класс является динамическим, то он может содержать, как статические поля и методы, так и динамические, и мы можем создать экземпляр этого класса.

#CSharp 