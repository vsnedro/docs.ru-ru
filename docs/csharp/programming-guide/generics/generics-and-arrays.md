---
title: Руководство по программированию на C#. Универсальные шаблоны и массивы
description: Сведения об использовании универсальных шаблонов и массивов при программировании на C#. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: f3d9e9e0c84d954278780e7598545f80aea0e58c
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299049"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="2444f-104">Универсальные методы и массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2444f-104">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="2444f-105">В C# 2.0 и более поздних версиях одномерные массивы с нулевой нижней границей автоматически реализуют <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="2444f-105">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="2444f-106">Это позволяет создавать универсальные методы, которые могут использовать один и тот же код для выполнения итераций в массивах и других типах коллекций.</span><span class="sxs-lookup"><span data-stu-id="2444f-106">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="2444f-107">Этот способ используется преимущественно для чтения данных в коллекциях.</span><span class="sxs-lookup"><span data-stu-id="2444f-107">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="2444f-108">Интерфейс <xref:System.Collections.Generic.IList%601> нельзя использовать для добавления или удаления элементов массива.</span><span class="sxs-lookup"><span data-stu-id="2444f-108">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="2444f-109">При попытке вызвать метод <xref:System.Collections.Generic.IList%601>, например <xref:System.Collections.Generic.IList%601.RemoveAt%2A>, для массива в этом контексте возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="2444f-109">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="2444f-110">В следующем примере кода показано, как отдельный универсальный метод, принимающий входной параметр <xref:System.Collections.Generic.IList%601>, можно использовать для выполнения итераций в списке и массиве (в данном случае в массиве целых чисел).</span><span class="sxs-lookup"><span data-stu-id="2444f-110">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="2444f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2444f-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="2444f-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2444f-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2444f-113">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="2444f-113">Generics</span></span>](./index.md)
- [<span data-ttu-id="2444f-114">Массивы</span><span class="sxs-lookup"><span data-stu-id="2444f-114">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="2444f-115">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="2444f-115">Generics</span></span>](../../../standard/generics/index.md)
