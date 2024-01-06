IComparable - это интерфейс, который обязывает класс содержать внутри себя метод CompareTo:
```cs
int CompareTo(object value);
```
Данный метод сравнивает объекты и возвращает -1, если первый объект больше второго, 0 если они равны, 1 в противном случае.

Данный интерфейс полезен при сравнении элементов. Его наличие может сказать о том, можно ли сравнивать эти элементы или нельзя.

Пример использования интерфейса при сортировки массива:
```cs
public static void BubleSort(Array array)
{
	for(int i = array.Length - 1; i >= 0; i--)
	{
		for(int j = 0; j <= i; j++)
		{
			var element1 = (IComparable)array.GetValue(j);
			var element0 = array.GetValue(j - 1);
			if(element1.CompareTo(element0) < 0)
			{
				//some logic
			}
		}
	}
}
```
#CSharp 