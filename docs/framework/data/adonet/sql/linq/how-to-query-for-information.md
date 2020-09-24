---
title: Практическое руководство. Как обращаться с запросами о сведениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166408"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="5d5f8-102">Практическое руководство. Как обращаться с запросами о сведениях</span><span class="sxs-lookup"><span data-stu-id="5d5f8-102">How to: Query for Information</span></span>

<span data-ttu-id="5d5f8-103">Запросы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используют тот же синтаксис, что и запросы в LINQ.</span><span class="sxs-lookup"><span data-stu-id="5d5f8-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="5d5f8-104">Единственное отличие заключается в том, что объекты, на которые имеются ссылки в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запросах, сопоставляются с элементами в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5d5f8-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="5d5f8-105">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f8-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="5d5f8-106">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки.</span><span class="sxs-lookup"><span data-stu-id="5d5f8-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="5d5f8-107">Некоторые функции запросов LINQ могут потребовать особого внимания в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложениях.</span><span class="sxs-lookup"><span data-stu-id="5d5f8-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="5d5f8-108">Дополнительные сведения см. в разделе [Основные понятия запросов](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f8-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d5f8-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5d5f8-109">Example</span></span>  

 <span data-ttu-id="5d5f8-110">Следующий запрос возвращает список клиентов из Лондона.</span><span class="sxs-lookup"><span data-stu-id="5d5f8-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="5d5f8-111">В этом примере используется таблица `Customers` из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="5d5f8-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5d5f8-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5d5f8-112">See also</span></span>

- [<span data-ttu-id="5d5f8-113">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="5d5f8-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="5d5f8-114">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="5d5f8-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="5d5f8-115">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="5d5f8-115">Querying the Database</span></span>](querying-the-database.md)
