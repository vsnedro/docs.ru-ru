---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.date: 03/30/2017
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
ms.openlocfilehash: f35cc0c12f2ac42c2b26536186c21feef193ae5d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594404"
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a><span data-ttu-id="625d9-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="625d9-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span></span>
<span data-ttu-id="625d9-103">Невозможно создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="625d9-103">A transaction could not be created.</span></span>  
  
## <a name="description"></a><span data-ttu-id="625d9-104">Описание</span><span class="sxs-lookup"><span data-stu-id="625d9-104">Description</span></span>  
 <span data-ttu-id="625d9-105">Данная трассировка создается, если MSDTC не может создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="625d9-105">This trace is generated when MSDTC is unable to create a transaction.</span></span> <span data-ttu-id="625d9-106">Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.</span><span class="sxs-lookup"><span data-stu-id="625d9-106">This can be due to low resources, insufficient log space, or other errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="625d9-107">Диагностика</span><span class="sxs-lookup"><span data-stu-id="625d9-107">Troubleshooting</span></span>  
 <span data-ttu-id="625d9-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="625d9-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625d9-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="625d9-109">See also</span></span>

- [<span data-ttu-id="625d9-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="625d9-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="625d9-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="625d9-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="625d9-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="625d9-112">Administration and Diagnostics</span></span>](../index.md)
