---
description: 'Дополнительные сведения о: подоператоре (Visual Basic)'
title: Оператор Sub
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: 9be40c8284c677a151e4b1665f0b49e5f852bf00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740994"
---
# <a name="sub-statement-visual-basic"></a>Оператор Sub (Visual Basic)

Объявляет имя, параметры и код, определяющие `Sub` процедуру.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Компоненты

- `attributelist`

  Необязательный элемент. См. [список атрибутов](attribute-list.md).

- `Partial`

  Необязательный элемент. Указывает определение разделяемого метода. См. раздел [разделяемые методы](../../programming-guide/language-features/procedures/partial-methods.md).

- `accessmodifier`

  Необязательный элемент. Может принимать следующие значения:

  - [Общедоступная](../modifiers/public.md)

  - [Защищенный](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Частная](../modifiers/private.md)

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

- `name`

  Обязательный элемент. Имя процедуры. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md). Чтобы создать процедуру конструктора для класса, задайте в качестве имени `Sub` процедуры `New` ключевое слово. Дополнительные сведения см. в разделе [время существования объекта: как создаются и уничтожаются объекты](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Необязательный элемент. Список параметров типа для универсальной процедуры. См. [список типов](type-list.md).

- `parameterlist`

  Необязательный элемент. Список имен локальных переменных, представляющих параметры этой процедуры. См. [список параметров](parameter-list.md).

- `Implements`

  Необязательный элемент. Указывает, что эта процедура реализует одну или несколько `Sub` процедур, каждая из которых определена в интерфейсе, реализованном классом или структурой этой процедуры. См. [инструкцию Implements](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Sub`.

  `implementedprocedure [ , implementedprocedure ... ]`

  Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.

  `interface.definedname`

  |Отделение|Описание|
  |---|---|
  |`interface`|Обязательный элемент. Имя интерфейса, реализованного классом или структурой, содержащейся в этой процедуре.|
  |`definedname`|Обязательный элемент. Имя, под которым процедура определена в `interface`.|

- `Handles`

  Необязательный элемент. Указывает, что эта процедура может управлять одним или несколькими конкретными событиями. См. раздел [Handles](handles-clause.md).

- `eventlist`

  Является обязательным, если предоставлен параметр `Handles`. Список событий, обрабатываемых этой процедурой.

  `eventspecifier [ , eventspecifier ... ]`

  Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.

  `eventvariable.event`

  |Отделение|Описание|
  |---|---|
  |`eventvariable`|Обязательный элемент. Объектная переменная, объявленная с типом данных класса или структуры, которая вызывает событие.|
  |`event`|Обязательный элемент. Имя события, обрабатываемого этой процедурой.|

- `statements`

  Необязательный элемент. Блок инструкций для выполнения в рамках этой процедуры.

- `End Sub`

  Завершает определение этой процедуры.

## <a name="remarks"></a>Remarks

Весь исполняемый код должен находиться внутри процедуры. Используйте `Sub` процедуру, если не нужно возвращать значение в вызывающий код. Используйте `Function` процедуру, если требуется вернуть значение.

## <a name="defining-a-sub-procedure"></a>Определение подпроцедуры

Процедуру можно определить `Sub` только на уровне модуля. Контекст объявления для процедуры, следовательно, должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

`Sub` процедуры по умолчанию имеют открытый доступ. Уровни доступа можно изменить с помощью модификаторов доступа.

Если в процедуре используется `Implements` ключевое слово, содержащий класс или структуру должны иметь `Implements` оператор, который сразу следует за `Class` `Structure` оператором или. `Implements`Инструкция должна включать каждый интерфейс, указанный в `implementslist` . Однако имя, по которому интерфейс определяет `Sub` (в `definedname` ), не обязательно должен совпадать с именем этой процедуры (в `name` ).

## <a name="returning-from-a-sub-procedure"></a>Возврат из подпроцедуры

Когда `Sub` процедура возвращается в вызывающий код, выполнение переходит к инструкции после оператора, вызвавшего ее.

В следующем примере показан возврат из `Sub` процедуры.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

`Exit Sub`Операторы и `Return` вызывают немедленный выход из `Sub` процедуры. Любое количество `Exit Sub` инструкций и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Sub` `Return` операторы и.

## <a name="calling-a-sub-procedure"></a>Вызов процедуры подпрограммы

Процедура вызывается с `Sub` помощью имени процедуры в инструкции и затем после этого имени вместе со списком аргументов в круглых скобках. Скобки можно опустить, только если не указаны аргументы. Однако код является более удобочитаемым, если всегда включать круглые скобки.

`Sub`Процедура и `Function` процедура могут иметь параметры и выполнять ряд инструкций. Однако `Function` процедура возвращает значение, а `Sub` процедура — нет. Поэтому нельзя использовать `Sub` процедуру в выражении.

`Call`Ключевое слово можно использовать при вызове `Sub` процедуры, но это ключевое слово не рекомендуется для большинства случаев использования. Дополнительные сведения см. в разделе [оператор Call](call-statement.md).

Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности. По этой причине, если список аргументов содержит выражения, вызывающие другие процедуры, не следует рассчитывать на то, что эти выражения будут вызываться в определенном порядке.

## <a name="async-sub-procedures"></a>Процедуры Async

С помощью функции Async можно вызывать асинхронные функции без использования явных обратных вызовов или вручную разделить код по нескольким функциям или лямбда-выражениям.

Если вы пометите процедуру с модификатором [Async](../modifiers/async.md) , то можете использовать оператор [await](../operators/await-operator.md) в процедуре. Когда управление достигает `Await` выражения в `Async` процедуре, управление возвращается вызывающему объекту, и ход выполнения процедуры приостанавливается до тех пор, пока не завершится ожидаемая задача. После завершения задачи выполнение может быть возобновлено в процедуре.

> [!NOTE]
> `Async`Процедура возвращается к вызывающему объекту, когда происходит либо первый ожидающий объект, который еще не завершен, либо `Async` достигнут конец процедуры, в зависимости от того, что произойдет раньше.

Можно также пометить [оператор Function](function-statement.md) с помощью `Async` модификатора. `Async`Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task> . В примере далее в этом разделе показана `Async` функция, имеющая тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> .

`Async``Sub`процедуры в основном используются для обработчиков событий, где значение не может быть возвращено. `Async` `Sub` Процедуру нельзя ожидать, и вызывающая `Async` `Sub` процедура не может перехватывать исключения, которые `Sub` создает процедура.

`Async`Процедура не может объявлять параметры [ByRef](../modifiers/byref.md) .

Дополнительные сведения о `Async` процедурах см. в разделе [Асинхронное программирование с использованием Async и await](../../programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../programming-guide/concepts/async/control-flow-in-async-programs.md)и [асинхронные типы возвращаемых](../../programming-guide/concepts/async/async-return-types.md)данных.

## <a name="example"></a>Пример

В следующем примере оператор используется `Sub` для определения имени, параметров и кода, образующих тело `Sub` процедуры.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Пример

В следующем примере `DelayAsync` — это, `Async` `Function` имеющий тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> . `DelayAsync` имеет инструкцию `Return` , которая возвращает целое число. Поэтому объявление функции `DelayAsync` должно иметь тип возвращаемого значения `Task(Of Integer)` . Так как тип возвращаемого значения — `Task(Of Integer)` , вычисление `Await` выражения в `DoSomethingAsync` создает целое число, как показано в следующей инструкции: `Dim result As Integer = Await delayTask` .

`startButton_Click`Процедура является примером `Async Sub` процедуры. Поскольку `DoSomethingAsync` является `Async` функцией, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()` . `startButton_Click` `Sub` Процедура должна быть определена с `Async` модификатором, так как содержит `Await` выражение.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>См. также

- [Оператор Implements](implements-statement.md)
- [Оператор Function](function-statement.md)
- [Список параметров](parameter-list.md)
- [Оператор Dim](dim-statement.md)
- [Оператор Call](call-statement.md)
- [Окна](of-clause.md)
- [Массивы параметров](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Практическое руководство. Использование универсального класса](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Рекомендации по устранению неполадок](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Разделяемые методы](../../programming-guide/language-features/procedures/partial-methods.md)
