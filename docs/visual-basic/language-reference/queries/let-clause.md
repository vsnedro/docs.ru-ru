---
title: Предложение Let
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: a6ff3fc80a2b6752c61a8b8f7d4ce62b5a46baad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869878"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="fd0cc-102">Предложение Let (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd0cc-102">Let Clause (Visual Basic)</span></span>

<span data-ttu-id="fd0cc-103">Выполняет вычисление значения и присваивает его новой переменной в запросе.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd0cc-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="fd0cc-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="fd0cc-105">Parts</span></span>  
  
|<span data-ttu-id="fd0cc-106">Термин</span><span class="sxs-lookup"><span data-stu-id="fd0cc-106">Term</span></span>|<span data-ttu-id="fd0cc-107">Определение</span><span class="sxs-lookup"><span data-stu-id="fd0cc-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="fd0cc-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-108">Required.</span></span> <span data-ttu-id="fd0cc-109">Псевдоним, который может использоваться для ссылки на результаты предоставляемого выражения.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="fd0cc-110">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-110">Required.</span></span> <span data-ttu-id="fd0cc-111">Выражение, которое будет вычислено и назначено указанной переменной.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0cc-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="fd0cc-112">Remarks</span></span>  

 <span data-ttu-id="fd0cc-113">`Let`Предложение позволяет вычислять значения для каждого результата запроса и ссылаться на них с помощью псевдонима.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="fd0cc-114">Псевдоним можно использовать в других предложениях, например в `Where` предложении.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="fd0cc-115">`Let`Предложение позволяет создать инструкцию запроса, которая будет проще читать, поскольку можно указать псевдоним для предложения выражения, включенного в запрос, и заменить псевдоним при каждом использовании предложения Expression.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="fd0cc-116">В предложение можно включить любое количество `variable` `expression` назначений и `Let` .</span><span class="sxs-lookup"><span data-stu-id="fd0cc-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="fd0cc-117">Разделяйте каждое назначение запятой (,).</span><span class="sxs-lookup"><span data-stu-id="fd0cc-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd0cc-118">Пример</span><span class="sxs-lookup"><span data-stu-id="fd0cc-118">Example</span></span>  

 <span data-ttu-id="fd0cc-119">В следующем примере кода предложение используется `Let` для расчета скидки на 10% для продуктов.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="fd0cc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fd0cc-120">See also</span></span>

- <span data-ttu-id="fd0cc-121">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd0cc-121">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="fd0cc-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="fd0cc-122">Queries</span></span>](index.md)
- [<span data-ttu-id="fd0cc-123">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="fd0cc-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="fd0cc-124">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="fd0cc-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="fd0cc-125">Предложение WHERE</span><span class="sxs-lookup"><span data-stu-id="fd0cc-125">Where Clause</span></span>](where-clause.md)
