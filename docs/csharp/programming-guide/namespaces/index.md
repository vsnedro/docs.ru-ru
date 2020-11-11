---
title: Руководство по программированию на C#. Пространства имен
description: Сведения о работе с пространствами имен при программировании на C#. В этой статье приводятся общие сведения о свойствах пространств имен, а также ссылки на дополнительные ресурсы.
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 41a666fd5f368e6990e08a36700e18f648939213
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440345"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="8fb42-104">Пространства имен (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="8fb42-104">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="8fb42-105">Пространства имен часто используются в программировании на C# двумя способами.</span><span class="sxs-lookup"><span data-stu-id="8fb42-105">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="8fb42-106">Первый способ — .NET использует пространства имен для упорядочения множества ее классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8fb42-106">First, .NET uses namespaces to organize its many classes, as follows:</span></span>  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<span data-ttu-id="8fb42-107"><xref:System> является пространством имен, а <xref:System.Console> — это класс в нем.</span><span class="sxs-lookup"><span data-stu-id="8fb42-107"><xref:System> is a namespace and <xref:System.Console> is a class in that namespace.</span></span> <span data-ttu-id="8fb42-108">Можно использовать ключевое слово `using`, и тогда полное имя не потребуется. См. следующий пример:</span><span class="sxs-lookup"><span data-stu-id="8fb42-108">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="8fb42-109">См. дополнительные сведения о [директиве using](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="8fb42-109">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>

<span data-ttu-id="8fb42-110">Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах.</span><span class="sxs-lookup"><span data-stu-id="8fb42-110">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="8fb42-111">Используйте ключевое слово [namespace](../../language-reference/keywords/namespace.md), чтобы объявить пространство имен, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8fb42-111">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="8fb42-112">Имя пространства имен должно быть допустимым [именем идентификатора](../inside-a-program/identifier-names.md) C#.</span><span class="sxs-lookup"><span data-stu-id="8fb42-112">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="8fb42-113">Обзор пространств имен</span><span class="sxs-lookup"><span data-stu-id="8fb42-113">Namespaces overview</span></span>

<span data-ttu-id="8fb42-114">Пространства имен имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="8fb42-114">Namespaces have the following properties:</span></span>

- <span data-ttu-id="8fb42-115">Они помогают упорядочивать проекты с большим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="8fb42-115">They organize large code projects.</span></span>
- <span data-ttu-id="8fb42-116">Они разделяются оператором `.`.</span><span class="sxs-lookup"><span data-stu-id="8fb42-116">They are delimited by using the `.` operator.</span></span>
- <span data-ttu-id="8fb42-117">Директива `using` позволяет не указывать название пространства имен для каждого класса.</span><span class="sxs-lookup"><span data-stu-id="8fb42-117">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>
- <span data-ttu-id="8fb42-118">Пространство имен `global` является корневым: `global::System` всегда будет ссылаться на пространство имен <xref:System> в .NET.</span><span class="sxs-lookup"><span data-stu-id="8fb42-118">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8fb42-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8fb42-119">C# language specification</span></span>

<span data-ttu-id="8fb42-120">Дополнительные сведения см. в статье [Пространства имен](~/_csharplang/spec/namespaces.md) в разделе [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8fb42-120">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8fb42-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8fb42-121">See also</span></span>

- [<span data-ttu-id="8fb42-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8fb42-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8fb42-123">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="8fb42-123">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="8fb42-124">Практическое руководство. Использование пространства имен My</span><span class="sxs-lookup"><span data-stu-id="8fb42-124">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="8fb42-125">Имена идентификаторов</span><span class="sxs-lookup"><span data-stu-id="8fb42-125">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="8fb42-126">Директива using</span><span class="sxs-lookup"><span data-stu-id="8fb42-126">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="8fb42-127">:: Оператор</span><span class="sxs-lookup"><span data-stu-id="8fb42-127">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
