Назначение:
Шаблонный метод определяет основу алгоритма и позволяет подклассам переопределять некоторые шаги алгоритма, не изменяя структуры в целом.

Участники:
- AbstractClass - определяет невертуальный метод TemplateMethod, который внутри себя вызывает примитивные операции PremetiveOperation1, PremetiveOperation2 и тд.
- ConcreteClass - реализует примитивные операции AbstractClass.

UML-диаграмма:
![[templateMethodUML.png]]

Способы реализации:
- С помощью невиртуального метода и виртуальных операций (классическая реализация)
- С помощью функционального программирования, где в каждой реализации TemplateMethod меняет своё поведение с помощью определения делегатов:
```cs
// Интерфейс сервиса сохранения записей 
interface ILogSaver 
{ 
	void UploadLogEntries(IEnumerable logEntries); 
	void UploadExceptions(IEnumerable exceptions); 
	} 
// Прокси-класс инкапсулирует особенности работы 
// с WCF-инфраструктурой 
class LogSaverProxy : ILogSaver 
{ 
	class LogSaverClient : ClientBase 
	{ 
		public ILogSaver LogSaver 
		{ 
			get 
			{ 
				return Channel; 
			} 
		} 
	} 
	public void UploadLogEntries(IEnumerable logEntries) 
	{
		UseProxyClient(c => c.UploadLogEntries(logEntries)); 
	}
	
	public void UploadExceptions(IEnumerable exceptions)
	{ 
		UseProxyClient(c => c.UploadExceptions(exceptions)); 
	} 
	
	private void UseProxyClient(Action accessor) 
	{ 
		var client = new LogSaverClient(); 
		try 
		{ 
			accessor(client.LogSaver); 
			client.Close(); 
		} 
		catch (CommunicationException e) 
		{ 
			client.Abort(); 
			throw new OperationFailedException(e);
		}
	}
}
```
- С помощью методов расширения.

Зачем применять:
- Шаблонный метод можно использовать тогда, когда появляется возможность переиспользовать код с помощью наследования. В этот момент разработчику нужно задуматься о том, в каком отношении будут находиться родительский и дочерние классы.
#DesNArch 