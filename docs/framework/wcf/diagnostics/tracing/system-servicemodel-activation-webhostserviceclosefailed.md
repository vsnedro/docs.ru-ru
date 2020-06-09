---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: af24847d5174475103340725c86ff44024556671
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84588864"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="54ed3-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="54ed3-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="54ed3-103">Возникает при невозможности правильного закрытия службы или при прерывании службы.</span><span class="sxs-lookup"><span data-stu-id="54ed3-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="54ed3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="54ed3-104">Description</span></span>  
 <span data-ttu-id="54ed3-105">Данный код ошибки отображается только в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="54ed3-105">This error code only appears in the log file.</span></span> <span data-ttu-id="54ed3-106">Как правило, он указывает на наличие программной ошибки, например при попытке закрыть службу после того, как был вызван метод Abort.</span><span class="sxs-lookup"><span data-stu-id="54ed3-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="54ed3-107">Диагностика</span><span class="sxs-lookup"><span data-stu-id="54ed3-107">Troubleshooting</span></span>  
 <span data-ttu-id="54ed3-108">Проверьте исходный код приложения.</span><span class="sxs-lookup"><span data-stu-id="54ed3-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ed3-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="54ed3-109">See also</span></span>

- [<span data-ttu-id="54ed3-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="54ed3-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="54ed3-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="54ed3-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="54ed3-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="54ed3-112">Administration and Diagnostics</span></span>](../index.md)
