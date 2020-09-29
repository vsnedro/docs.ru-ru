---
title: Руководство по программированию на C#. Сравнение свойств и индексаторов
description: Определите, в чем индексаторы в C# подобны свойствам. К методам доступа индексаторов применяются правила, которые определены для методов доступа к свойствам, за исключением некоторых различий.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: fff20ca965e7614d26f7da32321a829d13292389
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192533"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="57852-104">Сравнение свойств и индексаторов (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="57852-104">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="57852-105">Индексаторы подобны свойствам.</span><span class="sxs-lookup"><span data-stu-id="57852-105">Indexers are like properties.</span></span> <span data-ttu-id="57852-106">К методам доступа индексаторов применяются те же правила, которые определены для методов доступа к свойствам, за исключением различий, показанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="57852-106">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="57852-107">Свойство.</span><span class="sxs-lookup"><span data-stu-id="57852-107">Property</span></span>|<span data-ttu-id="57852-108">Индексатор</span><span class="sxs-lookup"><span data-stu-id="57852-108">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="57852-109">Позволяет вызывать методы как открытые члены данных.</span><span class="sxs-lookup"><span data-stu-id="57852-109">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="57852-110">Обеспечивает доступ к элементам внутренней коллекции объекта с использованием нотации массива для самого объекта.</span><span class="sxs-lookup"><span data-stu-id="57852-110">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="57852-111">Доступ по простому имени.</span><span class="sxs-lookup"><span data-stu-id="57852-111">Accessed through a simple name.</span></span>|<span data-ttu-id="57852-112">Доступ посредством индекса.</span><span class="sxs-lookup"><span data-stu-id="57852-112">Accessed through an index.</span></span>|  
|<span data-ttu-id="57852-113">Может быть статическим членом или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="57852-113">Can be a static or an instance member.</span></span>|<span data-ttu-id="57852-114">Должен быть членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="57852-114">Must be an instance member.</span></span>|  
|<span data-ttu-id="57852-115">Метод доступа [get](../../language-reference/keywords/get.md) свойства не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="57852-115">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="57852-116">Метод доступа `get` индексатора имеет тот же список формальных параметров, что и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="57852-116">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="57852-117">Метод доступа [set](../../language-reference/keywords/set.md) свойства содержит неявный параметр `value`.</span><span class="sxs-lookup"><span data-stu-id="57852-117">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="57852-118">Метод доступа `set` индексатора имеет тот же список формальных параметров, что и сам индексатор, и также должен содержать параметр [value](../../language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="57852-118">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="57852-119">Поддерживает сокращенный синтаксис с использованием [автоматически реализуемых свойств](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="57852-119">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="57852-120">Поддерживает элементы в виде выражения для индексаторов только для получения.</span><span class="sxs-lookup"><span data-stu-id="57852-120">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57852-121">См. также</span><span class="sxs-lookup"><span data-stu-id="57852-121">See also</span></span>

- [<span data-ttu-id="57852-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="57852-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="57852-123">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="57852-123">Indexers</span></span>](./index.md)
- [<span data-ttu-id="57852-124">Свойства</span><span class="sxs-lookup"><span data-stu-id="57852-124">Properties</span></span>](../classes-and-structs/properties.md)
