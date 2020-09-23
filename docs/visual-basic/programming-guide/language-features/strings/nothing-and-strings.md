---
title: Nothing и строки
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d4c7ee6d13334617a80abb845af52bf388a12797
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072526"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="b0774-102">Nothing и строки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b0774-102">Nothing and Strings in Visual Basic</span></span>

<span data-ttu-id="b0774-103">Среда выполнения Visual Basic и .NET Framework оцениваются по- `Nothing` разному, когда речь идет о строках.</span><span class="sxs-lookup"><span data-stu-id="b0774-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="b0774-104">Среда выполнения Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b0774-104">Visual Basic Runtime and the .NET Framework</span></span>  

 <span data-ttu-id="b0774-105">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="b0774-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="b0774-106">Среда выполнения Visual Basic обычно вычисляется `Nothing` как пустая строка ("").</span><span class="sxs-lookup"><span data-stu-id="b0774-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="b0774-107">Однако .NET Framework не создает исключение, когда выполняется попытка выполнить операцию со строкой `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="b0774-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0774-108">См. также</span><span class="sxs-lookup"><span data-stu-id="b0774-108">See also</span></span>

- [<span data-ttu-id="b0774-109">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b0774-109">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
