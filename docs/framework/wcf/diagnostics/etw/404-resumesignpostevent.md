---
description: 'Дополнительные сведения: 404-Ресумесигнпостевент'
title: 404 - ResumeSignpostEvent
ms.date: 03/30/2017
ms.assetid: 395cc7ca-f35f-4295-be97-39a077f99c97
ms.openlocfilehash: f735df6133c9708c05b2319e7ea17d7795e901b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760294"
---
# <a name="404---resumesignpostevent"></a>404 - ResumeSignpostEvent

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|404|  
|Keywords|Устранение неполадок|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие отмечает продолжение сквозного действия. В ней содержится имя действия.  
  
## <a name="message"></a>Сообщение  

 Граница действия.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
