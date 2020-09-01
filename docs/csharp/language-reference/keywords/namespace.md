---
description: Ключевое слово namespace. Справочник по C#
title: Ключевое слово namespace. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: a6cfd1c3d37cbdef1f0dd72ddca85ce91f2e183b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139584"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="3b2f1-103">namespace (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3b2f1-103">namespace (C# Reference)</span></span>

<span data-ttu-id="3b2f1-104">Ключевое слово `namespace` используется для объявления области действия, которая содержит набор связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-104">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="3b2f1-105">Пространство имен можно использовать для организации элементов кода и для создания глобально уникальных типов.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-105">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="3b2f1-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b2f1-106">Remarks</span></span>

<span data-ttu-id="3b2f1-107">В пространстве имен можно объявить ноль или больше следующих типов:</span><span class="sxs-lookup"><span data-stu-id="3b2f1-107">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="3b2f1-108">другое пространство имен</span><span class="sxs-lookup"><span data-stu-id="3b2f1-108">another namespace</span></span>

- [<span data-ttu-id="3b2f1-109">class</span><span class="sxs-lookup"><span data-stu-id="3b2f1-109">class</span></span>](class.md)

- [<span data-ttu-id="3b2f1-110">interface</span><span class="sxs-lookup"><span data-stu-id="3b2f1-110">interface</span></span>](interface.md)

- [<span data-ttu-id="3b2f1-111">struct</span><span class="sxs-lookup"><span data-stu-id="3b2f1-111">struct</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="3b2f1-112">enum</span><span class="sxs-lookup"><span data-stu-id="3b2f1-112">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="3b2f1-113">delegate</span><span class="sxs-lookup"><span data-stu-id="3b2f1-113">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="3b2f1-114">Независимо от того, было ли пространство имен объявлено явным образом в исходном файле на языке C#, компилятор добавляет пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="3b2f1-115">Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="3b2f1-116">Любой идентификатор в глобальном пространстве имен доступен для использования в именованном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="3b2f1-117">Пространства имен неявно имеют общий доступ, и это невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="3b2f1-118">Описание модификаторов доступа, которые можно назначить элементам в пространстве имен, см. в разделе [Модификаторы доступа](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="3b2f1-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="3b2f1-119">Пространство имен можно определить в двух или нескольких объявлениях.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="3b2f1-120">Например, в следующем примере два класса определяются в качестве части пространства имен `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="3b2f1-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="3b2f1-121">Пример</span><span class="sxs-lookup"><span data-stu-id="3b2f1-121">Example</span></span>

<span data-ttu-id="3b2f1-122">В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3b2f1-122">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="3b2f1-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3b2f1-123">C# language specification</span></span>

<span data-ttu-id="3b2f1-124">Дополнительные сведения см. в статье [Пространства имен](~/_csharplang/spec/namespaces.md) в разделе [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3b2f1-124">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b2f1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3b2f1-125">See also</span></span>

- [<span data-ttu-id="3b2f1-126">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3b2f1-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3b2f1-127">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="3b2f1-127">C# keywords</span></span>](index.md)
- [<span data-ttu-id="3b2f1-128">using</span><span class="sxs-lookup"><span data-stu-id="3b2f1-128">using</span></span>](using-directive.md)
- [<span data-ttu-id="3b2f1-129">using static</span><span class="sxs-lookup"><span data-stu-id="3b2f1-129">using static</span></span>](using-static.md)
- [<span data-ttu-id="3b2f1-130">Квалификатор псевдонима пространства имен `::`</span><span class="sxs-lookup"><span data-stu-id="3b2f1-130">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="3b2f1-131">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="3b2f1-131">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
