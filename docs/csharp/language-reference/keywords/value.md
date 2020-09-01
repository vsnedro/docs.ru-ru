---
description: Справочник по C#. Контекстное ключевое слово value
title: Справочник по C#. Контекстное ключевое слово value
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: f72e9f097880d9de725a85a0973001baaefd9a9c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141742"
---
# <a name="value-c-reference"></a><span data-ttu-id="6560c-103">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6560c-103">value (C# Reference)</span></span>

<span data-ttu-id="6560c-104">Контекстное ключевое слово `value` используется в методе доступа `set` в объявлениях [свойства](../../programming-guide/classes-and-structs/properties.md) и [индексатора](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6560c-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="6560c-105">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="6560c-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="6560c-106">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству или индексатору.</span><span class="sxs-lookup"><span data-stu-id="6560c-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="6560c-107">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="6560c-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="6560c-108">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="6560c-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="6560c-109">Дополнительные сведения см. в статьях [Свойства](../../programming-guide/classes-and-structs/properties.md) и [Индексаторы](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6560c-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6560c-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6560c-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6560c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6560c-111">See also</span></span>

- [<span data-ttu-id="6560c-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6560c-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6560c-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6560c-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6560c-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6560c-114">C# Keywords</span></span>](index.md)
