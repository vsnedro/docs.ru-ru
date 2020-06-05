---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 3a1de120f5f97ba93939f332f121d70cd3091216
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392978"
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
В Visual Basic есть два типа типов: ссылочные типы и типы значений. В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно. Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная. В случае с типами значений каждая переменная имеет собственную копию данных, и операции с одной переменной не могут влиять на другую (за исключением [модификатора ByRef в параметрах](../../../language-reference/modifiers/byref.md)).
  
## <a name="value-types"></a>Типы значений  
 Тип данных — это *тип значения* , если он содержит данные в пределах отдельного выделения памяти. К типам значений относятся следующие.  
  
- Все числовые типы данных  
  
- `Boolean`, `Char` и `Date`.  
  
- Все структуры, даже если их члены являются ссылочными типами  
  
- Перечисления, так как их базовый тип всегда,,,,,, `SByte` `Short` `Integer` `Long` `Byte` `UShort` `UInteger` или`ULong`  
  
 Каждая структура является типом значения, даже если она содержит члены ссылочного типа. По этой причине типы значений, такие как `Char` и `Integer` , реализуются с помощью структур .NET Framework.  
  
 Тип значения можно объявить с помощью зарезервированного ключевого слова, например `Decimal` . `New`Для инициализации типа значения также можно использовать ключевое слово. Это особенно полезно, если тип имеет конструктор, принимающий параметры. Примером этого является <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> конструктор, который создает новое `Decimal` значение из предоставляемых частей.  
  
## <a name="reference-types"></a>Ссылочные типы  
 *Ссылочный тип* хранит ссылку на свои данные. К ссылочным типам относятся следующие:  
  
- `String`  
  
- Все массивы, даже если их элементы являются типами значений  
  
- Типы классов, такие как<xref:System.Windows.Forms.Form>  
  
- Делегаты  
  
 Класс является *ссылочным типом*. Обратите внимание, что каждый массив является ссылочным типом, даже если его члены являются типами значений.  
  
 Поскольку каждый ссылочный тип представляет базовый класс .NET Framework, при его инициализации необходимо использовать ключевое слово [New operator](../../../language-reference/operators/new-operator.md) . Следующая инструкция инициализирует массив.  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Элементы, не являющиеся типами  
 Следующие элементы программирования не являются типами, так как их нельзя указать в качестве типа данных для объявленного элемента:  
  
- Пространства имен  
  
- Модули  
  
- События  
  
- Свойства и процедуры  
  
- Переменные, константы и поля  
  
## <a name="working-with-the-object-data-type"></a>Работа с типом данных Object  
 Переменной типа данных можно присвоить либо ссылочный тип, либо тип значения `Object` . `Object`Переменная всегда хранит ссылку на данные, а не сами данные. Однако при присвоении переменной типа значения `Object` она ведет себя так, как если бы она содержала свои собственные данные. Дополнительные сведения см. в разделе [тип данных объекта](../../../language-reference/data-types/object-data-type.md).  
  
 Определить, выступает ли переменная в `Object` качестве ссылочного типа или типа значения, можно, передав ее <xref:Microsoft.VisualBasic.Information.IsReference%2A> методу в <xref:Microsoft.VisualBasic.Information> классе <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>Возвращает, `True` Если содержимое `Object` переменной представляет ссылочный тип.  
  
## <a name="see-also"></a>См. также раздел

- [Типы значений, допускающие значение null](nullable-value-types.md)
- [Преобразование типов в Visual Basic](type-conversions.md)
- [Оператор Structure](../../../language-reference/statements/structure-statement.md)
- [Эффективное использование типов данных](efficient-use-of-data-types.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Типы данных](index.md)
