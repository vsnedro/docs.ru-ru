---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: ad9d82162313e46626e5e2fa6f4ef99bf0139162
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599663"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="23aeb-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="23aeb-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="23aeb-103">Служба протокола WS-AT получила ошибку от своего координатора в ответ на сообщение о регистрации.</span><span class="sxs-lookup"><span data-stu-id="23aeb-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="23aeb-104">Описание</span><span class="sxs-lookup"><span data-stu-id="23aeb-104">Description</span></span>  
 <span data-ttu-id="23aeb-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager из-за того, что возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="23aeb-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="23aeb-106">Диагностика</span><span class="sxs-lookup"><span data-stu-id="23aeb-106">Troubleshooting</span></span>  
 <span data-ttu-id="23aeb-107">Проверьте возвращаемую ошибку в сообщении трассировки.</span><span class="sxs-lookup"><span data-stu-id="23aeb-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23aeb-108">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="23aeb-108">See also</span></span>

- [<span data-ttu-id="23aeb-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="23aeb-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="23aeb-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="23aeb-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="23aeb-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="23aeb-111">Administration and Diagnostics</span></span>](../index.md)
