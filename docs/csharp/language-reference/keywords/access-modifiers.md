---
description: Справочник по C#. Модификаторы доступа
title: Справочник по C#. Модификаторы доступа
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 2ea7a65c23b6a1edee572f6f6ff6c52d14358408
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127156"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="16c60-103">Модификаторы доступа (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="16c60-103">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="16c60-104">Модификаторы доступа — это ключевые слова, которые задают объявленный уровень доступности члена или типа.</span><span class="sxs-lookup"><span data-stu-id="16c60-104">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="16c60-105">В этом разделе описываются четыре модификатора доступа:</span><span class="sxs-lookup"><span data-stu-id="16c60-105">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="16c60-106">С помощью этих модификаторов можно задать следующие шесть уровней доступа:</span><span class="sxs-lookup"><span data-stu-id="16c60-106">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="16c60-107">[`public`](public.md): Неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="16c60-107">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="16c60-108">[`protected`](protected.md): Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="16c60-108">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="16c60-109">[`internal`](internal.md): Доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="16c60-109">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="16c60-110">[`protected internal`](protected-internal.md): Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="16c60-110">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="16c60-111">[`private`](private.md): Доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="16c60-111">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="16c60-112">[`private protected`](private-protected.md): Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса в текущей сборке.</span><span class="sxs-lookup"><span data-stu-id="16c60-112">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="16c60-113">В этом разделе также представлена следующая информация:</span><span class="sxs-lookup"><span data-stu-id="16c60-113">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="16c60-114">[Уровни доступности](./accessibility-levels.md): с помощью четырех модификаторов доступа можно объявить шесть уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="16c60-114">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="16c60-115">[Домен доступности](./accessibility-domain.md): определяет, в каких разделах программы может присутствовать ссылка на этот член.</span><span class="sxs-lookup"><span data-stu-id="16c60-115">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="16c60-116">[Ограничения на использование уровней доступности](./restrictions-on-using-accessibility-levels.md): общие сведения об ограничениях на использование объявленных уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="16c60-116">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c60-117">См. также</span><span class="sxs-lookup"><span data-stu-id="16c60-117">See also</span></span>

- [<span data-ttu-id="16c60-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="16c60-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="16c60-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="16c60-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="16c60-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="16c60-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="16c60-121">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="16c60-121">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="16c60-122">Ключевые слова доступа</span><span class="sxs-lookup"><span data-stu-id="16c60-122">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="16c60-123">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="16c60-123">Modifiers</span></span>](index.md)
