---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: 5066501faf4c336e095910e7e2d8ba1186ba3386
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251871"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="94fe3-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="94fe3-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>

<span data-ttu-id="94fe3-103">Служба протокола WS-AT получила ошибку от своего координатора в ответ на сообщение о регистрации.</span><span class="sxs-lookup"><span data-stu-id="94fe3-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="94fe3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="94fe3-104">Description</span></span>  

 <span data-ttu-id="94fe3-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager из-за того, что возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="94fe3-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="94fe3-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="94fe3-106">Troubleshooting</span></span>  

 <span data-ttu-id="94fe3-107">Проверьте возвращаемую ошибку в сообщении трассировки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fe3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="94fe3-108">See also</span></span>

- [<span data-ttu-id="94fe3-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="94fe3-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="94fe3-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="94fe3-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="94fe3-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="94fe3-111">Administration and Diagnostics</span></span>](../index.md)
