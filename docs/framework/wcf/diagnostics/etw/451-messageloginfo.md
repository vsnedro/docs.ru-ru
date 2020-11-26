---
title: 451 - MessageLogInfo
ms.date: 03/30/2017
ms.assetid: 485b4b29-dc21-4a35-93f8-5f4726d6aa5a
ms.openlocfilehash: 2b5dd36099e1d9978cb1136462c224a79465f823
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242790"
---
# <a name="451---messageloginfo"></a>451 - MessageLogInfo

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|451|  
|Keywords|Troubleshooting, WCFMessageLogging|  
|Level|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие формируется при отправке данных журнала сообщений.  
  
## <a name="message"></a>Сообщение  

 %1  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|data1|`xs:string`||  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
