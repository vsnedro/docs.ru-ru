---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 83bb67f2a5eb1a9353129bce9ec22f18eb382259
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251975"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="d1d82-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="d1d82-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>

<span data-ttu-id="d1d82-103">Сбой службы протокола WS-AT при отправке сообщения Register своему координатору</span><span class="sxs-lookup"><span data-stu-id="d1d82-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="d1d82-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d1d82-104">Description</span></span>  

 <span data-ttu-id="d1d82-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager по причине невозможности отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="d1d82-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d1d82-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d1d82-106">Troubleshooting</span></span>  

 <span data-ttu-id="d1d82-107">Проверить сообщение трассировки на исключение, приводящее к сбою отправки сообщения</span><span class="sxs-lookup"><span data-stu-id="d1d82-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d82-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d1d82-108">See also</span></span>

- [<span data-ttu-id="d1d82-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="d1d82-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="d1d82-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="d1d82-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d1d82-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="d1d82-111">Administration and Diagnostics</span></span>](../index.md)
