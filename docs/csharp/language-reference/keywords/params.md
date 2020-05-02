---
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
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738844"
---
# <a name="params-c-reference"></a><span data-ttu-id="0aa3c-102">params (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0aa3c-102">params (C# Reference)</span></span>

<span data-ttu-id="0aa3c-103">С помощью ключевого слова `params` можно указать [параметр метода](method-parameters.md), принимающий переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="0aa3c-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="0aa3c-104">Тип параметра должен быть одномерным массивом.</span><span class="sxs-lookup"><span data-stu-id="0aa3c-104">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="0aa3c-105">В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.</span><span class="sxs-lookup"><span data-stu-id="0aa3c-105">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="0aa3c-106">Если объявленный тип параметра `params` не является одномерным массивом, возникает ошибка компилятора [CS0225](../../misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="0aa3c-106">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="0aa3c-107">При вызове метода с параметром `params` можно передать следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="0aa3c-107">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="0aa3c-108">разделенный запятыми список аргументов типа элементов массива;</span><span class="sxs-lookup"><span data-stu-id="0aa3c-108">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="0aa3c-109">массив аргументов указанного типа;</span><span class="sxs-lookup"><span data-stu-id="0aa3c-109">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="0aa3c-110">не передавать аргументы.</span><span class="sxs-lookup"><span data-stu-id="0aa3c-110">No arguments.</span></span> <span data-ttu-id="0aa3c-111">Если аргументы не отправляются, длина списка `params` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="0aa3c-111">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="0aa3c-112">Пример</span><span class="sxs-lookup"><span data-stu-id="0aa3c-112">Example</span></span>

<span data-ttu-id="0aa3c-113">В следующем примере показаны различные способы оправки аргументов параметру `params`.</span><span class="sxs-lookup"><span data-stu-id="0aa3c-113">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="0aa3c-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0aa3c-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0aa3c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0aa3c-115">See also</span></span>

- [<span data-ttu-id="0aa3c-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0aa3c-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0aa3c-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0aa3c-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0aa3c-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0aa3c-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0aa3c-119">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="0aa3c-119">Method Parameters</span></span>](method-parameters.md)
