delegate - это один из базовых(на ровне с классом и структурой) reference type тип данных, который содержит в себе ссылку на метод.

Пример:
```cs
public delegate void Do();
```
Делегат строится по следующей структуре: {модификатор доступа} delegate {возвращаемый тип данных} {имя}(переменные).
Делегаты можно объявлять в любой точке кода.

Теперь в отдельной части кода мы можем создать переменную типа этого делегата и присвоить в неё ссылку на метод, который будет соответствовать семантике делегата:
```cs
public void DoSomething(){}

//...

Do do = DoSomething();
do();//вызов метода делегата
```

Как хранится делегат в памяти?
В памяти делегат содержит помимо адреса метода ещё и Target - объекта, относительно которого вызывается метод в делегате. Таргет заполняется в случае, если переданный метод является динамическим. В ином случае таргет является null.
![[delegateMemoryMap1.png]]

Поскольку делегаты являются ссылкой над методами, то также, как и методы, делегаты можно параметризировать с помощью [[Generic]]
```cs
public delegate T1 DoSomething<T1, T2>(T2 a, T2 b);
```
Благодаря generic можно быстро создавать нужные делегаты, поэтому в DotNet обобщения делегатов были вынесен в [[Func]], [[Action]], [[Predicate]].

[[Анонимные методы]]
#CSharp 