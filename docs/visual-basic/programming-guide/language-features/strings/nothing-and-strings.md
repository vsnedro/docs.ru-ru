---
title: Nothing и строки
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 392de45b0ee1688224f3e8170b0144f1acdb0912
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360570"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="3283f-102">Nothing и строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3283f-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="3283f-103">Среда выполнения Visual Basic и .NET Framework оцениваются по- `Nothing` разному, когда речь идет о строках.</span><span class="sxs-lookup"><span data-stu-id="3283f-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="3283f-104">Среда выполнения Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3283f-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="3283f-105">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="3283f-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="3283f-106">Среда выполнения Visual Basic обычно вычисляется `Nothing` как пустая строка ("").</span><span class="sxs-lookup"><span data-stu-id="3283f-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="3283f-107">Однако .NET Framework не создает исключение, когда выполняется попытка выполнить операцию со строкой `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="3283f-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3283f-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3283f-108">See also</span></span>

- [<span data-ttu-id="3283f-109">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3283f-109">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
