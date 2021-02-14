---
description: 'Дополнительные сведения: инструкции в Visual Basic'
title: Операторы
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: 9da27c77c858075e413580047b7ed688b328c87f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436894"
---
# <a name="statements-in-visual-basic"></a>Операторы в Visual Basic

Инструкция в Visual Basic является полной инструкцией. Он может содержать ключевые слова, операторы, переменные, константы и выражения. Каждая инструкция принадлежит к одной из следующих категорий:

- **Операторы объявления**, которые наименают переменную, константу или процедуру, а также могут указывать тип данных.

- **Исполняемые операторы**, инициирующие действия. Эти инструкции могут вызывать метод или функцию, и они могут выполнять цикл или ветвление по блокам кода. Исполняемые операторы включают **Операторы присваивания**, которые присваивают значение или выражение переменной или константе.

В этом разделе описывается каждая категория. Кроме того, в этом разделе описывается, как объединить несколько инструкций в одной строке и как продолжить выполнение инструкции на нескольких строках.

## <a name="declaration-statements"></a>Инструкции объявления

Операторы объявления используются для именования и определения процедур, переменных, свойств, массивов и констант. При объявлении программного элемента можно также определить его тип данных, уровень доступа и область. Дополнительные сведения см. в разделе [Характеристики объявленных элементов](./declared-elements/declared-element-characteristics.md).

Следующий пример содержит три объявления.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

Первое объявление — это `Sub` оператор. Вместе с его `End Sub` оператором сопоставления объявляется процедура с именем `applyFormat` . Он также указывает, что `applyFormat` это означает, что `Public` любой код, который может ссылаться на него, может вызывать его.

Второе объявление — это `Const` оператор, который объявляет константу `limit` , указывая `Integer` тип данных и значение 33.

Третье объявление — это `Dim` оператор, объявляющий переменную `thisWidget` . Тип данных — это конкретный объект, а именно объект, созданный из `Widget` класса. Можно объявить переменную для любого простейшего типа данных или любого типа объекта, предоставляемого в используемом приложении.

### <a name="initial-values"></a>Начальные значения

При выполнении кода, содержащего оператор объявления, Visual Basic резервирует память, необходимую для объявленного элемента. Если элемент содержит значение, Visual Basic инициализирует его значением по умолчанию для его типа данных. Дополнительные сведения см. в разделе «поведение» в [операторе Dim](../../language-reference/statements/dim-statement.md).

Начальное значение переменной можно присвоить как часть объявления, как показано в следующем примере.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Если переменная является объектной переменной, можно явно создать экземпляр его класса при объявлении с помощью ключевого слова [New operator](../../language-reference/operators/new-operator.md) , как показано в следующем примере.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Обратите внимание, что начальное значение, указанное в операторе объявления, не присваивается переменной до тех пор, пока выполнение не достигнет оператора объявления. До этого времени переменная будет содержать значение по умолчанию для его типа данных.

## <a name="executable-statements"></a>Исполняемые операторы

Исполняемый оператор выполняет действие. Он может вызывать процедуру, переходить к другому месту в коде, выполнять перебор нескольких инструкций или оценивать выражение. Оператор присваивания является особым случаем исполняемого оператора.

В следующем примере используется `If...Then...Else` структура элемента управления для выполнения различных блоков кода на основе значения переменной. В каждом блоке кода `For...Next` цикл выполняется заданное число раз.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

`If`Инструкция в предыдущем примере проверяет значение параметра `clockwise` . Если значение равно `True` , вызывается `spinClockwise` метод `aWidget` . Если значение равно `False` , вызывается `spinCounterClockwise` метод `aWidget` . `If...Then...Else`Структура элемента управления заканчивается на `End If` .

`For...Next`Цикл внутри каждого блока вызывает соответствующий метод несколько раз, равным значению `revolutions` параметра.

## <a name="assignment-statements"></a>Операторы присваивания

Операторы присваивания выполняют операции присваивания, которые состоят из значения с правой стороны оператора присваивания ( `=` ) и сохраняют его в элементе слева, как показано в следующем примере.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

В предыдущем примере инструкция присваивания сохраняет литеральное значение 42 в переменной `v` .

### <a name="eligible-programming-elements"></a>Подходящие программные элементы

Программный элемент в левой части оператора присваивания должен иметь возможность принимать и сохранять значение. Это означает, что это должна быть переменная или свойство, не предназначенное [только для чтения](../../language-reference/modifiers/readonly.md)или которое должно быть элементом массива. В контексте оператора присваивания такой элемент иногда называют *левосторонним* значением для «левого значения».

Значение в правой части оператора присваивания формируется выражением, которое может состоять из любого сочетания литералов, констант, переменных, свойств, элементов массива, других выражений или вызовов функций. Это показано в следующем примере.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

В предыдущем примере значение, содержащееся в переменной, добавляется в `y` значение переменной `z` , а затем добавляется значение, возвращаемое вызовом функции `findResult` . Общее значение этого выражения сохраняется в переменной `x` .

### <a name="data-types-in-assignment-statements"></a>Типы данных в операторах присваивания

В дополнение к числовым значениям оператор присваивания также может назначать `String` значения, как показано в следующем примере.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

Можно также назначать `Boolean` значения с помощью `Boolean` литерала или `Boolean` выражения, как показано в следующем примере.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Аналогичным образом можно назначить соответствующие значения для программирования элементов `Char` `Date` `Object` типа данных, или. Можно также назначить экземпляр объекта элементу, объявленному как класс, из которого создается этот экземпляр.

### <a name="compound-assignment-statements"></a>Составные операторы присваивания

*Составные операторы присваивания* сначала выполняют операцию над выражением, прежде чем присваивать его элементу программирования. В следующем примере показан один из этих операторов, `+=` который увеличивает значение переменной слева от оператора на значение выражения в правой части.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

В предыдущем примере к значению добавляется 1 `n` , а затем это новое значение сохраняется в `n` . Это краткий эквивалент следующей инструкции:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

С помощью операторов этого типа можно выполнять разнообразные операции составного присваивания. Список этих операторов и дополнительные сведения об этих операторах см. в разделе [Операторы присваивания](../../language-reference/operators/assignment-operators.md).

Оператор присваивания объединения ( `&=` ) полезен для добавления строки в конец уже существующих строк, как показано в следующем примере.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Преобразования типов в операторах присваивания

Значение, присваиваемое переменной, свойству или элементу массива, должно иметь тип данных, соответствующий целевому элементу. В общем случае следует попытаться создать значение того же типа данных, что и у целевого элемента. Однако некоторые типы могут быть преобразованы в другие типы во время назначения.

Дополнительные сведения о преобразовании типов данных см. [в разделе преобразования типов в Visual Basic](./data-types/type-conversions.md). Вкратце, Visual Basic автоматически преобразует значение заданного типа в любой другой тип, в который он расширяется. *Расширяющее преобразование* — это одно из, которое всегда выполняется во время выполнения и не теряет никаких данных. Например, Visual Basic преобразует `Integer` значение в `Double` при необходимости, поскольку `Integer` расширяется до `Double` . Для получения дополнительной информации см. [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Сужающие преобразования* (которые не расширяются) приводят к риску сбоя во время выполнения или потери данных. Сужающие преобразования можно выполнить явным образом с помощью функции преобразования типа. также можно указать компилятору выполнять все преобразования неявно, задав `Option Strict Off` . Дополнительные сведения см. в разделе [явные и неявные преобразования](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Размещение нескольких инструкций на одной строке

Можно использовать несколько операторов в одной строке, разделенных символом двоеточия ( `:` ). Это показано в следующем примере.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Хотя иногда удобно, такая форма синтаксиса делает код трудным для чтения и обслуживания. Поэтому рекомендуется размещать один оператор в строке.

## <a name="continuing-a-statement-over-multiple-lines"></a>Продолжение выполнения инструкции на нескольких строках

Оператор обычно размещается на одной строке, но если он слишком длинный, его можно продолжить на следующей строке с помощью последовательности продолжения строки, которая состоит из пробела, за которым следует символ подчеркивания (), `_` за которым следует возврат каретки. В следующем примере `MsgBox` Исполняемый оператор продолжает находиться на двух строках.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Неявное продолжение строки

Во многих случаях оператор можно продолжить в следующей строке подряд без использования символа подчеркивания ( `_` ). Следующие элементы синтаксиса неявно пропродолжат оператор в следующей строке кода.

- После запятой ( `,` ). Пример:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- После открывающей скобки ( `(` ) или перед закрывающей круглой скобкой ( `)` ). Пример:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- После открывающей фигурной скобки ( `{` ) или перед закрывающей фигурной скобкой ( `}` ). Пример:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](./objects-and-classes/object-initializers-named-and-anonymous-types.md) или [Инициализаторы коллекций](./collection-initializers/index.md).

- После открытого внедренного выражения ( `<%=` ) или перед закрытием внедренного выражения ( `%>` ) в XML-литерале. Пример:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Дополнительные сведения см. [в разделе внедренные выражения в XML](./xml/embedded-expressions-in-xml.md).

- После оператора объединения ( `&` ). Пример:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Дополнительные сведения см. [в разделе операторы, перечисленные по функциональным возможностям](../../language-reference/operators/operators-listed-by-functionality.md).

- После операторов присваивания ( `=` ,, `&=` ,, `:=` `+=` `-=` , `*=` , `/=` , `\=` , `^=` , `<<=` , `>>=` ). Пример:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Дополнительные сведения см. [в разделе операторы, перечисленные по функциональным возможностям](../../language-reference/operators/operators-listed-by-functionality.md).

- После бинарных операторов ( `+` ,, `-` ,, `/` `*` `Mod` , `<>` , `<` , `>` , `<=` ,,, `>=` `^` `>>` , `<<` , `And` , `AndAlso` ,,, `Or` `OrElse` `Like` , `Xor` ) в выражении. Пример:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Дополнительные сведения см. [в разделе операторы, перечисленные по функциональным возможностям](../../language-reference/operators/operators-listed-by-functionality.md).

- После `Is` операторов и `IsNot` . Пример:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Дополнительные сведения см. [в разделе операторы, перечисленные по функциональным возможностям](../../language-reference/operators/operators-listed-by-functionality.md).

- После символа квалификатора элемента ( `.` ) и перед именем члена. Пример:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Однако при `_` использовании `With` инструкции или предоставлении значений в списке инициализации для типа необходимо включить символ продолжения строки () после символа квалификатора элемента. Рассмотрите возможность разбиения строки после оператора присваивания (например, `=` ) при использовании `With` инструкций или списков инициализации объектов. Пример:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Дополнительные сведения см [. в разделе with... End с оператором](../../language-reference/statements/with-end-with-statement.md) или [инициализаторами объектов: именованные и анонимные типы](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- После квалификатора свойства оси XML ( `.` или `.@` или `...` ). Однако при использовании ключевого слова необходимо включить символ продолжения строки ( `_` ) при указании квалификатора элемента `With` . Пример:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Дополнительные сведения см. в разделе [Свойства осей XML](../../language-reference/xml-axis/index.md).

- После знака "меньше" (<) или перед знаком "больше `>` " () при указании атрибута. Также после знака `>` "больше" () при указании атрибута. Однако `_` при указании атрибутов уровня сборки или уровня модуля необходимо включить символ продолжения строки (). Пример:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Дополнительные сведения см. в разделе [Общие сведения об атрибутах](../concepts/attributes/index.md).

- До и после операторов запроса ( `Aggregate` , `Distinct` , `From` , `Group By` , `Group Join` , `Join` , `Let` , `Order By` , `Select` ,,,,, `Skip` ,,,, `Skip While` `Take` `Take While` `Where` `In` `Into` `On` `Ascending` и `Descending` ). Нельзя разбивать строку между ключевыми словами операторов запроса, которые состоят из нескольких ключевых слов ( `Order By` , `Group Join` , `Take While` и `Skip While` ). Пример:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Дополнительные сведения см. в разделе [запросы](../../language-reference/queries/index.md).

- После `In` ключевого слова в `For Each` операторе. Пример:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../language-reference/statements/for-each-next-statement.md).

- После `From` ключевого слова в инициализаторе коллекции. Пример:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Дополнительные сведения см. в разделе [Инициализаторы коллекций](collection-initializers/index.md).

## <a name="adding-comments"></a>Добавление комментариев

Исходный код не всегда говорят сами за себя, даже программисту, который написал его. Для облегчения документирования кода большинство программистов используют внедренные комментарии. Комментарии в коде могут объяснить процедуру или конкретную инструкцию, которая может быть прочитана или обработана другим пользователем позже. Visual Basic игнорирует комментарии во время компиляции и не влияет на скомпилированный код.

Строки комментариев начинаются с апострофа ( `'` ) или `REM` за ним пробела. Их можно добавлять в любом месте кода, за исключением строк. Чтобы добавить комментарий к оператору, вставьте апостроф или `REM` после оператора, за которым следует комментарий. Комментарии также можно найти в отдельной строке. В следующем примере демонстрируются эти возможности.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Проверка ошибок компиляции

Если после ввода строки кода линия отображается волнистой синей линией (также может появиться сообщение об ошибке), в инструкции присутствует синтаксическая ошибка. Необходимо выяснить, что именно не так с оператором (просмотрев список задач, или навести указатель мыши на ошибку с помощью указателя и прочитать сообщение об ошибке) и исправить его. До тех пор, пока в коде не будут исправлены все синтаксические ошибки, программа не сможет правильно выполнить компиляцию.

## <a name="related-sections"></a>Связанные разделы

|Термин|Определение|
|---|---|
|[Операторы присваивания](../../language-reference/operators/assignment-operators.md)|Содержит ссылки на страницы справочника по языку, охватывающие операторы присваивания, такие как `=` , `*=` и `&=` .|
|[Операторы и выражения](./operators-and-expressions/index.md)|Показывает, как объединить элементы с операторами для получения новых значений.|
|[Практическое руководство. Разбиение и объединение инструкций в коде](../program-structure/how-to-break-and-combine-statements-in-code.md)|Показывает, как разбить один оператор на несколько строк и поместить несколько инструкций в одну строку.|
|[Практическое руководство. Операторы меток](../program-structure/how-to-label-statements.md)|Показывает, как пометить строку кода.|
