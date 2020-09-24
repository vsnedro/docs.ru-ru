---
title: Неподдерживаемые функциональные возможности
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164159"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="76df9-102">Неподдерживаемые функциональные возможности</span><span class="sxs-lookup"><span data-stu-id="76df9-102">Unsupported Functionality</span></span>

<span data-ttu-id="76df9-103">В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76df9-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="76df9-104">Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="76df9-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="76df9-105">Для получения дополнительной информации см. <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76df9-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="76df9-106">В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="76df9-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="76df9-107">Аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="76df9-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="76df9-108">В LINQ to SQL реализована ограниченная поддержка функции `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="76df9-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="76df9-109">Дополнительные сведения см. в разделе [методы System. Math](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="76df9-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76df9-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="76df9-110">See also</span></span>

- [<span data-ttu-id="76df9-111">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="76df9-111">Data Types and Functions</span></span>](data-types-and-functions.md)
