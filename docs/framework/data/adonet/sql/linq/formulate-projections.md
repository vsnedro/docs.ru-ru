---
title: Формулировка проекций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f0bc6dfcff7778ebc7156cbb039e13570c90467b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194405"
---
# <a name="formulate-projections"></a><span data-ttu-id="717ad-102">Формулировка проекций</span><span class="sxs-lookup"><span data-stu-id="717ad-102">Formulate Projections</span></span>

<span data-ttu-id="717ad-103">В следующих примерах показано, как `select` инструкция в C# и `Select` инструкции в Visual Basic можно сочетать с другими функциями для формирования проекций запросов.</span><span class="sxs-lookup"><span data-stu-id="717ad-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="717ad-104">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-104">Example</span></span>  

 <span data-ttu-id="717ad-105">В следующем примере `Select` предложение в Visual Basic ( `select` предложение в C#) используется для возврата последовательности имен контактов для `Customers` .</span><span class="sxs-lookup"><span data-stu-id="717ad-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="717ad-106">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-106">Example</span></span>  

 <span data-ttu-id="717ad-107">В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата последовательности имен контактов и телефонных номеров для `Customers` .</span><span class="sxs-lookup"><span data-stu-id="717ad-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="717ad-108">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-108">Example</span></span>  

 <span data-ttu-id="717ad-109">В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата последовательности имен и телефонных номеров сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="717ad-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="717ad-110">`FirstName`Поля и `LastName` объединяются в одно поле ( `Name` ), а `HomePhone` поле переименовывается в `Phone` результирующую последовательность.</span><span class="sxs-lookup"><span data-stu-id="717ad-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="717ad-111">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-111">Example</span></span>  

 <span data-ttu-id="717ad-112">В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата последовательности всех объектов `ProductID` и вычисляемого значения с именем `HalfPrice` .</span><span class="sxs-lookup"><span data-stu-id="717ad-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="717ad-113">В качестве значения устанавливается `UnitPrice`, разделенная на 2.</span><span class="sxs-lookup"><span data-stu-id="717ad-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="717ad-114">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-114">Example</span></span>  

 <span data-ttu-id="717ad-115">В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *Условный оператор* для возврата последовательности названия продукта и доступности продукта.</span><span class="sxs-lookup"><span data-stu-id="717ad-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="717ad-116">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-116">Example</span></span>  

 <span data-ttu-id="717ad-117">В следующем примере используется предложение Visual Basic `Select` ( `select` предложение в C#) и *известный тип* (Name) для возврата последовательности имен сотрудников.</span><span class="sxs-lookup"><span data-stu-id="717ad-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="717ad-118">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-118">Example</span></span>  

 <span data-ttu-id="717ad-119">В следующем примере с помощью `Select` и `Where` в Visual Basic ( `select` и `where` в C#) возвращается *отфильтрованная последовательность* имен контактов для клиентов в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="717ad-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="717ad-120">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-120">Example</span></span>  

 <span data-ttu-id="717ad-121">В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата в *форме подмножества* данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="717ad-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="717ad-122">Пример</span><span class="sxs-lookup"><span data-stu-id="717ad-122">Example</span></span>  

 <span data-ttu-id="717ad-123">В следующем примере вложенные запросы используется для возврата следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="717ad-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="717ad-124">Последовательность всех заказов и их соответствующие `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="717ad-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="717ad-125">Последовательность элементов, упорядоченных по наличию скидки.</span><span class="sxs-lookup"><span data-stu-id="717ad-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="717ad-126">Количество сэкономленных средств при отсутствии расходов на доставку.</span><span class="sxs-lookup"><span data-stu-id="717ad-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="717ad-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="717ad-127">See also</span></span>

- [<span data-ttu-id="717ad-128">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="717ad-128">Query Examples</span></span>](query-examples.md)
