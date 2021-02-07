---
description: 'Дополнительные сведения: 1030-Стартфаултворкитем'
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 2d148277b2d593cfcf75e17662626f1f486e7c1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668101"
---
# <a name="1030---startfaultworkitem"></a>1030 - StartFaultWorkItem

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1030|  
|Keywords|WFRuntime|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает на начало выполнения FaultWorkItem.  
  
## <a name="message"></a>Сообщение  

 Запуск выполнения Фаултворкитем для действия "%1", DisplayName: "%2", InstanceId: "%3".  Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Имя типа действия с ошибкой.|  
|FaultActivityDisplayName|xs:string|Отображаемое имя действия с ошибкой.|  
|FaultActivityInstanceId|xs:string|Идентификатор экземпляра действия с ошибкой.|  
|ExceptionActivity|xs:string|Имя типа действия, вызвавшего исключение.|  
|ExceptionActivityDisplayName|xs:string|Отображаемое имя действия, вызвавшего исключение.|  
|ExceptionActivityInstanceId|xs:string|Идентификатор экземпляра действия, вызвавшего исключение.|  
|Исключение|xs:string|Сведения об исключении|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
