Ещё одной классической задачей для стека является задача "Вычислений", которая заключается в том, что мы должны разобрать строку из арифметических операций, а затем получить результат.

Эта задача решается за O(n). Реализация на C#:
```cs
public int Solve(string str)
{
	var stack = new Stack<int>();
	var dict = new Dictionary<char, Func<int, int, int>()>();
	dict.Add('*', (a, b) => a*b);
	dict.Add('+', (a, b) => a+b);
	dict.Add('-', (a, b) => a-b);
	dict.Add('/', (a, b) => a/b;
	foreach(var item in str)
	{
		if(item <= '9' && '0' <= item)
		{
			stack.Push(item - '0');
			continue;	
		}
		else if(dict.Keys.Constains(item))
		{
			var arg1 = stack.Pop();
			var arg2 = stack.Pop();
			stack.Push(dict[item](arg1, arg2));
		}
		else
			throw new Exception("Unexcepted symbol: " + item);
	}
	return stack.Pop();
}
```

#CompSci 