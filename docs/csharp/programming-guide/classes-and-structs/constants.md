---
title: Руководство по программированию на C#. Константы
description: Константы в C# — это литеральные значения, которые известны во время компиляции и не изменяются после компиляции программы. Константами могут быть только встроенные типы C#.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 4783aff8e9424c90e46cb52692a3e645e995d914
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899078"
---
# <a name="constants-c-programming-guide"></a>Константы (Руководство по программированию на C#)

Константы — это постоянные значения, которые известны во время компиляции и не изменяются во время выполнения программы. Константы должны объявляться с модификатором [const](../../language-reference/keywords/const.md). Только [встроенные типы](../../language-reference/builtin-types/built-in-types.md) C# (за исключением <xref:System.Object?displayProperty=nameWithType>) могут быть объявлены как `const`. Пользовательские типы, включая классы, структуры и массивы, не могут объявляться как `const`. Модификатор [readonly](../../language-reference/keywords/readonly.md) позволяет создать класс, структуру или массив, которые инициализируются один раз (например, в конструкторе), и впоследствии изменить их нельзя.  
  
 C# не поддерживает методы, свойства или события `const`.  
  
 Тип перечисления позволяет определять именованные константы для целочисленных встроенных типов (например `int`, `uint`, `long` и т. д.). Дополнительные сведения см. в разделе [Перечисление](../../language-reference/builtin-types/enum.md).  
  
 Константы должны инициализироваться сразу после объявления. Пример:  
  
 [!code-csharp[Calendar#1](snippets/constants/Calendar.cs#1)]
  
 В этом примере константа `Months` всегда имеет значение 12, и его не может изменить даже сам класс. На самом деле в случае, если компилятор встречает идентификатор константы в исходном коде C# (например, `Months`), он подставляет значение литерала непосредственно в создаваемый им промежуточный язык (IL). Поскольку с константой в среде выполнения не связан адрес ни одной переменной, поля `const` не могут передаваться по ссылке и отображаться в выражении как левостороннее значение.  
  
> [!NOTE]
> Будьте внимательны, ссылаясь на постоянные значения, определенные в другом коде, например, в DLL. Если в новой версии DLL для константы определяется новое значение, старое значение литерала хранится в вашей программе вплоть до повторной компиляции для новой версии.  
  
 Несколько констант одного типа можно объявить одновременно, например:  
  
 [!code-csharp[Calendar#2](snippets/constants/Calendar.cs#2)]
  
 Выражение, которое используется для инициализации константы, может ссылаться на другую константу, если не создает циклическую ссылку. Пример:  
  
 [!code-csharp[Calendar#3](snippets/constants/Calendar.cs#3)]
  
 Константы могут иметь пометку [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) или [private protected](../../language-reference/keywords/private-protected.md). Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к константе. Дополнительные сведения см. в разделе [Модификаторы доступа](./access-modifiers.md).  
  
 Доступ к константам осуществляется так, как если бы они были [статическими](../../language-reference/keywords/static.md) полями, поскольку значение константы одинаково для всех экземпляров типа. Для их объявления используйте ключевое слово `static`. Выражения, которые не относятся к классу, определяющему константу, должны включать имя класса, период и имя константы для доступа к этой константе. Пример:  
  
 [!code-csharp[Calendar#4](snippets/constants/Calendar.cs#4)]
  
## <a name="c-language-specification"></a>Спецификация языка C#  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Свойства](./properties.md)
- [Типы](../types/index.md)
- [readonly](../../language-reference/keywords/readonly.md)
- [Immutability in C# Part One: Kinds of Immutability](/archive/blogs/ericlippert/immutability-in-c-part-one-kinds-of-immutability) (Неизменность в C#, часть 1. Виды неизменности)
