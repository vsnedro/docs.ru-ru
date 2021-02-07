---
description: 'Дополнительные сведения: 208-Мессажеинспекторафтеррецеивеинвокед'
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 29935f5dc8c5dd53c0bf427bfdc9b3858d7fb8fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728058"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a>208 - MessageInspectorAfterReceiveInvoked

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|208|  
|Keywords|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается после того, как модель службы вызвала метод `AfterReceive` для инспектора сообщений.  
  
## <a name="message"></a>Сообщение  

 Диспетчер вызвал AfterReceiveReply относительно MessageInspector типа «%1».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Имя CLR FullName типа вызванного инспектора `MessageInspector`.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
