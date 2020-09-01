---
description: Справочник по C#. Ключевое слово params для массивов параметров
title: Справочник по C#. Ключевое слово params для массивов параметров
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134475"
---
# <a name="params-c-reference"></a><span data-ttu-id="5a282-103">params (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5a282-103">params (C# Reference)</span></span>

<span data-ttu-id="5a282-104">С помощью ключевого слова `params` можно указать [параметр метода](method-parameters.md), принимающий переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="5a282-104">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="5a282-105">Тип параметра должен быть одномерным массивом.</span><span class="sxs-lookup"><span data-stu-id="5a282-105">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="5a282-106">В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.</span><span class="sxs-lookup"><span data-stu-id="5a282-106">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="5a282-107">Если объявленный тип параметра `params` не является одномерным массивом, возникает ошибка компилятора [CS0225](../../misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="5a282-107">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="5a282-108">При вызове метода с параметром `params` можно передать следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="5a282-108">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="5a282-109">разделенный запятыми список аргументов типа элементов массива;</span><span class="sxs-lookup"><span data-stu-id="5a282-109">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="5a282-110">массив аргументов указанного типа;</span><span class="sxs-lookup"><span data-stu-id="5a282-110">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="5a282-111">не передавать аргументы.</span><span class="sxs-lookup"><span data-stu-id="5a282-111">No arguments.</span></span> <span data-ttu-id="5a282-112">Если аргументы не отправляются, длина списка `params` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="5a282-112">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="5a282-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5a282-113">Example</span></span>

<span data-ttu-id="5a282-114">В следующем примере показаны различные способы оправки аргументов параметру `params`.</span><span class="sxs-lookup"><span data-stu-id="5a282-114">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="5a282-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5a282-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5a282-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5a282-116">See also</span></span>

- [<span data-ttu-id="5a282-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5a282-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5a282-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5a282-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5a282-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="5a282-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5a282-120">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="5a282-120">Method Parameters</span></span>](method-parameters.md)
