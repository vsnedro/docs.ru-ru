---
title: + (Объединение строк) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 92591448a3707ba11ad2462161050e48e0398728
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173631"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="b20ef-102">+ (объединение строк) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b20ef-102">+ (String Concatenation) (Entity SQL)</span></span>

<span data-ttu-id="b20ef-103">Объединяет две строки.</span><span class="sxs-lookup"><span data-stu-id="b20ef-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b20ef-104">Syntax</span></span>  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b20ef-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b20ef-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="b20ef-106">Любое допустимое выражение с типом данных EDM.String.</span><span class="sxs-lookup"><span data-stu-id="b20ef-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="b20ef-107">Оба выражения должны иметь одинаковый тип данных, или одно из выражений должно допускать неявное преобразование к типу данных другого выражения.</span><span class="sxs-lookup"><span data-stu-id="b20ef-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b20ef-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="b20ef-108">Result Types</span></span>  

 <span data-ttu-id="b20ef-109">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="b20ef-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="b20ef-110">Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b20ef-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20ef-111">Пример</span><span class="sxs-lookup"><span data-stu-id="b20ef-111">Example</span></span>  

 <span data-ttu-id="b20ef-112">В следующем запросе Entity SQL с помощью оператора «+» объединяются две строки.</span><span class="sxs-lookup"><span data-stu-id="b20ef-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="b20ef-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b20ef-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b20ef-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="b20ef-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b20ef-115">Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b20ef-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="b20ef-116">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b20ef-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="b20ef-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b20ef-117">See also</span></span>

- [<span data-ttu-id="b20ef-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b20ef-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b20ef-119">Типы концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="b20ef-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
