---
description: 'Дополнительные сведения: 1126-Инвокедмесодсревексцептион'
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 35c4311a4ab7750cc54a5c9ffb379f34b1cb12aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667360"
---
# <a name="1126---invokedmethodthrewexception"></a>1126 - InvokedMethodThrewException

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1126|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.  
  
## <a name="message"></a>Сообщение  

 Возникло исключение в методе, вызванном операцией «%1». %2  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|Исключение|xs:string|Сведения об исключении|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
