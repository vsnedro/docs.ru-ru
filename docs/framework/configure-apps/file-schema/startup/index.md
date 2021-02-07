---
description: Дополнительные сведения о схеме параметров запуска
title: Схема параметров запуска
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: 268b8d8dc2598add61435dd6b07031aa06831737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726095"
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
