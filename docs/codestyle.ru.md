## Отступы, переносы, скобки
* Для отступов используются пробелы
* Фигурные скобки при инициализации свойств объектов
	* Можно писать в одну строку, когда логики/кода немного
	* Вокруг фигурных скобок должны быть пробелы:
	
	`var employee = new Employee { City = new City { Name = name } };`

## Наименование
* Имена приватных полей пишутся в *_camelCase* с подчеркиванием. Наименование переменных производится в классическом *camelCase* (с маленькой буквы)
* Наименование методов и классов производится в *PascalCase*
* Наименование классов работы с Db и Dto производится в единственном числе, по названии таблицы, с которой они связаны.

    Например, таблица **Products**, классы **Product** и **ProductDto**
* При наименование классов и интерфейсов сервисов, репозиториев необходимо использовать наименование сущности в единственном числе
* При наименование контроллеров необходимо использовать наименование сущности во множественном числе
* Имена констант пишутся с большой буквы в *PascalCase*

## Директивы using
* Желательно сортировать и удалять неиспользуемые
* При сортировке `System.*` ставятся всегда в начале

## Комментарии, коммиты
* Комментарии и коммиты пишутся только на английском языке

  В коммите пишется сначала номер задачи, дальше через пробел кратко что в себе содержит комммит/что было сделано. Например:
  > Feature-120 Added EmployeesController and fixed namespace of models
* К каждому публичному методу должен быть комментарий `<summary>` с кратким описанием того, что делает метод
* Текст любого комментария должен начинаться с большой буквы

## Разное
* При большом количестве параметров у метода или конструктора лучше использовать следующий способ форматирования:
```csharp
public void SomeMethod(Param1 param1,
    Param2 param2,
    Param3 param3,
    Param4 param4)
{ }

либо

public void SomeMethod(
    Param1 param1,
    Param2 param2,
    Param3 param3,
    Param4 param4)
{ }
```
* При вызове метода, если смысл передаваемого параметра не ясен из его значения, например, `GetSomething(false)`, то желательно явно указывать имя параметра - `GetSomething(includeHidden: false)`
* Приватные поля, значение у которых устанавливается только в конструкторе, должны помечаться как `readonly`
* Неиспользуемый код следует удалять, а не комментировать
  * Если может понадобиться когда-нибудь в будущем вернуть, удалять отдельным коммитом
  * Если он должен по каким-то причинам остаться (например, для изменения стратегии работы метода), следует развернуто пояснить в комментарии перед данным кодом. Сам код при этом закомментировать
* В БД все даты следует хранить только в UTC, на front отдаётся и принимается тоже в UTC
