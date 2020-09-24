---
description: Справочник по C#. Контекстное ключевое слово value
title: Справочник по C#. Контекстное ключевое слово value
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ad2eb6f12d8c295dc5203994d6c570cd2377e3ee
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828920"
---
# <a name="value-c-reference"></a><span data-ttu-id="05f60-103">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="05f60-103">value (C# Reference)</span></span>

<span data-ttu-id="05f60-104">Контекстное ключевое слово `value` используется в методе доступа `set` в объявлениях [свойства](../../programming-guide/classes-and-structs/properties.md) и [индексатора](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="05f60-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="05f60-105">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="05f60-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="05f60-106">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству или индексатору.</span><span class="sxs-lookup"><span data-stu-id="05f60-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="05f60-107">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="05f60-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="05f60-108">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="05f60-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="05f60-109">Дополнительные сведения см. в статьях [Свойства](../../programming-guide/classes-and-structs/properties.md) и [Индексаторы](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="05f60-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexers](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="05f60-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="05f60-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="05f60-111">См. также</span><span class="sxs-lookup"><span data-stu-id="05f60-111">See also</span></span>

- [<span data-ttu-id="05f60-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="05f60-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="05f60-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="05f60-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="05f60-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="05f60-114">C# Keywords</span></span>](index.md)
