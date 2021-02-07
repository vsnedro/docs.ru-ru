---
description: 'Дополнительные сведения: 1125-Инвокемесодиснотстатик'
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: cd63b7b75121a70f7d7bad6a799827971aa4eae9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667373"
---
# <a name="1125---invokemethodisnotstatic"></a>1125 - InvokeMethodIsNotStatic

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1125|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - не статический.  
  
## <a name="message"></a>Сообщение  

 Метод InvokeMethod «%1»: метод не является статическим.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
