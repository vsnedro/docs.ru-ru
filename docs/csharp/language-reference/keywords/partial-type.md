---
description: Разделяемый тип. Справочник по C#
title: Разделяемый тип. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 8ae98805eea7231e3a15cb74e636313e796796a2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89117991"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="ff196-103">разделяемый тип (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ff196-103">partial type (C# Reference)</span></span>

<span data-ttu-id="ff196-104">Определения разделяемых типов позволяют разделять определения классов, структур и интерфейсов на несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="ff196-104">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="ff196-105">В файле *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="ff196-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="ff196-106">Объявление в файле *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="ff196-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="ff196-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff196-107">Remarks</span></span>

<span data-ttu-id="ff196-108">Разделение типа класса, структуры или интерфейса на несколько файлов может пригодиться при работе с крупными проектами или с автоматически созданным кодом, например предоставляемым [конструктором Windows Forms](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ff196-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="ff196-109">Разделяемый тип может содержать [разделяемый метод](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="ff196-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="ff196-110">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ff196-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ff196-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ff196-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ff196-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ff196-112">See also</span></span>

- [<span data-ttu-id="ff196-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ff196-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ff196-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ff196-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ff196-115">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="ff196-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="ff196-116">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="ff196-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
