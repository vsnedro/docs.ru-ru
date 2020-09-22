---
title: Предложение Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 49eaab2e6a8c48d61518ea51ef2f644b6eb48314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875284"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="2f938-102">Предложение Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f938-102">Distinct Clause (Visual Basic)</span></span>

<span data-ttu-id="2f938-103">Ограничивают значения текущей переменной диапазона, чтобы исключить дублирующиеся значения в последующих предложениях запроса.</span><span class="sxs-lookup"><span data-stu-id="2f938-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f938-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f938-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="2f938-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f938-105">Remarks</span></span>  

 <span data-ttu-id="2f938-106">`Distinct`Для получения списка уникальных элементов можно использовать предложение.</span><span class="sxs-lookup"><span data-stu-id="2f938-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="2f938-107">`Distinct`Предложение приводит к тому, что запрос пропускает дублирующиеся результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="2f938-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="2f938-108">`Distinct`Предложение применяется к повторяющимися значениям для всех полей возврата, указанных в `Select` предложении.</span><span class="sxs-lookup"><span data-stu-id="2f938-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="2f938-109">Если `Select` предложение не указано, `Distinct` предложение применяется к переменной диапазона для запроса, указанного в `From` предложении.</span><span class="sxs-lookup"><span data-stu-id="2f938-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="2f938-110">Если переменная диапазона не является неизменяемым типом, запрос будет игнорировать только результат запроса, если все элементы типа соответствуют существующему результату запроса.</span><span class="sxs-lookup"><span data-stu-id="2f938-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f938-111">Пример</span><span class="sxs-lookup"><span data-stu-id="2f938-111">Example</span></span>  

 <span data-ttu-id="2f938-112">Следующее выражение запроса соединяет список клиентов и список заказов клиентов.</span><span class="sxs-lookup"><span data-stu-id="2f938-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="2f938-113">`Distinct`Предложение включается для возврата списка уникальных имен клиентов и дат заказов.</span><span class="sxs-lookup"><span data-stu-id="2f938-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="2f938-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2f938-114">See also</span></span>

- <span data-ttu-id="2f938-115">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f938-115">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="2f938-116">Запросы</span><span class="sxs-lookup"><span data-stu-id="2f938-116">Queries</span></span>](index.md)
- [<span data-ttu-id="2f938-117">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="2f938-117">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="2f938-118">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="2f938-118">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="2f938-119">Предложение WHERE</span><span class="sxs-lookup"><span data-stu-id="2f938-119">Where Clause</span></span>](where-clause.md)
