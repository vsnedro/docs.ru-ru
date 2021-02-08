---
description: 'Дополнительные сведения: User-Defined тип данных'
title: Тип данных, определенный пользователем
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 6eb94b38e2d29a4bbdfcf94de307bbe07a2c1b0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774971"
---
# <a name="user-defined-data-type"></a>Тип данных, определенный пользователем

Хранит данные в определенном формате. `Structure`Оператор определяет формат.

Предыдущие версии Visual Basic поддерживают определяемый пользователем тип (UDT). Текущая версия расширяет определяемый пользователем тип на *структуру*. Структура — это объединение одного или нескольких *элементов* различных типов данных. Visual Basic обрабатывает структуру как единое целое, хотя вы также можете обращаться к ее членам по отдельности.

## <a name="remarks"></a>Remarks

Определяйте и используйте тип данных Structure, если необходимо объединить различные типы данных в один блок или если ни один из простейших типов данных не подходит для ваших нужд.

Значение по умолчанию для типа данных Structure состоит из сочетания значений по умолчанию для каждого из его элементов.

## <a name="declaration-format"></a>Формат объявления

Объявление структуры начинается с [оператора Structure](../statements/structure-statement.md) и заканчивается `End Structure` инструкцией. `Structure`Инструкция предоставляет имя структуры, которая также является идентификатором типа данных, определяемого структурой. Другие части кода могут использовать этот идентификатор для объявления переменных, параметров и возвращаемых значений функций в качестве типа данных этой структуры.

Объявления между `Structure` `End Structure` операторами и определяют элементы структуры.

## <a name="member-access-levels"></a>Уровни доступа к членам

Каждый член необходимо объявить с помощью [оператора Dim](../statements/dim-statement.md) или оператора, определяющего уровень доступа, например [Public](../modifiers/public.md), [Friend](../modifiers/friend.md)или [Private](../modifiers/private.md). При использовании `Dim` инструкции уровень доступа по умолчанию равен public.

## <a name="programming-tips"></a>Советы по программированию

- **Потребление памяти.** Как и для всех составных типов данных, вы не можете безопасно вычислить общее потребление памяти для структуры, добавив в них номинальные объемы выделяемого пространства для его членов. Кроме того, нельзя безопасно предположить, что порядок хранения в памяти совпадает с порядком объявления. Если необходимо управлять структурой хранилища структуры, можно применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут к `Structure` оператору.

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для платформа .NET Framework, например автоматизации или COM-объекты, помните, что определяемые пользователем типы в других средах несовместимы с типами структуры Visual Basic.

- **Расширяющие.** Автоматическое преобразование в любой тип данных структуры или из него отсутствует. Операторы преобразования в структуре можно определить с помощью оператора [оператора](../statements/operator-statement.md), а каждый оператор преобразования можно объявить как `Widening` или `Narrowing` .

- **Символы типа.** Типы данных структуры не имеют символа литерального типа или символа типа идентификатора.

- **Тип Framework.** В платформа .NET Framework нет соответствующего типа. Все структуры наследуют от класса платформа .NET Framework <xref:System.ValueType?displayProperty=nameWithType> , но никакая отдельная структура не соответствует <xref:System.ValueType?displayProperty=nameWithType> .

## <a name="example"></a>Пример

В следующей парадигме показана структура объявления структуры.

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a>См. также

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Оператор Structure](../statements/structure-statement.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
