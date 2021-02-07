---
description: 'Дополнительные сведения о: 107--Букмаркресумптионрекорд'
title: 107 ― BookmarkResumptionRecord
ms.date: 03/30/2017
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
ms.openlocfilehash: 456a6cd9f723732454ce032facd062a26aa609be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667633"
---
# <a name="107----bookmarkresumptionrecord"></a>107 ― BookmarkResumptionRecord

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|107|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись BookmarkResumptionRecord.  
  
## <a name="message"></a>Сообщение  

 TrackRecord=BookmarkResumptionRecord, InstanceId=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5, OwnerActivityName=%6, OwnerActivityId=%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName=%11  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Имя|xs:string|Имя возобновленной закладки.|  
|SubInstanceID|xs:GUID|Идентификатор области закладки.|  
|OwnerActivityName|xs:string|Имя действия закладки.|  
|OwnerActivityId|xs:string|Идентификатор действия закладки.|  
|OwnerActivityInstanceId|xs:string|Идентификатор экземпляра действия закладки.|  
|OwnerActivityTypeName|xs:string|Тип действия закладки.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "annotationName" type="System.String"> аннотатионвалуе \</item> \</items> .  Если заметки не указаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName" example: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
