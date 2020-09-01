---
description: Справочник по C#. Оператор delegate
title: Справочник по C#. Оператор delegate
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dfaaf40c0f5a19534adef3be7e3c917bc95c4a8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122255"
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

Вы также можете использовать ключевое слово `delegate` для объявления [типа делегата](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Операторы и выражения C#](index.md)
- [=> оператор](lambda-operator.md)
