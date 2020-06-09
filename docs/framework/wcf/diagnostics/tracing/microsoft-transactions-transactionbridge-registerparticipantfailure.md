---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 1819a269a6775c8541f38f4aa5d733002e3c1e9f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599687"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="28465-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="28465-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="28465-103">Службе протокола WS-AT не удалось зарегистрировать участника для протокола управления.</span><span class="sxs-lookup"><span data-stu-id="28465-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="28465-104">Описание</span><span class="sxs-lookup"><span data-stu-id="28465-104">Description</span></span>  
 <span data-ttu-id="28465-105">Отслеживается, обнаруживает ли MSDTC недопустимый запрос на регистрацию.</span><span class="sxs-lookup"><span data-stu-id="28465-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="28465-106">Это может происходить из-за множественных запросов на регистрацию завершения и внутренних ошибок.</span><span class="sxs-lookup"><span data-stu-id="28465-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="28465-107">Диагностика</span><span class="sxs-lookup"><span data-stu-id="28465-107">Troubleshooting</span></span>  
 <span data-ttu-id="28465-108">Не пытайтесь зарегистрировать завершение несколько раз.</span><span class="sxs-lookup"><span data-stu-id="28465-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="28465-109">Проверьте строку состояния в сообщении трассировки, чтобы определить, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="28465-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28465-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="28465-110">See also</span></span>

- [<span data-ttu-id="28465-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="28465-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="28465-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="28465-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="28465-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="28465-113">Administration and Diagnostics</span></span>](../index.md)
