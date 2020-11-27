---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 87a98d30f5ecde6f81580a95e337df22341c23d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279029"
---
# <a name="213---servicehoststarted"></a>213 - ServiceHostStarted

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|213|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost|  
|Level|LogAlways|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается при запуске службы, размещенной на веб-сервере. Обычно это происходит, когда служба активируется сообщением. Это также может произойти, если служба настроена для автоматического запуска.  
  
## <a name="message"></a>Сообщение  

 ServiceHost запущена: «%1».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Имя типа службы|`xs:string`|Имя CLR FullName типа реализации службы.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
