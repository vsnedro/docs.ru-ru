---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: d84f6c6f38868f7915caaaf87e15885099b65456
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266679"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a>201 - ClientMessageInspectorAfterReceiveInvoked

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|201|  
|Keywords|Troubleshooting, ServiceModel|  
|Level|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается после того, как модель службы вызывает метод `AfterReceiveReply` для инспектора сообщений клиента.  
  
## <a name="message"></a>Сообщение  

 Диспетчер вызвал AfterReceiveReply относительно ClientMessageInspector типа «%1».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Имя CLR FullName типа вызванного инспектора.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
