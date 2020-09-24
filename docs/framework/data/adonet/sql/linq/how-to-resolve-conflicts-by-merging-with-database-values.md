---
title: Практическое руководство. Как разрешать конфликты путем слияния значений базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
ms.openlocfilehash: fb77c4a23a4c4fa93dc55e63858ee41783c197ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166187"
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="f71c8-102">Практическое руководство. Как разрешать конфликты путем слияния значений базы данных</span><span class="sxs-lookup"><span data-stu-id="f71c8-102">How to: Resolve Conflicts by Merging with Database Values</span></span>

<span data-ttu-id="f71c8-103">Чтобы согласовать различия между ожидаемыми и фактическими значениями базы данных до повторной отправки изменений, можно воспользоваться <xref:System.Data.Linq.RefreshMode.KeepChanges> для слияния значений базы данных с текущими значениями члена клиента.</span><span class="sxs-lookup"><span data-stu-id="f71c8-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="f71c8-104">Дополнительные сведения см. в разделе [Оптимистическая блокировка: обзор](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f71c8-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f71c8-105">Во всех случаях запись на клиенте сначала обновляется путем извлечения обновленных данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="f71c8-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="f71c8-106">Это действие гарантирует успешное выполнение следующей попытки обновления при тех же проверках параллелизма.</span><span class="sxs-lookup"><span data-stu-id="f71c8-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f71c8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f71c8-107">Example</span></span>  

 <span data-ttu-id="f71c8-108">В данном сценарии, когда Пользователь1 пытается отправить изменения, возникает исключение <xref:System.Data.Linq.ChangeConflictException>, поскольку Пользователь2 в это время изменил столбцы "Помощник" и "Отдел".</span><span class="sxs-lookup"><span data-stu-id="f71c8-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="f71c8-109">Эта ситуация представлена в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f71c8-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="f71c8-110">Manager</span><span class="sxs-lookup"><span data-stu-id="f71c8-110">Manager</span></span>|<span data-ttu-id="f71c8-111">Помощник</span><span class="sxs-lookup"><span data-stu-id="f71c8-111">Assistant</span></span>|<span data-ttu-id="f71c8-112">отдел;</span><span class="sxs-lookup"><span data-stu-id="f71c8-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="f71c8-113">Исходное состояние базы данных при отправке запросов Пользователем1 и Пользователем2.</span><span class="sxs-lookup"><span data-stu-id="f71c8-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="f71c8-114">Алексеи</span><span class="sxs-lookup"><span data-stu-id="f71c8-114">Alfreds</span></span>|<span data-ttu-id="f71c8-115">Мария</span><span class="sxs-lookup"><span data-stu-id="f71c8-115">Maria</span></span>|<span data-ttu-id="f71c8-116">Sales</span><span class="sxs-lookup"><span data-stu-id="f71c8-116">Sales</span></span>|  
|<span data-ttu-id="f71c8-117">Пользователь1 готовится отправить изменения.</span><span class="sxs-lookup"><span data-stu-id="f71c8-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="f71c8-118">Алексей</span><span class="sxs-lookup"><span data-stu-id="f71c8-118">Alfred</span></span>||<span data-ttu-id="f71c8-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="f71c8-119">Marketing</span></span>|  
|<span data-ttu-id="f71c8-120">Пользователь2 уже отправил изменения.</span><span class="sxs-lookup"><span data-stu-id="f71c8-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="f71c8-121">Инна</span><span class="sxs-lookup"><span data-stu-id="f71c8-121">Mary</span></span>|<span data-ttu-id="f71c8-122">Служба</span><span class="sxs-lookup"><span data-stu-id="f71c8-122">Service</span></span>|  
  
 <span data-ttu-id="f71c8-123">Пользователь1 решает устранить этот конфликт путем объединения значений базы данных с текущими значениями члена клиента.</span><span class="sxs-lookup"><span data-stu-id="f71c8-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="f71c8-124">Ожидаемый результат: значения базы данных будут переопределены только при изменении значения текущим набором изменений.</span><span class="sxs-lookup"><span data-stu-id="f71c8-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="f71c8-125">При устранении Пользователем1 конфликта с помощью <xref:System.Data.Linq.RefreshMode.KeepChanges> результат в базе данных будет соответствовать данным в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f71c8-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="f71c8-126">Manager</span><span class="sxs-lookup"><span data-stu-id="f71c8-126">Manager</span></span>|<span data-ttu-id="f71c8-127">Помощник</span><span class="sxs-lookup"><span data-stu-id="f71c8-127">Assistant</span></span>|<span data-ttu-id="f71c8-128">отдел;</span><span class="sxs-lookup"><span data-stu-id="f71c8-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="f71c8-129">Новое состояние после устранения конфликта.</span><span class="sxs-lookup"><span data-stu-id="f71c8-129">New state after conflict resolution.</span></span>|<span data-ttu-id="f71c8-130">Алексей</span><span class="sxs-lookup"><span data-stu-id="f71c8-130">Alfred</span></span><br /><br /> <span data-ttu-id="f71c8-131">(от Пользователя1)</span><span class="sxs-lookup"><span data-stu-id="f71c8-131">(from User1)</span></span>|<span data-ttu-id="f71c8-132">Инна</span><span class="sxs-lookup"><span data-stu-id="f71c8-132">Mary</span></span><br /><br /> <span data-ttu-id="f71c8-133">(от Пользователя2)</span><span class="sxs-lookup"><span data-stu-id="f71c8-133">(from User2)</span></span>|<span data-ttu-id="f71c8-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="f71c8-134">Marketing</span></span><br /><br /> <span data-ttu-id="f71c8-135">(от Пользователя1)</span><span class="sxs-lookup"><span data-stu-id="f71c8-135">(from User1)</span></span>|  
  
 <span data-ttu-id="f71c8-136">В следующем примере показано объединение значений базы данных с текущими значениями члена клиента (если клиент также не изменил это значение).</span><span class="sxs-lookup"><span data-stu-id="f71c8-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="f71c8-137">Конфликты проверки или пользовательской обработки отдельных членов не возникают.</span><span class="sxs-lookup"><span data-stu-id="f71c8-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f71c8-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f71c8-138">See also</span></span>

- [<span data-ttu-id="f71c8-139">Практическое руководство. Как разрешать конфликты путем переписывания значений базы данных</span><span class="sxs-lookup"><span data-stu-id="f71c8-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)
- [<span data-ttu-id="f71c8-140">Практическое руководство. Как разрешать конфликты параллелизма путем сохранения значений базы данных</span><span class="sxs-lookup"><span data-stu-id="f71c8-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)
- [<span data-ttu-id="f71c8-141">Практическое руководство. Как управлять конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="f71c8-141">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
