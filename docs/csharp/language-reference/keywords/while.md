---
description: Справочник по C#. while
title: Справочник по C#. while
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 97299f9ac6f2cdd6bbddf831b3ee2ad711935fbe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141872"
---
# <a name="while-c-reference"></a>while (Справочник по C#)

Оператор `while` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`. Так как это выражение оценивается перед каждым выполнением цикла, цикл `while` выполняется ноль или несколько раз. Это отличает его от цикла [do](do.md), который выполняется от одного до нескольких раз.

В любой точке блока операторов `while` можно разорвать цикл с помощью оператора [break](break.md).

Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md). Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла. В противном случае выполнение продолжается с первого оператора после цикла.

Можно также выйти из цикла `while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).

## <a name="example"></a>Пример

В следующем примере показано применение оператора `while`. Нажмите **Запустить** для выполнения примера кода. После этого можно изменить код и запустить его еще раз.

[!code-csharp-interactive[while loop example](snippets/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор while](~/_csharplang/spec/statements.md#the-while-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Оператор do](do.md)
