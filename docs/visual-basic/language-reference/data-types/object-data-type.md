---
description: 'Дополнительные сведения: тип данных Object'
title: Object Data Type
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: b1f169e4e590335a0879f5ecd9b68507a3fa2ccb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792158"
---
# <a name="object-data-type"></a>Object Data Type

Содержит адреса, которые ссылаются на объекты. В переменную можно назначить любой ссылочный тип (строка, массив, класс или интерфейс) `Object` . `Object`Переменная также может ссылаться на данные любого типа значения (числовой,,,, `Boolean` `Char` `Date` Структура или перечисление).

## <a name="remarks"></a>Remarks

`Object`Тип данных может указывать на данные любого типа данных, включая любой экземпляр объекта, распознаваемый приложением. Используйте `Object` , если во время компиляции неизвестно, на какой тип данных может указывать переменная.

Значение по умолчанию `Object` — `Nothing` (пустая ссылка).

## <a name="data-types"></a>Типы данных

Переменной можно присвоить переменную, константу или выражение любого типа данных `Object` . Чтобы определить тип данных `Object` , на который в настоящее время ссылается переменная, можно использовать <xref:System.Type.GetTypeCode%2A> метод <xref:System.Type?displayProperty=nameWithType> класса. Это показано в следующем примере.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

`Object`Тип данных является ссылочным типом. Однако Visual Basic обрабатывает `Object` переменную как тип значения, если она ссылается на данные типа значения.

## <a name="storage"></a>Память

Любой тип данных, на который он ссылается, `Object` переменная не содержит само значение данных, а указатель на это значение. Он всегда использует четыре байта в памяти компьютера, но не включает хранилище для данных, представляющих значение переменной. Из-за кода, использующего указатель для нахождение данных, `Object` переменные, содержащие типы значений, немного медленнее, чем явно типизированные переменные.

## <a name="programming-tips"></a>Советы по программированию

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для платформа .NET Framework, например автоматизации или COM-объекты, помните, что типы указателей в других средах несовместимы с `Object` типом Visual Basic.

- **Производительность.** Переменная, объявляемая с `Object` типом, достаточно гибка, чтобы содержать ссылку на любой объект. Однако при вызове метода или свойства для такой переменной всегда вызывается *позднее связывание* (во время выполнения). Чтобы принудительно выполнить *раннее связывание* (во время компиляции) и повысить производительность, объявите переменную с конкретным именем класса или приведите ее к конкретному типу данных.

  При объявлении объектной переменной попробуйте использовать конкретный тип класса, например <xref:System.OperatingSystem> , вместо обобщенного `Object` типа. Также следует использовать наиболее конкретный класс, например <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Control> , вместо, чтобы получить доступ к его свойствам и методам. Для поиска доступных имен классов обычно можно использовать список **классы** в **обозревателе объектов** .

- **Расширяющие.** Все типы данных и все ссылочные типы расширяются до `Object` типа данных. Это означает, что можно преобразовать любой тип в `Object` без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.

  Однако при преобразовании между типами значений и `Object` Visual Basic выполняет операции, называемые *упаковкой* и *распаковкой*, что делает выполнение более медленным.

- **Символы типа.** `Object` не имеет символа типа литерала или символа типа идентификатора.

- **Тип Framework.** Соответствующий тип в платформа .NET Framework — это <xref:System.Object?displayProperty=nameWithType> класс.

## <a name="example"></a>Пример

В следующем примере показана `Object` переменная, указывающая на экземпляр объекта.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>См. также

- <xref:System.Object>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Практическое руководство. Определение наличия связи между двумя объектами](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Практическое руководство. Определение идентичности двух объектов](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
