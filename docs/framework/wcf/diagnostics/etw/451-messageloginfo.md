---
description: 'Дополнительные сведения: 451-Мессажелогинфо'
title: 451 - MessageLogInfo
ms.date: 03/30/2017
ms.assetid: 485b4b29-dc21-4a35-93f8-5f4726d6aa5a
ms.openlocfilehash: 9df1911eaee3300b770175f2af26e6dafd3de90c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760281"
---
# <a name="451---messageloginfo"></a>451 - MessageLogInfo

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|451|  
|Keywords|Troubleshooting, WCFMessageLogging|  
|Уровень|Сведения|  
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
