---
title: Устаревшие интерфейсы размещения CLR и CoClasses
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
ms.openlocfilehash: 814f148b39045ad5454a23dfce8e7f9441f69041
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616415"
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="e14e4-102">Устаревшие интерфейсы размещения CLR и CoClasses</span><span class="sxs-lookup"><span data-stu-id="e14e4-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="e14e4-103">В этом разделе описываются интерфейсы, которые могут использоваться неуправляемыми узлами для интеграции среды CLR в .NET Framework версии 1,0 и 1,1 в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="e14e4-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="e14e4-104">Эти интерфейсы предоставляют основному приложению методы для настройки и загрузки среды выполнения в процесс.</span><span class="sxs-lookup"><span data-stu-id="e14e4-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e14e4-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e14e4-105">In This Section</span></span>  
 <span data-ttu-id="e14e4-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="e14e4-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="e14e4-107">Предоставляет для узла методы настройки <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="e14e4-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="e14e4-108">Класс ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="e14e4-108">ICeeFileGen Class</span></span>](iceefilegen-class.md)  
 <span data-ttu-id="e14e4-109">Не рекомендуется Предоставляет функциональные возможности для создания машинного переносимого исполняемого файла (PE).</span><span class="sxs-lookup"><span data-stu-id="e14e4-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="e14e4-110">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e14e4-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)  
 <span data-ttu-id="e14e4-111">Предоставляет для узла методы настройки параметров среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e14e4-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e14e4-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e14e4-112">Related Sections</span></span>  
 [<span data-ttu-id="e14e4-113">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e14e4-113">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="e14e4-114">Содержит разделы, описывающие интерфейсы размещения, предоставляемые с .NET Framework версии 2,0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e14e4-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
