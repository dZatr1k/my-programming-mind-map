IEnumerable и IEnumerable\<T> - это интерфейсы, которые говорят о том, что класс является некоторой коллекцией, которую можно перебрать.

IEnumerable был добавлен в .NET 1.0 и 1.1, где про обобщение типа не было и речи, поэтому этот интерфейс выглядит так:
```cs
public interface IEnumerable
{
    IEnumerator GetEnumerator();
}
```

#Доработать #CSharp 