---
title: Руководство по программированию на C#. Явная реализация элементов двух интерфейсов
description: Узнайте, как явно реализовать два интерфейса с одинаковыми именами членов и присвоить каждому члену интерфейса отдельную реализацию в этом примере C#.
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: d60ec43f734d5e8bfa7f467874440bd3514877fe
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303066"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="e25b0-103">Руководство по программированию на C#. Явная реализация элементов двух интерфейсов</span><span class="sxs-lookup"><span data-stu-id="e25b0-103">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="e25b0-104">Явная реализация [интерфейсов](../../language-reference/keywords/interface.md) позволяет разработчику реализовать два интерфейса с одинаковыми именами членов и создать отдельные реализации каждого члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e25b0-104">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="e25b0-105">В этом примере размеры поля выводятся в метрической и английской системе мер.</span><span class="sxs-lookup"><span data-stu-id="e25b0-105">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="e25b0-106">[Класс](../../language-reference/keywords/class.md) Box реализует два интерфейса (IEnglishDimensions и IMetricDimensions), представляющие соответствующие системы мер.</span><span class="sxs-lookup"><span data-stu-id="e25b0-106">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="e25b0-107">В обоих интерфейсах представлены члены с одинаковыми именами: Length и Width.</span><span class="sxs-lookup"><span data-stu-id="e25b0-107">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25b0-108">Пример</span><span class="sxs-lookup"><span data-stu-id="e25b0-108">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e25b0-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e25b0-109">Robust Programming</span></span>  
 <span data-ttu-id="e25b0-110">Если требуется использовать единицы английской системы мер по умолчанию, реализуйте методы Length и Width обычным способом, после чего явно реализуйте методы Length и Width из интерфейса IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="e25b0-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="e25b0-111">В этом случае единицы английской системы мер будут доступны из экземпляра класса, а метрические единицы — из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="e25b0-111">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e25b0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e25b0-112">See also</span></span>

- [<span data-ttu-id="e25b0-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e25b0-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e25b0-114">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="e25b0-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="e25b0-115">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e25b0-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="e25b0-116">Практическое руководство. Явная реализация членов интерфейса</span><span class="sxs-lookup"><span data-stu-id="e25b0-116">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
