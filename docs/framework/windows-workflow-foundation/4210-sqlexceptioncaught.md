---
title: 4210 - SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 1dab44e3fb97d74a2146f5bf992225222bc93d50
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280381"
---
# <a name="4210---sqlexceptioncaught"></a>4210 - SqlExceptionCaught

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4210|  
|Keywords|WFInstanceStore|  
|Level|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что было перехвачено исключение SQL.  
  
## <a name="message"></a>Сообщение  

 Обнаружено исключение SQL с номером %1, сообщение %2.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Номер ошибки|xs:string|Номер ошибки SQL.|  
|ExceptionMessage|xs:string|Текст сообщения из исключения SQL.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
