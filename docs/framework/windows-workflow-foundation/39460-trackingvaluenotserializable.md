---
title: 39460 - TrackingValueNotSerializable
ms.date: 03/30/2017
ms.assetid: 476a29ad-24d8-4359-8c17-d4e20c1e1c15
ms.openlocfilehash: 0ffa33f78f0f3c4eaf2c7519ac27207c095d8c17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275857"
---
# <a name="39460---trackingvaluenotserializable"></a>39460 - TrackingValueNotSerializable

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|39460|  
|Keywords|WFTracking|  
|Level|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что извлеченные переменная или аргумент в записи отслеживания не сериализуются.  
  
## <a name="message"></a>Сообщение  

 Извлеченный аргумент или переменная «%1» не сериализуется.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|name|xs:string|Имя элемента.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
