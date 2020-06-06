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
# <a name="startup-settings-schema"></a>Схема параметров запуска

Параметры запуска определяют версию среды CLR, в которой должно выполняться приложение.  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. Приложения, созданные с помощью среды выполнения версии 1,1, должны использовать **\<supportedRuntime>** элемент.|  
|[\<supportedRuntime>](supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|  
|[\<startup>](startup-element.md)|Содержит **\<requiredRuntime>** элементы и **\<supportedRuntime>** .|  
  
## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../index.md)
- [Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
