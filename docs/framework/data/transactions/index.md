---
title: Обработка транзакций
description: Проверьте обработку транзакций в .NET. Транзакции гарантируют, что ресурсы, ориентированные на данные, не обновляются, пока все операции не будут выполнены успешно.
ms.date: 03/30/2017
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
ms.openlocfilehash: bbf2448128da7df8af415ff5dea7e3cd8af24d1e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186813"
---
# <a name="transaction-processing"></a><span data-ttu-id="d7bb7-104">Обработка транзакций</span><span class="sxs-lookup"><span data-stu-id="d7bb7-104">Transaction Processing</span></span>

<span data-ttu-id="d7bb7-105">При покупке книги в книжном интернет-магазине вы обмениваете деньги (находящиеся на вашей кредитной карте) на книгу.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-105">When you purchase a book from an online bookstore, you exchange money (in the form of credit) for a book.</span></span> <span data-ttu-id="d7bb7-106">Если на вашей кредитной карте достаточно средств, выполняется последовательность операций, гарантирующая, что вы получите книгу, а книжный магазин - ваши деньги.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-106">If your credit is good, a series of related operations ensures that you get the book and the bookstore gets your money.</span></span> <span data-ttu-id="d7bb7-107">Однако если не удается выполнить хотя бы одну операцию в этой последовательности, вся процедура обмена заканчивается неудачей.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-107">However, if a single operation in the series fails during the exchange, the entire exchange fails.</span></span> <span data-ttu-id="d7bb7-108">Вы не получаете книгу, а книжный магазин не получает ваши деньги.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-108">You do not get the book and the bookstore does not get your money.</span></span>  
  
 <span data-ttu-id="d7bb7-109">Технология, отвечающая за обеспечение сбалансированного и предсказуемого обмена, называется обработкой транзакций.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-109">The technology responsible for making the exchange balanced and predictable is called transaction processing.</span></span> <span data-ttu-id="d7bb7-110">Транзакции гарантируют, что изменения информационно-ориентированных ресурсов фиксируются только после успешного выполнения всех операций в блоке транзакции.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-110">Transactions ensure that data-oriented resources are not permanently updated unless all operations within the transactional unit complete successfully.</span></span> <span data-ttu-id="d7bb7-111">Объединение нескольких связанных операций в один блок, который либо полностью выполняется, либо полностью не выполняется, позволяет упростить процесс восстановления после ошибок и повысить надежность вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-111">By combining a set of related operations into a unit that either completely succeeds or completely fails, you can simplify error recovery and make your application more reliable.</span></span>  
  
 <span data-ttu-id="d7bb7-112">Системы обработки транзакций состоят из компьютерного оборудования и программного обеспечения, в котором работает транзакционное приложение, выполняющее повседневные транзакции, необходимые для ведения бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-112">Transaction processing systems consist of computer hardware and software hosting a transaction-oriented application that performs the routine transactions necessary to conduct business.</span></span> <span data-ttu-id="d7bb7-113">Примерами таких систем являются системы обработки заказов на закупку, бронирования авиабилетов, обработки платежных ведомостей, обработки записей сотрудников, управления производством и доставки.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-113">Examples include systems that manage sales order entry, airline reservations, payroll, employee records, manufacturing, and shipping.</span></span>  
  
 <span data-ttu-id="d7bb7-114">В данном разделе представлены как общие сведения об обработке транзакций, так и конкретная информация о создании транзакционных приложений и диспетчеров ресурсов с помощью платформы Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-114">This section provides both general information on transaction processing, and specific information on how to write transactional applications and resource managers using the Microsoft .NET Framework.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7bb7-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d7bb7-115">In This Section</span></span>  

 [<span data-ttu-id="d7bb7-116">Основные сведения о транзакциях</span><span class="sxs-lookup"><span data-stu-id="d7bb7-116">Transaction Fundamentals</span></span>](transaction-fundamentals.md)  
 <span data-ttu-id="d7bb7-117">Описывает базовые термины и понятия технологии обработки транзакций.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-117">Introduces basic transaction processing terms and concepts.</span></span>  
  
 [<span data-ttu-id="d7bb7-118">Функциональные возможности, предоставляемые пространством имен System.Transactions</span><span class="sxs-lookup"><span data-stu-id="d7bb7-118">Features Provided by System.Transactions</span></span>](features-provided-by-system-transactions.md)  
 <span data-ttu-id="d7bb7-119">Описывает, как можно использовать функциональные возможности пространства имен System.Transactions для создания собственного транзакционного приложения.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-119">Discusses how you can use features in System.Transactions to write your own transactional application.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d7bb7-120">Справка</span><span class="sxs-lookup"><span data-stu-id="d7bb7-120">Reference</span></span>  

 <xref:System.Transactions>  
 <span data-ttu-id="d7bb7-121">Предоставляет классы, позволяющие коду участвовать в транзакциях.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-121">Provides classes that allow your code to participate in transactions.</span></span> <span data-ttu-id="d7bb7-122">Эти классы поддерживают транзакции с несколькими распределенными участниками, многофазные уведомления и зачисление устойчивых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d7bb7-122">The classes support transactions with multiple distributed participants, multiple phase notifications, and durable enlistments.</span></span>
