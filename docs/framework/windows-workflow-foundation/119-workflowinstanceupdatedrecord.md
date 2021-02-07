---
description: 'Дополнительные сведения: 119-Воркфловинстанцеупдатедрекорд'
title: 119 ― WorkflowInstanceUpdatedRecord
ms.date: 03/30/2017
ms.assetid: 32485d0a-dcdb-45bc-b1e3-79fa9ad9439b
ms.openlocfilehash: e59bbe81d548fccb0d44d6f8c1b442ee6ad685f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703202"
---
# <a name="119---workflowinstanceupdatedrecord"></a>119 ― WorkflowInstanceUpdatedRecord

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|119|  
|Keywords|HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается участником трассировки событий Windows, когда обновляется экземпляр рабочего процесса.  
  
## <a name="message"></a>Сообщение  

 TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|ActivityDefinitionId|xs:string|Имя корневого действия в рабочем процессе.|  
|Область|xs:string|Текущее состояние рабочего процесса.|  
|OriginalDefinitionIdentity|xs:string|Исходный идентификатор определения рабочего процесса|  
|UpdatedDefinitionIdentity|xs:string|Обновленный идентификатор определения рабочего процесса.|  
|Заметки|xs:string|Заметки, добавленные к этому событию. Значения хранятся в XML-элементе в формате \<items> \< item name = "annotationName" type="System.String"> аннотатионвалуе \</item> \</items> . Если заметки не указаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|WorkflowDefinitionIdentity|xs:string|Идентификатор определения рабочего процесса|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
