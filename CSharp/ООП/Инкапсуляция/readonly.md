readonly - это модификатор доступа к полю, который сильно ограничивает изменение это поля в программе.

readonly поля можно изменить только внутри конструктора класса и нигде больше: не при обращении к объекту вне класса, не при обращении с помощью методов внутри класса. Мы можем получить только значение этого поля, но не изменить. То есть readonly поля имеют больше ограничений, чем private set поля. 

Пример:
```cs
class Counter
{
	public int Count {get; private set;}
	public readonly int MaxCount;
	
	public Counter(int maxCount)
	{
		Count = 0;
		MaxCount = maxCount;
	}
	
	public void IncreaseCount()
	{
		Count++;
		MaxCount++; //это сделать нельзя
	}
}

var counter = new Counter(10);
counter.MaxCount = 15; //это сделать нельзя
```

Чем отличаются readonly поля и const поля?
1. const поля являются статическими всегда, но readonly поля являются динамическими, если мы явно не указали, что они статические.
2. Значение const поля устанавливается во время компиляции, а значение readonly поля во время вызова конструктора класса.

#CSharp 