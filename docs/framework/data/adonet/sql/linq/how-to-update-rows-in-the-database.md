---
title: Практическое руководство. Как обновлять строки в базе данных
description: Научитесь обновлять строки в базе данных, изменяя LINQ to SQL объекты в коллекции, связанной с таблицами. LINQ to SQL преобразует дополнения в команды обновления SQL.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: f25efb91fb5a83fb1c7c109bd018c8210edaec8b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286343"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="0fd32-104">Практическое руководство. Как обновлять строки в базе данных</span><span class="sxs-lookup"><span data-stu-id="0fd32-104">How to: Update Rows in the Database</span></span>

<span data-ttu-id="0fd32-105">Строки в базе данных можно обновлять, изменяя значения членов объектов, связанных с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> коллекцией, а затем отправляя изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="0fd32-105">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0fd32-106">преобразует изменения в соответствующие `UPDATE` команды SQL.</span><span class="sxs-lookup"><span data-stu-id="0fd32-106">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="0fd32-107">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="0fd32-107">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="0fd32-108">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0fd32-108">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="0fd32-109">Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="0fd32-109">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="0fd32-110">В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="0fd32-110">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="0fd32-111">Дополнительные сведения см. в разделе [как подключиться к базе данных](how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="0fd32-111">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="0fd32-112">Чтобы обновить строку в базе данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0fd32-112">To update a row in the database</span></span>

1. <span data-ttu-id="0fd32-113">Отправьте в базу данных запрос на обновляемую строку.</span><span class="sxs-lookup"><span data-stu-id="0fd32-113">Query the database for the row to be updated.</span></span>

2. <span data-ttu-id="0fd32-114">Выполните необходимые изменения значений членов полученного объекта [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fd32-114">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>

3. <span data-ttu-id="0fd32-115">Отправьте изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="0fd32-115">Submit the changes to the database.</span></span>

## <a name="example"></a><span data-ttu-id="0fd32-116">Пример</span><span class="sxs-lookup"><span data-stu-id="0fd32-116">Example</span></span>

<span data-ttu-id="0fd32-117">В следующем примере выполняются запросы к базе данных для заказа № 11000, а затем изменяются значения `ShipName` и `ShipVia` полученного объекта `Order`.</span><span class="sxs-lookup"><span data-stu-id="0fd32-117">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="0fd32-118">И наконец, изменения этих членов отправляются в базу данных в качестве изменений столбцов `ShipName` и `ShipVia`.</span><span class="sxs-lookup"><span data-stu-id="0fd32-118">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="0fd32-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0fd32-119">See also</span></span>

- [<span data-ttu-id="0fd32-120">Практическое руководство. Как управлять конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="0fd32-120">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="0fd32-121">Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="0fd32-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="0fd32-122">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="0fd32-122">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
