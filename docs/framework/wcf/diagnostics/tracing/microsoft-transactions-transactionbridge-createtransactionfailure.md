---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.date: 03/30/2017
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
ms.openlocfilehash: 09b93ce4b72416cfea9f8c9850fd1e50c77035b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270227"
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a><span data-ttu-id="ad7a0-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="ad7a0-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span></span>

<span data-ttu-id="ad7a0-103">Невозможно создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="ad7a0-103">A transaction could not be created.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ad7a0-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ad7a0-104">Description</span></span>  

 <span data-ttu-id="ad7a0-105">Данная трассировка создается, если MSDTC не может создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="ad7a0-105">This trace is generated when MSDTC is unable to create a transaction.</span></span> <span data-ttu-id="ad7a0-106">Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.</span><span class="sxs-lookup"><span data-stu-id="ad7a0-106">This can be due to low resources, insufficient log space, or other errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ad7a0-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ad7a0-107">Troubleshooting</span></span>  

 <span data-ttu-id="ad7a0-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="ad7a0-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7a0-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ad7a0-109">See also</span></span>

- [<span data-ttu-id="ad7a0-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ad7a0-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="ad7a0-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ad7a0-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ad7a0-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ad7a0-112">Administration and Diagnostics</span></span>](../index.md)
