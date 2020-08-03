---
title: Руководство по программированию на C#. Вложенные типы
description: Тип, определенный внутри класса, структуры или интерфейса, называется в C# вложенным типом.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 9e1c6c1e8b22b5447d43915ab02984aa13146301
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864947"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="d1fc6-103">Вложенные типы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d1fc6-103">Nested Types (C# Programming Guide)</span></span>

<span data-ttu-id="d1fc6-104">Тип, определенный внутри [класса](../../language-reference/keywords/class.md), [структуры](../../language-reference/builtin-types/struct.md) или [интерфейса](../../language-reference/keywords/interface.md), называется вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-104">A type defined within a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) is called a nested type.</span></span> <span data-ttu-id="d1fc6-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d1fc6-105">For example</span></span>

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

<span data-ttu-id="d1fc6-106">Независимо от того, является ли внешний тип классом, интерфейсом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-106">Regardless of whether the outer type is a class, interface, or struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="d1fc6-107">В предыдущем примере класс `Nested` недоступен для внешних типов.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span>

<span data-ttu-id="d1fc6-108">Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="d1fc6-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="d1fc6-109">Вложенные типы **класса** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) или [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="d1fc6-109">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span>

   <span data-ttu-id="d1fc6-110">Тем не менее при определении вложенного класса `protected`, `protected internal` или `private protected` внутри [запечатанного класса](../../language-reference/keywords/sealed.md) возникает предупреждение компилятора [CS0628](../../misc/cs0628.md) "Новый защищенный член объявлен в запечатанном классе".</span><span class="sxs-lookup"><span data-stu-id="d1fc6-110">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="d1fc6-111">Вложенные типы **структуры** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) или [private](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="d1fc6-111">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>

<span data-ttu-id="d1fc6-112">В следующем примере класс `Nested` определяется как открытый:</span><span class="sxs-lookup"><span data-stu-id="d1fc6-112">The following example makes the `Nested` class public:</span></span>

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

<span data-ttu-id="d1fc6-113">Вложенный (внутренний) тип может получить доступ к вмещающему (внешнему) типу.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-113">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="d1fc6-114">Чтобы получить доступ к вмещающему типу, передайте его в качестве аргумента в конструктор вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-114">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="d1fc6-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="d1fc6-115">For example:</span></span>

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

<span data-ttu-id="d1fc6-116">Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-116">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="d1fc6-117">Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-117">It can access private and protected members of the containing type, including any inherited protected members.</span></span>

<span data-ttu-id="d1fc6-118">В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-118">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="d1fc6-119">Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="d1fc6-119">This is the name used to create a new instance of the nested class, as follows:</span></span>

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a><span data-ttu-id="d1fc6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d1fc6-120">See also</span></span>

- [<span data-ttu-id="d1fc6-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d1fc6-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d1fc6-122">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="d1fc6-122">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="d1fc6-123">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="d1fc6-123">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="d1fc6-124">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="d1fc6-124">Constructors</span></span>](./constructors.md)
