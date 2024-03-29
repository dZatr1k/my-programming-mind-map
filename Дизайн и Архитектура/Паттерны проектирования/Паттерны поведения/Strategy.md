Назначение:
Определяет семейство алгоритмов, инкапсулирует каждый из них и делает из взаимозаменяемыми. Стратегия позволяет изменять алгоритмы независимо от клиентов, которые ими пользуются.

Участники:
Strategy - определяет интерфейс алгоритма.
Context - является клиентом стратегии.
ConreteStrategyA, ConreteStrategyB - конкретные реализации стратегии.

UML-диаграмма:
![[strategyUML.png]]

Способы реализации в .NET:
- С помощью interface (классический вариант реализации)
- С помощью функционального программирования. В этом случае Context принимает делегат для своей работы.

Примечания:
- Паттерн стратегии довольно абстрактный, поэтому
	- Он не определяет того, как в метод стратегии будут передаваться аргументы, необходимые для работы этого метода.
	- Он не определяет, как контекст будет инициализировать конкретную реализацию стратегии.

Зачем применять:
- для инкапсуляции поведения или алгоритма
- для замены поведения программы во время выполнения

Любой спроектированный класс инкапсулирует в себе некоторое поведение или алгоритм, но он не обязательно должен быть или является стратегией. Стратегия нужна не для того, чтобы закрыть алгоритм от вида, а чтобы иметь возможность заменить этот алгоритм во время исполнения. Стратегия обеспечивает точку расширения системы в определённой плоскости.

#DesNArch 