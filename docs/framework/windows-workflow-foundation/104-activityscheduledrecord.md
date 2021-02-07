---
description: 'Дополнительные сведения: 104-Активитисчедуледрекорд'
title: 104 ― ActivityScheduledRecord
ms.date: 03/30/2017
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
ms.openlocfilehash: 9d52dac3ec68de0d38959e81294c5c6ead21428e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667815"
---
# <a name="104---activityscheduledrecord"></a>104 ― ActivityScheduledRecord

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|104|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается участником отслеживания ETW, когда действие в экземпляре рабочего процесса создает запись ActivityScheduledRecord.  
  
## <a name="message"></a>Сообщение  

 TrackRecord=ActivityScheduledRecord, InstanceId=%1, RecordNumber=%2, EventTime=%3, Name =%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName=%7, ChildActivityName=%8, ChildActivityId=%9, ChildActivityInstanceId=%10, ChildActivityTypeName=%11, Annotations=%12, ProfileName=%13  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Имя|xs:string|Имя действия, которое запланировало дочернее действие.|  
|ActivityId|xs:string|Идентификатор действия, которое запланировало дочернее действие.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра действия, которое запланировало дочернее действие.|  
|ActivityTypeName|xs:string|Тип действия, запросившего операцию отмены.|  
|ChildActivityName|xs:string|Имя запланированного действия.|  
|ChildActivityId|xs:string|Идентификатор запланированного действия.|  
|ChildActivityInstanceId|xs:string|Идентификатор экземпляра запланированного действия.|  
|ChildActivityTypeName|xs:string|Тип запланированного действия.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "annotationName" type="System.String"> аннотатионвалуе \</item> \</items> .  Если заметки не указаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName" example: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
