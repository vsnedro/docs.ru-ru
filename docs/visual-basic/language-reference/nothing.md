---
description: Дополнительные сведения о ключевом слове "Nothing" (Visual Basic)
title: Nothing - ключевое слово
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: c77f39c0a431dd05aabd24a235fb2dc88ea29e69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674731"
---
# <a name="nothing-keyword-visual-basic"></a>Ключевое слово Nothing (Visual Basic)

Представляет значение по умолчанию для любого типа данных. Для ссылочных типов значением по умолчанию является `null` ссылка. Для типов значений значение по умолчанию зависит от того, допускает ли тип значения значение null.

> [!NOTE]
> Для типов значений, не допускающих значения NULL, `Nothing` в Visual Basic отличается от `null` в C#. В Visual Basic при задании переменной типа значения, не допускающего значения NULL `Nothing` , переменной присваивается значение по умолчанию для его объявленного типа. В C# при присвоении переменной типа значения, не допускающего значения NULL `null` , возникает ошибка времени компиляции.

## <a name="remarks"></a>Remarks

`Nothing` представляет значение по умолчанию для типа данных. Значение по умолчанию зависит от того, имеет ли переменная тип значения или ссылочный тип.

Переменная *типа значения* напрямую содержит его значение. Типы значений включают все числовые типы данных,,, `Boolean` `Char` `Date` , все структуры и все перечисления. Переменная *ссылочного типа* хранит ссылку на экземпляр объекта в памяти. Ссылочные типы включают классы, массивы, делегаты и строки. Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../programming-guide/language-features/data-types/value-types-and-reference-types.md).

Если переменная имеет тип значения, поведение `Nothing` зависит от того, имеет ли переменная тип данных, допускающий значение null. Для представления типа значения, допускающего значение null, добавьте `?` модификатор к имени типа. Присваивание `Nothing` переменной, допускающей значение null, присваивает значение `null` . Дополнительные сведения и примеры см. в разделе [типы значений, допускающие значения NULL](../programming-guide/language-features/data-types/nullable-value-types.md).

Если переменная имеет тип значения, не допускающий значения NULL, при присвоении ей `Nothing` присваивается значение по умолчанию для его объявленного типа. Если этот тип содержит члены переменных, все они устанавливаются в значения по умолчанию. Следующий пример иллюстрирует это для скалярных типов.

[!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]

Если переменная имеет ссылочный тип, присвоение `Nothing` переменной задает `null` ссылку на тип переменной. Переменная, для которой задана `null` ссылка, не связана ни с одним объектом. Следующий пример демонстрирует это:

[!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]

При проверке наличия переменной ссылки (или типа значения, допускающего значение null) не `null` Используйте `= Nothing` или `<> Nothing` . Всегда используйте `Is Nothing` или `IsNot Nothing` .

Для строк в Visual Basic пустая строка равна `Nothing` . Таким образом, `"" = Nothing` имеет значение true.

В следующем примере показаны сравнения, использующие `Is` `IsNot` операторы и.

[!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]

Если объявить переменную без использования `As` предложения и присвоить ей значение `Nothing` , переменная имеет тип `Object` . Примером этого является `Dim something = Nothing` . В этом случае возникает ошибка времени компиляции, когда `Option Strict` имеет значение on и `Option Infer` отключено.

При назначении `Nothing` объектной переменной она больше не ссылается ни на один экземпляр объекта. Если переменная ранее ссылалась на экземпляр, задание для него значения не `Nothing` завершает сам экземпляр. Экземпляр завершается, и связанные с ним память и системные ресурсы освобождаются, только если сборщик мусора (GC) обнаружит, что активные ссылки не остались.

`Nothing` отличается от <xref:System.DBNull> объекта, который представляет неинициализированный вариант или несуществующий столбец базы данных.

## <a name="see-also"></a>См. также

- [Оператор Dim](./statements/dim-statement.md)
- [Время существования: создание и уничтожение объектов](../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Время существования в Visual Basic](../programming-guide/language-features/declared-elements/lifetime.md)
- [Оператор Is](./operators/is-operator.md)
- [Оператор IsNot](./operators/isnot-operator.md)
- [Типы значений, допускающие значение NULL](../programming-guide/language-features/data-types/nullable-value-types.md)
