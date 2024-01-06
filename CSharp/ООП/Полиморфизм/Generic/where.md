where - это ключевое слово, которое позволяет ограничивать тип, который можно положить в качестве дженерика. Это ограничение может происходить по следующим параметрам:
* <span style="color: purple">where T : SomeClass</span> - ограничение, которое говорит о том, что в качестве T мы можем передать только SomeClass или его детей.
* <span style="color: purple">where T : ISomeInterface</span> - ограничение на тип, который реализует интерфейс ISomeInterface.
* <span style="color: purple">where T : new()</span> - ограничение на тип, у которого есть конструктор без параметров.
* <span style="color: purple">where T : Enum</span> - ограничение на только Enum.
* <span style="color: purple">where T : struct</span> - ограничение на только структуру.
* <span style="color: purple">where T : class</span> - ограничение на только класс.
* <span style="color: purple">where T : U</span> - ограничение, где два параметра дженерика, которое говорит, что T - это родитель U.
* <span style="color: purple">where T : struct?</span> - ограничение на nullable структуру.


#CSharp 