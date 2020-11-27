---
title: Исключения, транзакции и компенсация
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 2d8574c0f0f6bd3f66214367c1ed15292adc24a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280251"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="ba1a3-102">Исключения, транзакции и компенсация</span><span class="sxs-lookup"><span data-stu-id="ba1a3-102">Exceptions, Transactions, and Compensation</span></span>

[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="ba1a3-103">предоставляет несколько различных механизмов обработки состояний ошибок времени выполнения в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="ba1a3-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="ba1a3-104">Рабочие процессы могут использовать сочетание обработчиков исключений, транзакций, отмены и компенсации для обработки ошибочных состояний и верного возобновления работы.</span><span class="sxs-lookup"><span data-stu-id="ba1a3-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba1a3-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="ba1a3-105">In This Section</span></span>  

 [<span data-ttu-id="ba1a3-106">Исключения</span><span class="sxs-lookup"><span data-stu-id="ba1a3-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="ba1a3-107">Показывается использование действия <xref:System.Activities.Statements.TryCatch> для обработки исключений в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="ba1a3-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="ba1a3-108">Транзакции</span><span class="sxs-lookup"><span data-stu-id="ba1a3-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="ba1a3-109">Показывается использование действия <xref:System.Activities.Statements.TransactionScope> для использования транзакций в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="ba1a3-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="ba1a3-110">Компенсация</span><span class="sxs-lookup"><span data-stu-id="ba1a3-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="ba1a3-111">Описывается компенсация в рабочих процессах и показывается использование действий компенсации, например <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> и <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="ba1a3-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="ba1a3-112">Отмена</span><span class="sxs-lookup"><span data-stu-id="ba1a3-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="ba1a3-113">Описывает, как производить выполнение отмены в рабочих процессах с помощью встроенных и настраиваемых действий.</span><span class="sxs-lookup"><span data-stu-id="ba1a3-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="ba1a3-114">Отладка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ba1a3-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="ba1a3-115">Содержит описание способов отладки рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="ba1a3-115">Describes how to debug workflows.</span></span>
