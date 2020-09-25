---
title: Практическое руководство. Как прямо выполнять запросы SQL
description: Узнайте, как использовать ExecuteQuery для выполнения запроса и последующего преобразования результатов непосредственно в объекты в случаях, когда LINQ to SQL запрос недостаточен.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 7ebd02581d789266396b58296bbd6ad312dd468e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200580"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="b7a31-103">Практическое руководство. Как прямо выполнять запросы SQL</span><span class="sxs-lookup"><span data-stu-id="b7a31-103">How to: Directly Execute SQL Queries</span></span>

<span data-ttu-id="b7a31-104">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в параметризованные запросы SQL (в текстовой форме) и отправляет их на сервер SQL для обработки.</span><span class="sxs-lookup"><span data-stu-id="b7a31-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="b7a31-105">В SQL не может выполняться все разнообразие методов, локально доступных приложению.</span><span class="sxs-lookup"><span data-stu-id="b7a31-105">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b7a31-106">пытается преобразовать эти локальные методы в равноценные операторы и функции среды SQL.</span><span class="sxs-lookup"><span data-stu-id="b7a31-106">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="b7a31-107">Большинство методов и операторов на .NET Framework встроенных типах имеют прямой перевод команд SQL.</span><span class="sxs-lookup"><span data-stu-id="b7a31-107">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="b7a31-108">Некоторые методы и операторы можно создать из доступных функций,</span><span class="sxs-lookup"><span data-stu-id="b7a31-108">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="b7a31-109">а те, которые не могут быть преобразованы, вызывают исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7a31-109">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="b7a31-110">Дополнительные сведения см. в разделе [Сопоставление типов SQL-CLR](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="b7a31-110">For more information, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="b7a31-111">В тех случаях, когда запроса [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] недостаточно для выполнения специализированной задачи, можно использовать метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> для выполнения запроса SQL и последующего преобразования результата запроса непосредственно в объекты.</span><span class="sxs-lookup"><span data-stu-id="b7a31-111">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7a31-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b7a31-112">Example</span></span>  

 <span data-ttu-id="b7a31-113">В следующем примере предполагается, что данные для класса `Customer` распределены по двум таблицам (customer1 и customer2).</span><span class="sxs-lookup"><span data-stu-id="b7a31-113">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="b7a31-114">Запрос возвращает последовательность объектов `Customer`.</span><span class="sxs-lookup"><span data-stu-id="b7a31-114">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="b7a31-115">При условии, что имена столбцов в табличных результатах соответствуют свойствам столбца класса сущностей, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объекты из любого SQL запроса.</span><span class="sxs-lookup"><span data-stu-id="b7a31-115">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7a31-116">Пример</span><span class="sxs-lookup"><span data-stu-id="b7a31-116">Example</span></span>  

 <span data-ttu-id="b7a31-117">Метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> также допускает использование параметров.</span><span class="sxs-lookup"><span data-stu-id="b7a31-117">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="b7a31-118">Для выполнения параметризованного запроса используется код, аналогичный представленному ниже.</span><span class="sxs-lookup"><span data-stu-id="b7a31-118">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="b7a31-119">Параметры записываются в тексте запроса с помощью той же нотации с фигурными скобками, которая используется в методах `Console.WriteLine()` и `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="b7a31-119">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="b7a31-120">`String.Format()`Фактически вызывается в предоставленной вами строке запроса, заменяя заключенные в фигурные скобки параметры созданными именами параметров, такими как @p0 , @p1 ..., @p (n).</span><span class="sxs-lookup"><span data-stu-id="b7a31-120">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a31-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b7a31-121">See also</span></span>

- [<span data-ttu-id="b7a31-122">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="b7a31-122">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="b7a31-123">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="b7a31-123">Querying the Database</span></span>](querying-the-database.md)
