---
description: 'Дополнительные сведения: 1132-Инвокемесоддоеснотусеасинкпаттерн'
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 05bbd1f6047ab4c6451d71a4f6007f3112f9630f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667282"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a>1132 - InvokeMethodDoesNotUseAsyncPattern

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1132|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 На шаге CacheMetadata действие InvokeMethod указывает, что при вызове метода не используется асинхронный шаблон.  
  
## <a name="message"></a>Сообщение  

 Метод InvokeMethod «%1»: в методе не используется асинхронная модель.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
