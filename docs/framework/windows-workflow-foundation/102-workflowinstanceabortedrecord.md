---
description: 'Дополнительные сведения: 102-Воркфловинстанцеабортедрекорд'
title: 102 ― WorkflowInstanceAbortedRecord
ms.date: 03/30/2017
ms.assetid: bde4378d-4eea-4907-aaf2-c1a2bc770a37
ms.openlocfilehash: 2fd192af1624618a2800843ad58a1fc65d5f86b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792860"
---
# <a name="102---workflowinstanceabortedrecord"></a>102 ― WorkflowInstanceAbortedRecord

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|102|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceAbortedRecord.  
  
## <a name="message"></a>Сообщение  

 TrackRecord=WorkflowInstanceAbortedRecord, InstanceId=%1, RecordNumber=%2, EventTime=%3, ActivityDefinitionId=%4, Reason=%5, Annotations=%6, ProfileName=%7  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|ActivityDefinitionId|xs:string|Имя корневого действия в рабочем процессе.|  
|Причина|xs:string|Причина, по которой был прерван рабочий процесс.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "annotationName" type="System.String"> аннотатионвалуе \</item> \</items> .  Если заметки не указаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName" example: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
