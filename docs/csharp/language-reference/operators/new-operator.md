---
description: Справочник по C#. Оператор new
title: Справочник по C#. Оператор new
ms.date: 10/02/2020
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 3125f3d2c694dcfc5682ee482f3f76072ac3726d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609386"
---
# <a name="new-operator-c-reference"></a>Оператор new (справочник по C#)

Оператор `new` создает экземпляр типа.

Ключевое слово `new` можно также использовать как [модификатор объявления члена](../keywords/new-modifier.md) или [ограничение универсального типа](../keywords/new-constraint.md).

## <a name="constructor-invocation"></a>Вызов конструктора

Для создания экземпляра типа обычно вызывается один из [конструкторов](../../programming-guide/classes-and-structs/constructors.md) этого типа с помощью оператора `new`:

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

Для создания экземпляра объекта и его инициализации в одном операторе можно использовать [инициализатор объекта или элементов](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) с оператором `new`, как в следующем примере:

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

Начиная с версии C# 9.0 выражения вызова конструктора имеют целевой тип. То есть, если известен целевой тип выражения, вы можете опустить имя типа, как показано в следующем примере:

:::code language="csharp" source="snippets/shared/NewOperator.cs" id="SnippetTargetTyped":::

Как показано в предыдущем примере, выражение `new` с целевым типом всегда указывается в скобках.

Если целевой тип выражения `new` неизвестен (например, если вы используете ключевое слово [`var`](../keywords/var.md)), нужно указать имя типа.

## <a name="array-creation"></a>создание массива

С помощью оператора `new` можно также создать экземпляр массива, как показано в следующем примере:

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

Чтобы создать экземпляр массива и заполнить его элементами в одном операторе, используйте синтаксис инициализации массива. В следующем примере показаны различные способы сделать это:

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).

## <a name="instantiation-of-anonymous-types"></a>Создание экземпляров анонимных типов

Чтобы создать экземпляр [анонимного типа](../../programming-guide/classes-and-structs/anonymous-types.md), используйте оператор `new` и синтаксис инициализации объекта:

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a>Уничтожение экземпляров типа

Уничтожать ранее созданные экземпляры типа необязательно. Экземпляры как ссылочных типов, так и типов значений уничтожаются автоматически. Экземпляры типов значений уничтожаются, как только уничтожается содержащий их контекст. Экземпляры ссылочных типов уничтожаются [сборщиком мусора](../../../standard/garbage-collection/index.md) в неуказанное время после удаления последней ссылки на них.

Для экземпляров типа, которые содержат неуправляемые ресурсы, например дескриптор файла, рекомендуется использовать детерминированную очистку, чтобы как можно скорее высвободить эти ресурсы. Дополнительные сведения см. в справке по API <xref:System.IDisposable?displayProperty=nameWithType> и статье об [операторе using](../keywords/using-statement.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Пользовательский тип не может перегружать оператор `new`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор new](~/_csharplang/spec/expressions.md#the-new-operator)[спецификация языка C#](~/_csharplang/spec/introduction.md).

Подробные сведения о выражении `new` с целевым типом см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы и выражения C#](index.md)
- [Инициализаторы объектов и коллекций](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
