IComparer - это интерфейс, который схож с интерфейсом [[IComparable]], однако, если IComparable говорит объекту сравнить себя с другим объектом, то IComparer наследуется к классу, который сам решает, как переданные объекты будут сравниваться.

Данные интерфейс очень хорошо помогает, когда в разных частях программы требуется несколько типов сортировок. То есть, если IComparable даёт сравнивать объекты только одним способом и этот способ единственный, то IComparer позволяет генерировать бесконечное множество способов сравнения объектов.

Интерфейс имеет следующую структуру:
```cs
interface IComparer
{
	int CompareTo(object x, object y);
}
```

При использовании IComparer мы определяем новый класс, который определяет то, как будут сравниваться объекты:
```cs
class ReverseIntComparer : IComparer
{
	public int CompareTo(object x, object y)
	{
		return -((int)x).CompareTo((int)y);
	}
}

class SomeClass
{
	public static void SomeMethod(int x, int y, IComparer comparer)
	{
		int compareResult = comparer.CompareTo(x, y);
		//some logic
	}
	public static void Main()
	{
		int x = 1;
		int y = 2;
		SomeMethod(x, y, new ReverseIntComparer());
	}
}
```
Вместо ReverseIntComparer можно написать любой другой класс, который будет реализовывать IComparer.

#CSharp 