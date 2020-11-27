---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 3e4e1ff7ea8d8768c8d902dc09bd3b78646c2caf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256330"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="4fefc-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="4fefc-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>

<span data-ttu-id="4fefc-103">Службе протокола WS-AT не удалось включить в список транзакцию, используя предоставленный контекст координации.</span><span class="sxs-lookup"><span data-stu-id="4fefc-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4fefc-104">Описание</span><span class="sxs-lookup"><span data-stu-id="4fefc-104">Description</span></span>  

 <span data-ttu-id="4fefc-105">Регистрируется, если координатору MSDTC не удалось включить в список транзакцию для заданного протокола 2pc.</span><span class="sxs-lookup"><span data-stu-id="4fefc-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="4fefc-106">Это может произойти, если транзакция больше не существует, включение в список уже запрещено или если уже имеется слишком много перечислений.</span><span class="sxs-lookup"><span data-stu-id="4fefc-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4fefc-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="4fefc-107">Troubleshooting</span></span>  

 <span data-ttu-id="4fefc-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="4fefc-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fefc-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4fefc-109">See also</span></span>

- [<span data-ttu-id="4fefc-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="4fefc-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="4fefc-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="4fefc-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4fefc-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="4fefc-112">Administration and Diagnostics</span></span>](../index.md)
