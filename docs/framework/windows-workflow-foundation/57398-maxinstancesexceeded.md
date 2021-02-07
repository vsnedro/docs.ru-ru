---
description: 'Дополнительные сведения: 57398-Максинстанцесексцеедед'
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: 104c466cb2e0ee8156e2b268caf5e757353dfb09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720232"
---
# <a name="57398---maxinstancesexceeded"></a>57398 - MaxInstancesExceeded

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|57398|  
|Keywords|WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Указывает, что система достигла предела, заданного для ограничителя MaxConcurrentInstances.  
  
## <a name="message"></a>Сообщение  

 Система достигла предела, заданного для ограничителя «MaxConcurrentInstances». Для этого ограничителя был задан предел %1. Значение ограничителя можно изменить, изменив атрибут maxConcurrentInstances в элементе serviceThrottle или свойство MaxConcurrentInstances для поведения ServiceThrottlingBehavior.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Имя|xs:string|Имя элемента.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
