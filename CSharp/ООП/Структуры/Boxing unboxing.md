Boxing unboxing - это аналог Upcast и Downcast в наследовании структур. В случае структур это явление происходит при переходе от структуры к object или же к переходу к интерфейсу, которая реализует данная структура.

И тут появляется противоречие, ведь структура лежит в стеке, а object или Interface должен иметь ссылку на конкретный объект. Поэтому при Upcast от структуры к object происходит boxing, то есть в куче выделяется отдельный контекст для копии структуры, а затем на этот контекст начинает указывать переменная типа object.

Затем при Downcast будет происходить unboxing, то есть структура, находящаяся в куче будет скопирована в переменную. Причём именно скопирована. Новая структура никак не будет связана со старой структурой.

#CSharp 