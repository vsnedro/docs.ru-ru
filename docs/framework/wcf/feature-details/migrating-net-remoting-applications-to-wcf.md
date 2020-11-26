---
title: Перенос приложений удаленного взаимодействия .NET на платформу WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 2cfaebd064d10e5b331412d177929ecb20117a07
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248218"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="eb275-102">Перенос приложений удаленного взаимодействия .NET на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="eb275-102">Migrating .NET Remoting Applications to WCF</span></span>

<span data-ttu-id="eb275-103">**Эта статья относится к устаревшей технологии, которая сохраняется для обеспечения обратной совместимости с существующими приложениями и не рекомендуется для новых разработчиков. Теперь распределенные приложения разрабатываются с помощью WCF.**</span><span class="sxs-lookup"><span data-stu-id="eb275-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="eb275-104">Существует два способа использования преимуществ WCF с существующими приложениями удаленного взаимодействия .NET: интеграция и миграция.</span><span class="sxs-lookup"><span data-stu-id="eb275-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="eb275-105">Интеграция позволяет работать с .NET Remoting 2,0 и WCF параллельно, позволяя предоставлять одни и те же бизнес-объекты одновременно на обеих технологиях без необходимости изменения существующего кода .NET Remoting 2,0.</span><span class="sxs-lookup"><span data-stu-id="eb275-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="eb275-106">Для интеграции требуется, чтобы вы выполняли на .NET Framework 2,0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="eb275-106">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="eb275-107">Если вы хотите воспользоваться преимуществами функций WCF и не требуется совместимость с удаленными системами 2,0, вы можете перенести всю службу в WCF.</span><span class="sxs-lookup"><span data-stu-id="eb275-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="eb275-108">Для миграции из .NET Remoting 2,0 в WCF требуются изменения в интерфейсе удаленного объекта и его параметрах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eb275-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="eb275-109">Оба этих раздела рассматриваются в статье [удаленное взаимодействие с Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="eb275-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb275-110">См. также</span><span class="sxs-lookup"><span data-stu-id="eb275-110">See also</span></span>

- [<span data-ttu-id="eb275-111">Общие сведения об основных понятиях</span><span class="sxs-lookup"><span data-stu-id="eb275-111">Conceptual Overview</span></span>](../conceptual-overview.md)
