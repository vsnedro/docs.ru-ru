---
title: Оператор Function
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404632"
---
# <a name="function-statement-visual-basic"></a>Оператор Function (Visual Basic)

Объявляет имя, параметры и код, определяющие `Function` процедуру.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Компоненты

- `attributelist`

  Необязательный элемент. См. [список атрибутов](attribute-list.md).

- `accessmodifier`

  Необязательный элемент. Может принимать следующие значения:

  - [Открытый](../modifiers/public.md)

  - [От](../modifiers/protected.md)

  - [Объявление](../modifiers/friend.md)

  - [Частное](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Частный защищенный](../modifiers/private-protected.md)

  См. раздел [уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Необязательный элемент. Может принимать следующие значения:

  - [Перегрузки](../modifiers/overloads.md)

  - [Переопределения](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательный элемент. См. раздел [Shared](../modifiers/shared.md).

- `Shadows`

  Необязательный элемент. См. раздел [Shadows](../modifiers/shadows.md).

- `Async`

  Необязательный элемент. См. статью [Async](../modifiers/async.md).

- `Iterator`

  Необязательный элемент. См. [итератор](../modifiers/iterator.md).

- `name`

  Обязательный. Имя процедуры. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Необязательный элемент. Список параметров типа для универсальной процедуры. См. [список типов](type-list.md).

- `parameterlist`

  Необязательный элемент. Список имен локальных переменных, представляющих параметры этой процедуры. См. [список параметров](parameter-list.md).

- `returntype`

  Обязательный `Option Strict` , если имеет значение `On` . Тип данных значения, возвращаемого этой процедурой.

- `Implements`

  Необязательный элемент. Указывает, что эта процедура реализует одну или несколько `Function` процедур, каждая из которых определена в интерфейсе, реализованном классом или структурой этой процедуры. См. [инструкцию Implements](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Function`.

  `implementedprocedure [ , implementedprocedure ... ]`

  Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.

  `interface.definedname`

  |Часть|Описание|
  |---|---|
  |`interface`|Обязательный. Имя интерфейса, реализованного классом или структурой, содержащейся в этой процедуре.|
  |`definedname`|Обязательный. Имя, под которым процедура определена в `interface`.|

- `Handles`

  Необязательный элемент. Указывает, что эта процедура может управлять одним или несколькими конкретными событиями. См. раздел [Handles](handles-clause.md).

- `eventlist`

  Является обязательным, если предоставлен параметр `Handles`. Список событий, обрабатываемых этой процедурой.

  `eventspecifier [ , eventspecifier ... ]`

  Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.

  `eventvariable.event`

  |Часть|Описание|
  |---|---|
  |`eventvariable`|Обязательный. Объектная переменная, объявленная с типом данных класса или структуры, которая вызывает событие.|
  |`event`|Обязательный. Имя события, обрабатываемого этой процедурой.|

- `statements`

  Необязательный элемент. Блок инструкций для выполнения в рамках этой процедуры.

- `End Function`

  Завершает определение этой процедуры.

## <a name="remarks"></a>Комментарии

Весь исполняемый код должен находиться внутри процедуры. Каждая процедура, в свою очередь, объявляется в классе, структуре или модуле, который называется содержащим классом, структурой или модулем.

Чтобы вернуть значение в вызывающий код, используйте `Function` процедуру; в противном случае используйте `Sub` процедуру.

## <a name="defining-a-function"></a>Определение функции

Процедуру можно определить `Function` только на уровне модуля. Таким образом, контекст объявления для функции должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

`Function`процедуры по умолчанию имеют открытый доступ. Уровни доступа можно изменить с помощью модификаторов доступа.

`Function`Процедура может объявлять тип данных возвращаемого процедурой значения. Можно указать любой тип данных или имя перечисления, структуру, класс или интерфейс. Если параметр не указан `returntype` , процедура возвращает `Object` .

Если в этой процедуре используется `Implements` ключевое слово, содержащий класс или структуру также должны иметь `Implements` оператор, который сразу следует `Class` за `Structure` оператором или. `Implements`Инструкция должна включать каждый интерфейс, указанный в `implementslist` . Однако имя, по которому интерфейс определяет `Function` (в `definedname` ), не обязательно должно совпадать с именем этой процедуры (в `name` ).

> [!NOTE]
> Лямбда-выражения можно использовать для определения выражений функций встроенным. Дополнительные сведения см. в разделе [выражение функции](../operators/function-expression.md) и [лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Возврат из функции

Когда `Function` процедура возвращается в вызывающий код, выполнение переходит к инструкции, следующей за инструкцией, вызвавшей процедуру.

Чтобы вернуть значение из функции, можно либо присвоить значение имени функции, либо включить его в `Return` инструкцию.

`Return`Оператор одновременно назначает возвращаемое значение и завершает функцию, как показано в следующем примере.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

В следующем примере возвращаемое значение присваивается имени функции `myFunction` , а затем используется `Exit Function` оператор для возврата.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

`Exit Function`Операторы и `Return` вызывают немедленный выход из `Function` процедуры. Любое количество `Exit Function` инструкций и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Function` `Return` операторы и.

Если вы используете `Exit Function` без присвоения значения `name` , процедура возвращает значение по умолчанию для типа данных, указанного в параметре `returntype` . Если параметр `returntype` не указан, процедура возвращает `Nothing` значение, которое является значением по умолчанию для `Object` .

## <a name="calling-a-function"></a>Вызов функции

Процедура вызывается с `Function` использованием имени процедуры, за которым следует список аргументов в выражении в круглых скобках. Скобки можно опустить, только если вы не предоставляете никаких аргументов. Однако код является более удобочитаемым, если всегда включать круглые скобки.

Процедура вызывается `Function` так же, как и любая библиотечная функция, такая как `Sqrt` , `Cos` или `ChrW` .

Функцию можно также вызвать с помощью `Call` ключевого слова. В этом случае возвращаемое значение игнорируется. `Call`В большинстве случаев использование ключевого слова не рекомендуется. Дополнительные сведения см. в разделе [оператор Call](call-statement.md).

Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности. По этой причине не следует использовать `Function` процедуру в арифметическом выражении, если функция изменяет значение переменных в том же выражении.

## <a name="async-functions"></a>Асинхронные функции

Функция *Async* позволяет вызывать асинхронные функции без использования явных обратных вызовов или вручную разделять код между несколькими функциями или лямбда-выражениями.

Если вы помечаете функцию модификатором [Async](../modifiers/async.md) , то можете использовать оператор [await](../operators/await-operator.md) в функции. Когда управление достигает `Await` выражения в `Async` функции, управление возвращается вызывающему объекту, и ход выполнения функции приостанавливается до тех пор, пока не завершится ожидаемая задача. После завершения задачи выполнение может возобновиться в функции.

> [!NOTE]
> `Async`Процедура возвращается к вызывающему объекту, когда он встречает первый ожидающий объект, который еще не завершен, или на конец процедуры, в зависимости от того, что `Async` происходит раньше.

`Async`Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task> . Ниже приведен пример `Async` функции, имеющей тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> .

`Async`Функция не может объявлять никакие параметры [ByRef](../modifiers/byref.md) .

[Оператор](sub-statement.md) подвыражения также может быть помечен `Async` модификатором. Это в основном используется для обработчиков событий, где значение не может быть возвращено. `Async` `Sub` Процедуру нельзя ожидать, и вызывающая `Async` `Sub` процедура не может перехватывать исключения, создаваемые `Sub` процедурой.

Дополнительные сведения о `Async` функциях см. в разделе [Асинхронное программирование с использованием Async и await](../../programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../programming-guide/concepts/async/control-flow-in-async-programs.md)и [асинхронные типы возвращаемых](../../programming-guide/concepts/async/async-return-types.md)данных.

## <a name="iterator-functions"></a>Функции итератора

Функция *итератора* выполняет настраиваемую итерацию для коллекции, например списка или массива. Функция итератора использует оператор [yield](yield-statement.md) для возвращения каждого элемента по одному за раз. При достижении оператора [yield](yield-statement.md) текущее расположение в коде запоминается. При следующем вызове функции итератора выполнение возобновляется с этого места.

Итератор вызывается из клиентского кода с помощью метода [For Each... Следующий](for-each-next-statement.md) оператор.

Тип возвращаемого значения функции итератора может быть <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601> .

Дополнительные сведения см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Пример

В следующем примере оператор используется `Function` для объявления имени, параметров и кода, образующих тело `Function` процедуры. `ParamArray`Модификатор позволяет функции принимать переменное число аргументов.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Пример

В следующем примере вызывается функция, объявленная в предыдущем примере.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Пример

В следующем примере `DelayAsync` — это, `Async` `Function` имеющий тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> . `DelayAsync` имеет инструкцию `Return` , которая возвращает целое число. Поэтому объявление функции `DelayAsync` должно иметь тип возвращаемого значения `Task(Of Integer)` . Так как тип возвращаемого значения — `Task(Of Integer)` , вычисление `Await` выражения в `DoSomethingAsync` создает целое число. Это продемонстрировано в этой инструкции: `Dim result As Integer = Await delayTask` .

`startButton_Click`Процедура является примером `Async Sub` процедуры. Поскольку `DoSomethingAsync` является `Async` функцией, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()` . `startButton_Click` `Sub` Процедура должна быть определена с `Async` модификатором, так как содержит `Await` выражение.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>См. также раздел

- [Оператор Sub](sub-statement.md)
- [Процедуры функций](../../programming-guide/language-features/procedures/function-procedures.md)
- [Список параметров](parameter-list.md)
- [Оператор Dim](dim-statement.md)
- [Оператор Call](call-statement.md)
- [Окна](of-clause.md)
- [Массивы параметров](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Практическое руководство. Использование универсального класса](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Рекомендации по устранению неполадок](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Выражение функции](../operators/function-expression.md)
