---
title: Выражение nameof. Справочник по C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: d71acf0cf7d5cdcfa5310455af2120fa1f82d567
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135923"
---
# <a name="nameof-expression-c-reference"></a>Выражение nameof (справочник по C#)

Выражение `nameof` создает имя, тип или элемент переменной в качестве строковой константы:

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

Если используются [буквальные идентификаторы](../tokens/verbatim.md), символ `@` не является частью имени, как показано в следующем примере.

[!code-csharp-interactive[nameof verbatim](snippets/NameOfOperator.cs#Verbatim)]

Значение выражения `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.

С помощью выражения `nameof` можно сделать код проверки аргументов более удобным:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

Выражение `nameof` доступно в C# версии 6 и выше.

## <a name="c-language-specification"></a>Спецификация языка C#

См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
