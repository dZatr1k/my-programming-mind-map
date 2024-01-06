Queue - это коллекция, элементы которой работают по принципу FIFO (Fitst In First Out). То есть первым вошел, первым вышел.
Порядок добавления и удаления элементов в стеке такой: положили 1, 2, 3, 4 а затем убрали 1, 2, 3, 4.

То есть очередь в программировании похожа на очередь в магазине, где если ты встал в очередь на каком-то месте, то чтобы выйти из неё тебе нужно добраться до её начала.

Реализация очереди на базе листа:
```cs
class Queue
{
	List<int> list = new List<int>();
	
	public void Enqueue(int value)//метод, который добавляет элемент в очередь
	{
		list.Add(value);
	}

	public int Dequeue()//метод, который удаляет элемент из стека и возвращает его значение
	{
		if(list.Count == 0)
			throw new InvalidOperationException();
		var result = list[0];
		list.Remove(0);
		return result;
	}
}
```

Реализация очереди на базе листов не очень эффективна, поскольку при удалении первого элемента мы должны сдвигать каждый элемент массива, поэтому данный метод работает O(n).

Решением этой проблемы является реализация очереди на базе [[Связные списки|связанного списка]]:
```cs
class Item
{
	public int Value;//значение
	public Item Next;//ссылка на следующий элемент
}
class Queue
{
	private Item _head;
	private Item _tail;
	
	public void Enqueue(int value)//метод, который добавляет элемент в очередь
	{
		var item = new Item {Value = value};
		if(_head == null)
		{
			_head = _tail = item;
		}
		else
		{
			_tail.Next = item;
			_tail = item;
		}
	}

	public int Dequeue()//метод, который удаляет элемент из стека и возвращает его значение
	{
		if(_head == null)
			throw new InvalidOperationException();
		var result = _head.Value;
		_head = _head.Next;
		if(_head == null)
			_tail = null;
		return result;
	}
}
```
В данной реализации исключение элемента происходит за O(1).

Как можно написать очередь, которая будет работать с любым типом данных?
Можно использовать object:
```cs
class Item
{
	public object Value;
	public Item Next;
}
class Queue
{
	private Item _head;
	private Item _tail;
	
	public void Enqueue(object value)
	{
		var item = new Item {Value = value};
		if(_head == null)
		{
			_head = _tail = item;
		}
		else
		{
			_tail.Next = item;
			_tail = item;
		}
	}
	
	public object Dequeue()
	{
		if(_head == null)
			throw new InvalidOperationException();
		var result = _head.Value;
		_head = _head.Next;
		if(_head == null)
			_tail = null;
		return result;
	}
}
```
Но данное решение не является хорошим, потому что появляется проблема, когда мы захотим как-то работать с переменными складывать их или производить другие операции, мы будем вынуждены применять Downcast. Но эта операция не всегда безопасна.

Правильным решением является решение, основанное на дженерик-классах:
```cs
class Item<T>
{
	public T Value;
	public Item<T> Next;
}
class Queue<T>
{
	private Item<T> _head;
	private Item<T> _tail;
	
	public void Enqueue(T value)
	{
		var item = new Item {Value = value};
		if(_head == null)
		{
			_head = _tail = item;
		}
		else
		{
			_tail.Next = item;
			_tail = item;
		}
	}
	
	public T Dequeue()
	{
		if(_head == null)
			throw new InvalidOperationException();
		var result = _head.Value;
		_head = _head.Next;
		if(_head == null)
			_tail = null;
		return result;
	}
}
```
[[Queue для скользящего среднего]]
#CompSci #Доработать 