---
description: Справочник по C#. Оператор delegate
title: Справочник по C#. Оператор delegate
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247661"
---
# <a name="delegate-operator-c-reference"></a>Справочник по C#. Оператор delegate

Оператор `delegate` создает анонимный метод, который можно преобразовать в тип делегата:

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> Начиная с C# 3, лямбда-выражения позволяют быстрее и проще создавать анонимные функции. С помощью [оператора =>](lambda-operator.md) создайте лямбда-выражение:
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> См. подробнее о возможностях [лямбда-выражений](lambda-expressions.md) (например, об использовании внешних переменных).

При использовании оператора `delegate` вам, возможно, нужно будет пропустить список параметров. В таком случае созданный анонимный метод можно будет преобразовать в тип делегата с любым списком параметров, как показано в примере ниже:

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

Это единственная функция анонимных методов, которая не поддерживается лямбда-выражениями. Во всех остальных случаях лямбда-выражение является предпочтительным способом написания встроенного кода.

Начиная с C# 9.0, можно использовать [отмены](../../discards.md), чтобы указать два или более входных параметра анонимного метода, которые не используются методом:

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

Если только один параметр имеет имя `_`, для обеспечения обратной совместимости `_` рассматривается как имя этого параметра в анонимном методе.

Кроме того, начиная с C# 9.0 можно использовать модификатор `static` в объявлении анонимного метода:

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

Статический анонимный метод не может записывать локальные переменные или состояние экземпляра из охватывающих областей.

Вы также можете использовать ключевое слово `delegate` для объявления [типа делегата](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Операторы и выражения C#](index.md)
- [=> оператор](lambda-operator.md)
