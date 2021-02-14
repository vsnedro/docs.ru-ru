---
description: 'Узнайте подробнее о: Перегрузки операторов'
title: Перегрузки операторов
ms.date: 10/22/2008
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: e6552f35081afa542e4dc14239206a63c7c1bd59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713329"
---
# <a name="operator-overloads"></a>Перегрузки операторов

Перегрузки операторов позволяют отображать типы платформ, как встроенные примитивы языка.

 Хотя в некоторых ситуациях это разрешено и полезно, перегрузки операторов следует использовать осторожно. Существует множество случаев злоупотреблений перегрузкой операторов. Например, когда конструкторы платформы использовали операторы для операций, которые должны быть простыми методами. Следующие рекомендации помогут решить, когда и как использовать перегрузку операторов.

 ❌ НЕ определяйте перегрузки операторов, за исключением типов, которые должны быть похожи на примитивные (встроенные) типы.

 ✔️ РЕКОМЕНДУЕТСЯ определять перегрузки операторов в типе, который должен быть похож на примитивный тип.

 Например, в <xref:System.String?displayProperty=nameWithType> определены `operator==` и `operator!=`.

 ✔️ РЕКОМЕНДУЕТСЯ️ определить перегрузки операторов в структурах, которые представляют числа (например, <xref:System.Decimal?displayProperty=nameWithType>).

 ❌ ОТНЕСИТЕСЬ к определению перегрузки операторов серьезно.

 Перегрузка операторов полезна в случаях, когда сразу очевидно, каким будет результат операции. Например, есть смысл вычесть одно значение <xref:System.DateTime> из другого `DateTime` и получить <xref:System.TimeSpan>. Однако не рекомендуется использовать оператор логического объединения, чтобы объединить два запроса к базе данных или использовать оператор сдвига для записи в поток.

 ❌ НЕ следует предоставлять перегрузки операторов, если по крайней мере один из операндов не относится к типу, определяющему перегрузку.

 ✔️ ВЫПОЛНЯЙТЕ операторы перегрузки в симметричном режиме.

 Например, если перегрузить `operator==`, необходимо также перегрузить `operator!=`. Аналогично если перегрузить `operator<`, то необходимо также перегрузить `operator>` и т. д.

 ✔️️ ПОДБЕРИТЕ методы с понятными именами, которые соответствуют каждому перегруженному оператору.

 Многие языки не поддерживают перегрузку операторов. По этой причине рекомендуется, чтобы типы с перегруженными операторами, включали дополнительный метод с соответствующим доменным именем, обеспечивающим эквивалентную функциональность.

 В следующей таблице приведен список операторов и соответствующие понятные имена методов.

|Символ оператора C#|Имя метаданных|Понятное имя|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a>Перегрузка оператора равенства ==

 Перегрузка `operator ==` довольно сложная. Семантика оператора должна быть совместима с несколькими другими элементами, например <xref:System.Object.Equals%2A?displayProperty=nameWithType>.

### <a name="conversion-operators"></a>Операторы преобразования

 Операторы преобразования — это унарные операторы, позволяющие выполнять преобразование из одного типа в другой. Операторы должны быть определены как статические элементы либо как операнды или типы возвращаемого значения. Существует два типа операторов преобразования: implicit и explicit.

 ❌ НЕ предоставляйте оператор преобразования, если пользователь явно не ожидает такое преобразование.

 ❌ НЕ определяйте операторы преобразования за пределами домена типа.

 Например, <xref:System.Int32>, <xref:System.Double> и <xref:System.Decimal> являются числовыми типами, а <xref:System.DateTime> — нет. Поэтому при преобразовании `Double(long)` в `DateTime` не должен использоваться оператор преобразования. В таком случае предпочтительнее использовать конструктор.

 ❌ НЕ предоставляйте неявный оператор преобразования, если преобразование может быть с потерями.

 Например, не существует неявного преобразования из `Double` в `Int32`, так как `Double`имеет более широкий диапазон, чем `Int32`. Явный оператор преобразования можно предоставить даже в том случае, если преобразование может быть с потерями.

 ❌ НЕ создавайте исключения из неявных приведений.

 Пользователям очень сложно понять, что происходит, так как они могут не знать, что выполняется преобразование.

 ✔️ РЕКОМЕНДУЕТСЯ создать <xref:System.InvalidCastException?displayProperty=nameWithType>, если вызов оператора приведения приводит к преобразованию с потерями, а контракт оператора не допускает этого.

 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также

- [Правила разработки членов](member.md)
- [Рекомендации по проектированию на основе Framework](index.md)
