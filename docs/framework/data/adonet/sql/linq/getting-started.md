---
title: Начало работы
description: С помощью этого примера кода приступайте к работе с LINQ to SQL, чтобы использовать технологию LINQ для доступа к базам данных SQL так же, как и к коллекции в памяти.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: a46c42e917bdab0d32ee594bbcd604ee9e3d26bc
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286421"
---
# <a name="getting-started"></a><span data-ttu-id="ba373-103">Приступая к работе</span><span class="sxs-lookup"><span data-stu-id="ba373-103">Getting Started</span></span>
<span data-ttu-id="ba373-104">С помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] можно использовать технологию LINQ для доступа к базам данных SQL так же, как и к коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="ba373-104">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="ba373-105">В следующем примере кода создается объект `nw` для представления базы данных `Northwind`, выполняется запрос к таблице `Customers`, фильтруются строки для поиска клиентов (`Customers`) из Лондона (`London`) и выбирается строка `CompanyName` для извлечения.</span><span class="sxs-lookup"><span data-stu-id="ba373-105">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="ba373-106">При выполнении цикла извлекается коллекция значений `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="ba373-106">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="ba373-107">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ba373-107">Next Steps</span></span>  
 <span data-ttu-id="ba373-108">Дополнительные примеры, включая вставку и обновление, см. [в разделе что можно делать с LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ba373-108">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="ba373-109">Далее ознакомьтесь с некоторыми пошаговыми руководствами и учебниками, чтобы получить практический навык работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba373-109">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ba373-110">См. раздел [обучение по пошаговым руководствам](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="ba373-110">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="ba373-111">Наконец, Узнайте, как приступить к работе над собственным [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проектом, прочитав [типичные шаги для использования LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ba373-111">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba373-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ba373-112">See also</span></span>

- [<span data-ttu-id="ba373-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ba373-113">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="ba373-114">Введение в LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ba373-114">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="ba373-115">Знакомство с LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba373-115">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="ba373-116">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ba373-116">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
