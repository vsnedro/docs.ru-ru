---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275896"
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|39458|  
|Keywords|WFTracking|  
|Level|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что запись отслеживания была усечена. Данные переменных, заметок, пользователей удалены.  
  
## <a name="message"></a>Сообщение  

 Усеченная запись отслеживания %1 записана в сеанс трассировки событий Windows с использованием поставщика %2. Данные переменных, заметок, пользователей удалены  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Номер записи отслеживания.|  
|ProviderId|xs:string|Идентификатор поставщика трассировки событий Windows.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
