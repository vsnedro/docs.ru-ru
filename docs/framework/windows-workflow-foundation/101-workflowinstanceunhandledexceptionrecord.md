---
title: 101 ― WorkflowInstanceUnhandledExceptionRecord
ms.date: 03/30/2017
ms.assetid: ab7d50a0-5347-4390-8445-1def4dfdff6a
ms.openlocfilehash: f62868a09b72ef4fe567fbedc1729cd6bad309f0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239761"
---
# <a name="101---workflowinstanceunhandledexceptionrecord"></a>101 ― WorkflowInstanceUnhandledExceptionRecord

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|101|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Level|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceUnhandledExceptionRecord.  
  
## <a name="message"></a>Сообщение  

 TrackRecord=WorkflowInstanceUnhandledExceptionRecord, InstanceId=%1, RecordNumber=%2, EventTime=%3, ActivityDefinitionId=%4, SourceName=%5, SourceId=%6, SourceInstanceId=%7, SourceTypeName=%8, Exception=%9, Annotations=%10, ProfileName=%11  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|ActivityDefinitionId|xs:string|Имя корневого действия в рабочем процессе.|  
|SourceName|xs:string|Имя исходного действия, в котором произошла ошибка, что привело к созданию исключения unhandledException.|  
|SourceId|xs:string|Идентификатор исходного действия, в котором произошла ошибка.|  
|SourceInstanceId|xs:string|Идентификатор экземпляра исходного действия, в котором произошла ошибка.|  
|SourceTypeName|xs:string|Имя типа исходного действия, в котором произошла ошибка, что привело к созданию исключения unhandledException.|  
|Исключение|xs:string|Данные необработанного исключения.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "annotationName" type="System.String"> аннотатионвалуе \</item> \</items> .  Если заметки не указаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Формат имени веб-сайта определяется как "виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName" example: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
