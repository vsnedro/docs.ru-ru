---
title: Создание транзакционного приложения
description: Написание транзакционного приложения в .NET. Используйте явную или неявную модель программирования с классом Transaction или классом TransactionScope соответственно.
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: b4cc33939128e61a69db319491a7d2d60ab9a819
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186671"
---
# <a name="writing-a-transactional-application"></a><span data-ttu-id="b4ee5-104">Создание транзакционного приложения</span><span class="sxs-lookup"><span data-stu-id="b4ee5-104">Writing a Transactional Application</span></span>

<span data-ttu-id="b4ee5-105">Пространство имен <xref:System.Transactions> предоставляет разработчикам транзакционных приложений две модели программирования для создания транзакций.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-105">As a transactional application programmer, you can take advantage of the two programming models provided by the <xref:System.Transactions> namespace to create a transaction.</span></span> <span data-ttu-id="b4ee5-106">Явную модель программирования можно использовать с помощью <xref:System.Transactions.Transaction> класса или неявной модели программирования, в которой транзакции автоматически управляются инфраструктурой с помощью <xref:System.Transactions.TransactionScope> класса.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-106">You can utilize the explicit programming model by using the <xref:System.Transactions.Transaction> class, or the implicit programming model in which transactions are automatically managed by the infrastructure, by using the <xref:System.Transactions.TransactionScope> class.</span></span> <span data-ttu-id="b4ee5-107">Для разработки рекомендуется использовать модель неявной транзакции.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-107">We recommend that you use the implicit transaction model for development.</span></span> <span data-ttu-id="b4ee5-108">Дополнительные сведения об использовании области транзакций см. в разделе [Реализация неявной транзакции с помощью области транзакций](implementing-an-implicit-transaction-using-transaction-scope.md) .</span><span class="sxs-lookup"><span data-stu-id="b4ee5-108">You can find more information on how to use a transaction scope in the [Implementing an Implicit Transaction using Transaction Scope](implementing-an-implicit-transaction-using-transaction-scope.md) topic.</span></span>  
  
 <span data-ttu-id="b4ee5-109">Обе модели поддерживают фиксацию транзакции при достижении программой согласованного состояния.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-109">Both models support committing a transaction when the program reaches a consistent state.</span></span> <span data-ttu-id="b4ee5-110">При успешной фиксации выполненные в ходе транзакции изменения становятся постоянными.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-110">If the commit succeeds, the transaction is durably committed.</span></span> <span data-ttu-id="b4ee5-111">Если фиксация завершается неудачей, транзакция прерывается.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-111">If the commit fails, the transaction aborts.</span></span> <span data-ttu-id="b4ee5-112">Если приложение не может успешно завершить транзакцию, оно пытается прервать ее выполнение и отменить произведенные в ходе транзакции изменения.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-112">If the application program cannot successfully complete the transaction, it attempts to abort and undo the transaction's effects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4ee5-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b4ee5-113">In This Section</span></span>  
  
### <a name="creating-a-transaction"></a><span data-ttu-id="b4ee5-114">Создание транзакции</span><span class="sxs-lookup"><span data-stu-id="b4ee5-114">Creating a Transaction</span></span>  

 <span data-ttu-id="b4ee5-115">Пространство имен <xref:System.Transactions> предоставляет две модели для создания транзакций.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-115">The <xref:System.Transactions> namespace provides two models for creating a transaction.</span></span> <span data-ttu-id="b4ee5-116">Эти модели рассматриваются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-116">These models are covered in the following topics.</span></span>  
  
 [<span data-ttu-id="b4ee5-117">Реализация неявной транзакции с использованием области транзакции</span><span class="sxs-lookup"><span data-stu-id="b4ee5-117">Implementing an Implicit Transaction using Transaction Scope</span></span>](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 <span data-ttu-id="b4ee5-118">Описывает, как пространство имен <xref:System.Transactions> поддерживает создание неявных транзакций с использованием класса <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-118">Describes how the <xref:System.Transactions> namespace supports creating implicit transactions using the <xref:System.Transactions.TransactionScope> class.</span></span>  
  
 [<span data-ttu-id="b4ee5-119">Реализация явной транзакции с помощью класса CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="b4ee5-119">Implementing an Explicit Transaction using CommittableTransaction</span></span>](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 <span data-ttu-id="b4ee5-120">Описывает, как пространство имен <xref:System.Transactions> поддерживает создание явных транзакций с использованием класса <xref:System.Transactions.CommittableTransaction>.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-120">Describes how the <xref:System.Transactions> namespace supports creating explicit transactions using the <xref:System.Transactions.CommittableTransaction> class.</span></span>  
  
### <a name="escalating-transaction-management"></a><span data-ttu-id="b4ee5-121">Передача управления транзакцией на следующий уровень иерархии</span><span class="sxs-lookup"><span data-stu-id="b4ee5-121">Escalating Transaction Management</span></span>  

 <span data-ttu-id="b4ee5-122">Если транзакции необходим доступ к ресурсу в другом домене приложения или требуется зачислить другой диспетчер устойчивых ресурсов, управление транзакцией автоматически передается координатору MSDTC.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-122">When a transaction needs to access a resource in another application domain, or if you want to enlist in another durable resource manager, the transaction is automatically escalated to be managed by the MSDTC.</span></span> <span data-ttu-id="b4ee5-123">Укрупнение транзакций рассматривается в разделе [эскалация управления транзакциями](transaction-management-escalation.md) .</span><span class="sxs-lookup"><span data-stu-id="b4ee5-123">Transaction escalation is covered in the [Transaction Management Escalation](transaction-management-escalation.md) topic.</span></span>  
  
### <a name="concurrency"></a><span data-ttu-id="b4ee5-124">Параллелизм</span><span class="sxs-lookup"><span data-stu-id="b4ee5-124">Concurrency</span></span>  

 <span data-ttu-id="b4ee5-125">В разделе [Управление параллелизмом с помощью класса DependentTransaction](managing-concurrency-with-dependenttransaction.md) показано, как можно достичь параллелизма между асинхронными задачами с использованием <xref:System.Transactions.DependentTransaction> класса.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-125">The topic [Managing Concurrency with DependentTransaction](managing-concurrency-with-dependenttransaction.md) demonstrates how concurrency can be achieved between asynchronous tasks by using the <xref:System.Transactions.DependentTransaction> class.</span></span>  
  
### <a name="com-interop"></a><span data-ttu-id="b4ee5-126">Взаимодействие с транзакциями COM+</span><span class="sxs-lookup"><span data-stu-id="b4ee5-126">COM+ Interop</span></span>  

 <span data-ttu-id="b4ee5-127">В разделе [взаимодействие с корпоративными службами и транзакциями COM+](interoperability-with-enterprise-services-and-com-transactions.md) показано, как можно сделать распределенные транзакции взаимодействующими с транзакциями COM+.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-127">The topic [Interoperability with Enterprise Services and COM+ Transactions](interoperability-with-enterprise-services-and-com-transactions.md) illustrates how you can make your distributed transactions interact with COM+ transactions.</span></span>  
  
### <a name="diagnostics"></a><span data-ttu-id="b4ee5-128">Диагностика</span><span class="sxs-lookup"><span data-stu-id="b4ee5-128">Diagnostics</span></span>  

 <span data-ttu-id="b4ee5-129">[Диагностические трассировки](diagnostic-traces.md) описывает, как можно использовать коды трассировки, созданные <xref:System.Transactions> инфраструктурой, для устранения неполадок в приложениях.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-129">[Diagnostic Traces](diagnostic-traces.md) describes how you can use the trace codes that are generated by the <xref:System.Transactions> infrastructure to troubleshoot errors in your applications.</span></span>  
  
### <a name="working-within-aspnet"></a><span data-ttu-id="b4ee5-130">Работа в среде ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4ee5-130">Working within ASP.NET</span></span>  

 <span data-ttu-id="b4ee5-131">В разделе [использование System. Transactions в ASP.NET](using-system-transactions-in-aspnet.md) описывается, как можно успешно использовать <xref:System.Transactions> внутри приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b4ee5-131">The [Using System.Transactions in ASP.NET](using-system-transactions-in-aspnet.md) topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>
