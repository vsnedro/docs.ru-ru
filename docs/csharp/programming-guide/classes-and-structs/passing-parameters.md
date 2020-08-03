---
title: Руководство по программированию на C#. Передача параметров
description: В C# аргументы могут передаваться параметрам по значению или по ссылке. Изменения в аргументе, переданном по ссылке, сохраняются. Для передачи параметра по ссылке используйте ключевые слова ref или out.
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 875a42aacf3d7aa4124684aefafdcb07ff4c87d6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864739"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="0e23d-105">Передача параметров (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="0e23d-105">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="0e23d-106">В C# аргументы могут передаваться параметрам либо по значению, либо по ссылке.</span><span class="sxs-lookup"><span data-stu-id="0e23d-106">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="0e23d-107">Передача по ссылке позволяет изменять и сохранять измененные значения параметров членов функций, методов, свойств, индексаторов, операторов и конструкторов в вызывающей среде.</span><span class="sxs-lookup"><span data-stu-id="0e23d-107">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="0e23d-108">Чтобы передать параметр по ссылке, намереваясь изменить значение, используйте ключевое слово `ref` или `out`.</span><span class="sxs-lookup"><span data-stu-id="0e23d-108">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="0e23d-109">Чтобы передать по ссылке, намереваясь предотвратить копирование, но не изменение значения, используйте модификатор `in`.</span><span class="sxs-lookup"><span data-stu-id="0e23d-109">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="0e23d-110">Для простоты в этих примерах используется только ключевое слово `ref`.</span><span class="sxs-lookup"><span data-stu-id="0e23d-110">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="0e23d-111">Дополнительные сведения о различиях между ключевыми словами `in`, `ref` и `out` см. в разделах [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="0e23d-111">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="0e23d-112">В приведенном ниже примере показано различие между параметрами-значениями и ссылочными параметрами.</span><span class="sxs-lookup"><span data-stu-id="0e23d-112">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="0e23d-113">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="0e23d-113">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="0e23d-114">Передача параметров типа значения</span><span class="sxs-lookup"><span data-stu-id="0e23d-114">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="0e23d-115">Передача параметров ссылочного типа</span><span class="sxs-lookup"><span data-stu-id="0e23d-115">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="0e23d-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0e23d-116">C# Language Specification</span></span>  

<span data-ttu-id="0e23d-117">Дополнительные сведения см. в разделе [Список аргументов](~/_csharplang/spec/expressions.md#argument-lists) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="0e23d-117">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="0e23d-118">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="0e23d-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e23d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0e23d-119">See also</span></span>

- [<span data-ttu-id="0e23d-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0e23d-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0e23d-121">Методы</span><span class="sxs-lookup"><span data-stu-id="0e23d-121">Methods</span></span>](./methods.md)
