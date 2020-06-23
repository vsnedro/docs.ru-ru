---
title: Однофазная и многофазная фиксация транзакции
description: Узнайте о фиксации транзакций на одном или двух этапах в .NET. Если транзакция включает более одного ресурса, необходимо выполнить двухфазной фиксацию (2PC).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
ms.openlocfilehash: 2f4486998f347bf1db6d22433e6e48b553609c18
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141828"
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a><span data-ttu-id="3b4b1-104">Однофазная и многофазная фиксация транзакции</span><span class="sxs-lookup"><span data-stu-id="3b4b1-104">Committing a Transaction in Single-Phase and Multi-Phase</span></span>
<span data-ttu-id="3b4b1-105">Каждым используемым в транзакции ресурсом управляет диспетчер ресурсов, действия которого координируются диспетчером транзакций.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-105">Each resource used in a transaction is managed by a resource manager (RM), whose actions are coordinated by a transaction manager (TM).</span></span> <span data-ttu-id="3b4b1-106">[Прикрепление ресурсов как участников в разделе транзакции](enlisting-resources-as-participants-in-a-transaction.md) описывает, как ресурс (или несколько ресурсов) можно прикрепить к транзакции.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-106">The [Enlisting Resources as Participants in a Transaction](enlisting-resources-as-participants-in-a-transaction.md) topic discusses how a resource (or multiple resources) can be enlisted in a transaction.</span></span> <span data-ttu-id="3b4b1-107">В этом разделе также описывается порядок координации процесса фиксации транзакции между зачисленными ресурсами.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-107">This topic discusses how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
 <span data-ttu-id="3b4b1-108">В конце транзакции приложение запрашивает ее фиксацию или откат.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-108">At the end of the transaction, the application requests the transaction to be either committed or rolled back.</span></span> <span data-ttu-id="3b4b1-109">Диспетчер транзакций должен исключить ситуации, в которых один из диспетчеров ресурсов голосует за фиксацию, а другие - за откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-109">The transaction manager must eliminate risks like some resource managers voting to commit while others voting to roll back the transaction.</span></span>  
  
 <span data-ttu-id="3b4b1-110">Если транзакция включает несколько ресурсов, необходимо выполнить двухфазную фиксацию (2PC).</span><span class="sxs-lookup"><span data-stu-id="3b4b1-110">If your transaction involves more than one resource, you must perform a two-phase commit (2PC).</span></span> <span data-ttu-id="3b4b1-111">Протокол двухфазной фиксации (фаза подготовки и фаза фиксации) гарантирует, что при завершении транзакции все изменения, произведенные над всеми ресурсами, либо полностью фиксируются, либо полностью откатываются.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-111">The two-phase commit protocol (the prepare phase and the commit phase) ensures that when the transaction ends, all changes to all resources are either totally committed or fully rolled back.</span></span> <span data-ttu-id="3b4b1-112">После завершения транзакции результат сообщается всем участникам.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-112">All the participants are then informed of the final result.</span></span> <span data-ttu-id="3b4b1-113">Подробное описание протокола двухфазной фиксации см. в книге "*обработка транзакций: основные понятия и методики (Morgan Кауфманн Series в управление данными Systems) ISBN: 1558601902*", Джим серый.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-113">For a detailed discussion of the two-phase commit protocol, please consult the book "*Transaction Processing : Concepts and Techniques (Morgan Kaufmann Series in Data Management Systems) ISBN:1558601902*" by Jim Gray.</span></span>  
  
 <span data-ttu-id="3b4b1-114">Кроме того, оптимизировать производительность транзакции можно путем участия в протоколе однофазной фиксации.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-114">You can also optimize your transaction's performance by taking part in the Single Phase Commit protocol.</span></span> <span data-ttu-id="3b4b1-115">Дополнительные сведения см. в статье [Оптимизация с использованием однофазных фиксаций и уведомления с одним этапом продвижения](optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="3b4b1-115">For more information, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="3b4b1-116">Если требуется только получение информации о результате транзакции без участия в голосовании, необходимо подписаться на событие <xref:System.Transactions.Transaction.TransactionCompleted>.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-116">If you just want to be informed of a transaction's outcome, and do not want to participate in voting, you should register for the <xref:System.Transactions.Transaction.TransactionCompleted> event.</span></span>  
  
## <a name="two-phase-commit-2pc"></a><span data-ttu-id="3b4b1-117">Двухфазная фиксация (2PC)</span><span class="sxs-lookup"><span data-stu-id="3b4b1-117">Two-phase Commit (2PC)</span></span>  
 <span data-ttu-id="3b4b1-118">В первой фазе транзакции диспетчер транзакций опрашивает каждый ресурс, чтобы определить, следует ли выполнить фиксацию или откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-118">In the first transaction phase, the transaction manager queries each resource to determine whether a transaction should be committed or rolled back.</span></span> <span data-ttu-id="3b4b1-119">Во второй фазе транзакции диспетчер транзакций уведомляет каждый ресурс о результате опроса, позволяя ресурсам выполнить необходимые операции очистки.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-119">In the second transaction phase, the transaction manager notifies each resource of the outcome of its queries, allowing it to perform any necessary cleanup.</span></span>  
  
 <span data-ttu-id="3b4b1-120">Для участия в такой транзакции диспетчеру ресурсов необходимо реализовать интерфейс <xref:System.Transactions.IEnlistmentNotification>, который предоставляет методы, вызываемые диспетчером транзакций как уведомления при двухфазной фиксации.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-120">To participate in this kind of transaction, a resource manager must implement the <xref:System.Transactions.IEnlistmentNotification> interface, which provides methods that are called by the TM as notifications during a 2PC.</span></span>  <span data-ttu-id="3b4b1-121">Ниже представлен пример такой реализации.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-121">The following sample shows an example of such implementation.</span></span>  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a><span data-ttu-id="3b4b1-122">Фаза подготовки (фаза 1)</span><span class="sxs-lookup"><span data-stu-id="3b4b1-122">Prepare phase (Phase 1)</span></span>  
 <span data-ttu-id="3b4b1-123">При получении запроса <xref:System.Transactions.CommittableTransaction.Commit%2A> от приложения диспетчер транзакций приступает к фазе подготовки всех зачисленных участников путем вызова метода <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> для каждого зачисленного ресурса с целью получения голосов за результат транзакции.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-123">Upon receiving a <xref:System.Transactions.CommittableTransaction.Commit%2A> request from the application, the transaction manager begins the Prepare phase of all the enlisted participants by calling the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method on each enlisted resource, in order to obtain each resource's vote on the transaction.</span></span>  
  
 <span data-ttu-id="3b4b1-124">Диспетчеру ресурсов, реализующему интерфейс <xref:System.Transactions.IEnlistmentNotification>, сначала необходимо реализовать метод <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29>, как показано в следующем простом примере.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-124">Your resource manager that implements the <xref:System.Transactions.IEnlistmentNotification> interface should first implement the <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> method as the following simple example shows.</span></span>  
  
```csharp
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 <span data-ttu-id="3b4b1-125">После получения этого вызова диспетчеру устойчивых ресурсов необходимо записать в журнал данные для восстановления транзакции (доступ к которым осуществляется путем извлечения свойства <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>) и всю необходимую информацию для завершения транзакции фиксацией.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-125">When the durable resource manager receives this call, it should log the transaction's recovery information (available by retrieving the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> property) and whatever information is necessary to complete the transaction on commit.</span></span> <span data-ttu-id="3b4b1-126">Запись этой информации в рамках метода <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> не требуется, поскольку диспетчер ресурсов может сделать это в рабочем потоке.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-126">This does not need to be performed within the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method because the RM can do this on a worker thread.</span></span>  
  
 <span data-ttu-id="3b4b1-127">После того, как диспетчер ресурсов завершил свои операции подготовки, ему необходимо проголосовать за фиксацию или откат путем вызова метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A> или <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-127">When the RM has finished its prepare work, it should vote to commit or roll back by calling the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> or <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> method.</span></span> <span data-ttu-id="3b4b1-128">Обратите внимание, что класс <xref:System.Transactions.PreparingEnlistment> наследует метод <xref:System.Transactions.Enlistment.Done%2A> от класса <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-128">Notice that the <xref:System.Transactions.PreparingEnlistment> class inherits a <xref:System.Transactions.Enlistment.Done%2A> method from the <xref:System.Transactions.Enlistment> class.</span></span> <span data-ttu-id="3b4b1-129">Если вызвать этот метод для обратного вызова <xref:System.Transactions.PreparingEnlistment> в фазе подготовки, он сообщает диспетчеру транзакций, что зачисленный ресурс доступен в режиме "только чтение" (т. е. диспетчеры ресурсов могут читать, но не могут изменять защищенные транзакцией данные), и диспетчер ресурсов не получает дальнейших уведомлений от диспетчера транзакций относительно результата транзакции в фазе 2.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-129">If you call this method on the <xref:System.Transactions.PreparingEnlistment> callback during the Prepare phase, it informs the TM that it is a Read-Only enlistment (that is, resource managers that can read but cannot update transaction-protected data) and the RM receives no further notifications from the transaction manager as to the outcome of the transaction in phase 2.</span></span>  
  
 <span data-ttu-id="3b4b1-130">Приложение получает сведения об успешной подготовке к фиксации транзакции после того, как все диспетчеры ресурсов проголосуют с помощью метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-130">The application is told of the successful commitment of the transaction after all the resource managers vote <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span></span>  
  
### <a name="commit-phase-phase-2"></a><span data-ttu-id="3b4b1-131">Фаза фиксации (фаза 2)</span><span class="sxs-lookup"><span data-stu-id="3b4b1-131">Commit phase (Phase 2)</span></span>  
 <span data-ttu-id="3b4b1-132">Если во второй фазе транзакции диспетчер транзакций получает сведения об успешной подготовке от всех диспетчеров ресурсов (все диспетчеры ресурсов вызвали метод <xref:System.Transactions.PreparingEnlistment.Prepared%2A> в конце фазы 1), он вызывает метод <xref:System.Transactions.IEnlistmentNotification.Commit%2A> для каждого диспетчера ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-132">In the second phase of the transaction, if the transaction manager receives successful prepares from all the resource managers (all the resource managers have invoked <xref:System.Transactions.PreparingEnlistment.Prepared%2A> at the end of phase 1), it invokes the <xref:System.Transactions.IEnlistmentNotification.Commit%2A> method for each resource manager.</span></span> <span data-ttu-id="3b4b1-133">После этого диспетчеры ресурсов могут зафиксировать изменения.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-133">The resource managers can then make the changes durable and complete the commit.</span></span>  
  
 <span data-ttu-id="3b4b1-134">Если в фазе 1 хотя бы от одного диспетчера ресурсов получено сообщение о том, что подготовку выполнить не удалось, диспетчер транзакций вызывает метод <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> для каждого диспетчера ресурсов и сообщает приложению о сбое фиксации.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-134">If any resource manager reported a failure to prepare in phase 1, the transaction manager invokes the <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> method for each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="3b4b1-135">Таким образом, используемому диспетчеру ресурсов необходимо реализовать следующие методы.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-135">Thus, your resource manager should implement the following methods.</span></span>  
  
```csharp
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment
     enlistment.Done();
}  
```  
  
 <span data-ttu-id="3b4b1-136">Диспетчер ресурсов должен выполнить любые действия, необходимые для завершения транзакции в соответствии с типом уведомления, и затем информировать диспетчер транзакций о завершении транзакции, вызвав метод <xref:System.Transactions.Enlistment.Done%2A> для параметра <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-136">The RM should perform any work necessary to finish the transaction based on the notification type, and inform the TM that it has finished by calling <xref:System.Transactions.Enlistment.Done%2A> method on the <xref:System.Transactions.Enlistment> parameter.</span></span> <span data-ttu-id="3b4b1-137">Это может быть выполнено в рабочем потоке.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-137">This work can be done on a worker thread.</span></span> <span data-ttu-id="3b4b1-138">Заметьте, что уведомления второго этапа могут быть встроены в тот же поток, который вызвал метод <xref:System.Transactions.PreparingEnlistment.Prepared%2A> на первой фазе.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-138">Note that the phase 2 notifications can happen inline on the same thread that called the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> method in phase 1.</span></span> <span data-ttu-id="3b4b1-139">Таким образом, после вызова метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A> не нужно выполнять никаких действий (например, снимать блокировки), которые должны были быть выполнены перед получением уведомлений второго этапа.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-139">As such, you should not do any work after the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> call (for example, releasing locks) that you would expect to have completed before receiving the phase 2 notifications.</span></span>  
  
### <a name="implementing-indoubt"></a><span data-ttu-id="3b4b1-140">Реализация метода InDoubt</span><span class="sxs-lookup"><span data-stu-id="3b4b1-140">Implementing InDoubt</span></span>  
 <span data-ttu-id="3b4b1-141">Наконец, необходимо реализовать метод <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> для диспетчера неустойчивых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-141">Finally, you should implement the <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> method for the volatile resource manager.</span></span> <span data-ttu-id="3b4b1-142">Этот метод вызывается при потере контакта диспетчера транзакций с одним или несколькими участниками, в результате чего их состояние становится неизвестным.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-142">This method is called if the transaction manager loses contact with one or more participants, so their status is unknown.</span></span> <span data-ttu-id="3b4b1-143">В этом случае необходимо сделать соответствующую запись в журнале, чтобы можно было позднее выяснить, остался ли кто-либо из участников транзакции в несогласованном состоянии.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-143">If this occurs, you should log this fact so that you can investigate later whether any of the transaction participants has been left in an inconsistent state.</span></span>  
  
```csharp
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a><span data-ttu-id="3b4b1-144">Оптимизация однофазной фиксации</span><span class="sxs-lookup"><span data-stu-id="3b4b1-144">Single Phase Commit Optimization</span></span>  
 <span data-ttu-id="3b4b1-145">Протокол однофазной фиксации наиболее эффективен при использовании во время выполнения, поскольку все изменения производятся без какой-либо явной координации.</span><span class="sxs-lookup"><span data-stu-id="3b4b1-145">The Single Phase Commit protocol is more efficient at run time because all updates are done without any explicit coordination.</span></span> <span data-ttu-id="3b4b1-146">Дополнительные сведения об этом протоколе см. в статье [Оптимизация с использованием однофазных фиксаций и уведомления с одним этапом продвижения](optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="3b4b1-146">For more information on this protocol, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4b1-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b4b1-147">See also</span></span>

- [<span data-ttu-id="3b4b1-148">Оптимизация производительности с помощью механизмов уведомления об однофазной фиксации и повышаемого однофазного присоединения</span><span class="sxs-lookup"><span data-stu-id="3b4b1-148">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](optimization-spc-and-promotable-spn.md)
- [<span data-ttu-id="3b4b1-149">Зачисление ресурсов в транзакцию в качестве участников</span><span class="sxs-lookup"><span data-stu-id="3b4b1-149">Enlisting Resources as Participants in a Transaction</span></span>](enlisting-resources-as-participants-in-a-transaction.md)
