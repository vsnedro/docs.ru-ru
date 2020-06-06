---
title: Схема параметров запуска
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "61701519"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="0479d-102">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="0479d-102">Startup settings schema</span></span>

<span data-ttu-id="0479d-103">Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="0479d-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="0479d-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="0479d-104">Element</span></span>|<span data-ttu-id="0479d-105">Описание</span><span class="sxs-lookup"><span data-stu-id="0479d-105">Description</span></span>|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="0479d-106">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0479d-106">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="0479d-107">Приложения, созданные с помощью среды выполнения версии 1,1, должны использовать **\<supportedRuntime>** элемент.</span><span class="sxs-lookup"><span data-stu-id="0479d-107">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="0479d-108">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="0479d-108">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[\<startup>](startup-element.md)|<span data-ttu-id="0479d-109">Содержит **\<requiredRuntime>** элементы и **\<supportedRuntime>** .</span><span class="sxs-lookup"><span data-stu-id="0479d-109">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0479d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0479d-110">See also</span></span>

- [<span data-ttu-id="0479d-111">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="0479d-111">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0479d-112">Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше</span><span class="sxs-lookup"><span data-stu-id="0479d-112">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
