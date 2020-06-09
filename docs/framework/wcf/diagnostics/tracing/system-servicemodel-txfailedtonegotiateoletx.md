---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2c9ea77cdd76d4593c2ee5b09a4b917677b8925f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601417"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="15ea5-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="15ea5-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="15ea5-103">Согласование протокола OleTransactions невозможно завершить для заданного контекста координации.</span><span class="sxs-lookup"><span data-stu-id="15ea5-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="15ea5-104">Описание</span><span class="sxs-lookup"><span data-stu-id="15ea5-104">Description</span></span>  
 <span data-ttu-id="15ea5-105">Трассируется, если входящая транзакция с информацией OleTx не может использовать прикрепленную информацию OleTx и вместо этого использует WS-AT.</span><span class="sxs-lookup"><span data-stu-id="15ea5-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="15ea5-106">Диагностика</span><span class="sxs-lookup"><span data-stu-id="15ea5-106">Troubleshooting</span></span>  
 <span data-ttu-id="15ea5-107">Показывает возможную проблему обмена данными MSDTC RPC между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="15ea5-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="15ea5-108">Появление большого количества таких трассировок в журнале может привести к значительному снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="15ea5-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="15ea5-109">Если информация OleTx не требуется, установите `OleTxUpgradeEnabled` на значение 0 в конфигурации реестра WS-AT.</span><span class="sxs-lookup"><span data-stu-id="15ea5-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ea5-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="15ea5-110">See also</span></span>

- [<span data-ttu-id="15ea5-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="15ea5-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="15ea5-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="15ea5-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="15ea5-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="15ea5-113">Administration and Diagnostics</span></span>](../index.md)
