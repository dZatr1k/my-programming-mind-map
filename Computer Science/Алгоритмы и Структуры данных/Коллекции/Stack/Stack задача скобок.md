Стандартной задачей, которая приводится начинающим программистам во время изучения стека, является задача "скобок":
	Нужно определить является ли строка из последовательности скобок "Правильной последовательностью". Формально на словах сложно будет объяснить, что это значит, поэтому дам примеры правильных и неправильных строк:
		"[][][][]" - правильная строка
		"({)}" - неправильная строка

С помощью стека данная задача решается за O(n). Вот как выглядит решение на C#:
```cs
public bool isCorrect(string str)
{
	var stack = new Stack<char>();
	var dict = new Dictionary<char, char>();
	dict.Add('{', '}');
	dict.Add('[', ']');
	dict.Add('<', '>');
	dict.Add('(', ')');
	foreach(var item in str)
	{
		if(dict.Keys.Constains(item))
		{
			stack.Push(item);
		}
		else if(dict.Values.Constains(item))
		{
			if(stack.Count == 0)
				return false;
			var openBracket = stack.Pop();
			if(dict[openBracket] != symbol)
					return false;
		}
		else
			return true;
	}
	return true;
}
```

#CompSci 