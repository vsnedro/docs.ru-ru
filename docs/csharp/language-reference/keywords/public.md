---
description: Справочник по C#. Ключевое слово public
title: Справочник по C#. Ключевое слово public
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 90c1d2a1d9efcdf57f914f4318bf7a743d3f37ec
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938472"
---
# <a name="public-c-reference"></a>public (справочник по C#)

Ключевое слово `public` является модификатором доступа для типов и членов типов. Общий доступ является уровнем доступа с максимальными правами. Ограничений доступа к общим членам не существует, как показано в следующем примере:

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

Дополнительные сведения см. в разделах [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](accessibility-levels.md).

## <a name="example"></a>Пример

В следующем примере объявляются два класса: `PointTest` и `Program`. Доступ к открытым членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `Program`.

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

Если уровень доступа `public` изменить на [private](private.md) или [protected](protected.md), будет выводится следующее сообщение об ошибке:

"PointTest.y" недоступен из-за его уровня защиты.

## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы доступа](access-modifiers.md)
- [Уровни доступности](accessibility-levels.md)
- [Модификаторы](index.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)
