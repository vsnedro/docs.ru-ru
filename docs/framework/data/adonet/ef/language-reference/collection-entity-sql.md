---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: c960ee69f8188f6dd3184b6fb31f3432f8d58fee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197954"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="c2be0-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c2be0-102">COLLECTION (Entity SQL)</span></span>

<span data-ttu-id="c2be0-103">Ключевое слово COLLECTION используется только в определении встроенной функции.</span><span class="sxs-lookup"><span data-stu-id="c2be0-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="c2be0-104">Функции коллекций — это функции, которые работают с коллекциями значений и возвращают скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="c2be0-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2be0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2be0-105">Syntax</span></span>  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a><span data-ttu-id="c2be0-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c2be0-106">Arguments</span></span>  

 `type_definition`  
 <span data-ttu-id="c2be0-107">Выражение, возвращающее коллекцию поддерживаемых типов, строк или ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2be0-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2be0-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2be0-108">Remarks</span></span>  

 <span data-ttu-id="c2be0-109">Дополнительные сведения о ключевом слове COLLECTION см. в статье [Type Definitions](type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c2be0-109">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2be0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="c2be0-110">Example</span></span>  

 <span data-ttu-id="c2be0-111">Следующий образец иллюстрирует использование ключевого слова COLLECTION для объявления коллекции десятичных чисел в качестве аргумента для встроенной функции запроса.</span><span class="sxs-lookup"><span data-stu-id="c2be0-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="c2be0-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c2be0-112">See also</span></span>

- [<span data-ttu-id="c2be0-113">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c2be0-113">Entity SQL Reference</span></span>](entity-sql-reference.md)
