---
description: 'Дополнительные сведения: эффективное использование типов данных (Visual Basic)'
title: Эффективное использование типов данных
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: e7660bbdec530ef18d663975e314d90b64e4b055
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476440"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Эффективное использование типов данных (Visual Basic)

Тип данных назначается необъявленным переменным и переменным, объявленным без типа данных `Object` . Это упрощает написание программ, но может привести к более медленному их выполнению.

## <a name="strong-typing"></a>Строгая типизация

 Указание типов данных для всех переменных называется *строгой типизацией*. Использование строгой типизации имеет несколько преимуществ.

- Он обеспечивает поддержку IntelliSense для переменных. Это позволяет просматривать их свойства и другие члены по мере ввода кода.

- Он использует преимущества проверки типов компилятора. Это перехватывает инструкции, которые могут завершиться ошибкой во время выполнения из-за таких ошибок, как переполнение. Он также перехватывает вызовы методов для объектов, которые их не поддерживают.

- Это приводит к ускорению выполнения кода.

## <a name="most-efficient-data-types"></a>Наиболее эффективные типы данных

 Для переменных, которые никогда не содержат дробей, целочисленные типы данных более эффективны, чем Нецелочисленные типы. В Visual Basic `Integer` и `UInteger` являются наиболее эффективными числовыми типами.

 Для дробных чисел `Double` является наиболее эффективным типом данных, так как процессоры на текущих платформах выполняют операции с плавающей запятой с двойной точностью. Однако операции с `Double` не так быстро, как с целочисленными типами, такими как `Integer` .

## <a name="specifying-data-type"></a>Указание типа данных

 Используйте [оператор Dim](../../../language-reference/statements/dim-statement.md) для объявления переменной определенного типа. Уровень доступа можно указать одновременно с помощью ключевого слова [Public](../../../language-reference/modifiers/public.md), [protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)или [Private](../../../language-reference/modifiers/private.md) , как показано в следующем примере.

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a>Преобразование символов

 `AscW`Функции и `ChrW` работают в Юникоде. Их следует использовать в предпочтениях `Asc` и `Chr` , которые должны преобразовываться в Юникод и из него.

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Типы данных](index.md)
- [Числовые типы данных](numeric-data-types.md)
- [Объявление переменной](../variables/variable-declaration.md)
- [Использование технологии IntelliSense](/visualstudio/ide/using-intellisense)
