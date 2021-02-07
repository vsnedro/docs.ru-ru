---
description: 'Дополнительные сведения: 105-Фаултпропагатионрекорд'
title: 105 ― FaultPropagationRecord
ms.date: 03/30/2017
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
ms.openlocfilehash: 95f82763606bf16219fa4234b5f6e7101c0954fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667685"
---
# <a name="105---faultpropagationrecord"></a>105 ― FaultPropagationRecord

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|105|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается участником отслеживания ETW, когда действие внутри рабочего процесса создает запись FaultPropagationRecord.  
  
## <a name="message"></a>Сообщение  

 TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId=%9, FaultHandlerActivityInstanceId=%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName=%15  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|FaultSourceActivityName|xs:string|Имя действия, создавшего ошибку.|  
|FaultSourceActivityId|xs:string|Идентификатор действия, создавшего ошибку.|  
|FaultSourceActivityInstanceId|xs:string|Идентификатор экземпляра действия, создавшего ошибку.|  
|FaultSourceActivityTypeName|xs:string|Тип действия, создавшего ошибку.|  
|FaultHandlerActivityName|xs:string|Отображаемое имя действия обработчика ошибок.|  
|FaultHandlerActivityId|xs:string|Идентификатор действия обработчика ошибок.|  
|FaultHandlerActivityInstanceId|xs:string|Идентификатор экземпляра действия обработчика ошибок.|  
|FaultHandlerActivityTypeName|xs:string|Тип действия обработчика ошибок.|  
|Сбой|xs:string|Сведения об ошибке.|  
|IsFaultSource|xs:unsignedByte|Указывает, если было событие создано источником ошибки.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "annotationName" type="System.String"> аннотатионвалуе \</item> \</items> .  Если заметки не указаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName" example: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
