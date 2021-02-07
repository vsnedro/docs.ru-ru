---
description: 'Дополнительные сведения: 103-Активитистатерекорд'
title: 103 ― ActivityStateRecord
ms.date: 03/30/2017
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
ms.openlocfilehash: 14afbfdb0869b6ee65e1482fa73aa36ccd58f307
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668127"
---
# <a name="103---activitystaterecord"></a>103 ― ActivityStateRecord

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|103|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие выдается участником отслеживания ETW, когда действие в экземпляре рабочего процесса создает запись ActivityStateRecord.  
  
## <a name="message"></a>Сообщение  

 TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Область|xs:string|Состояние действия.|  
|Имя|xs:string|Отображаемое имя действия, выдавшего событие.|  
|ActivityId|xs:string|Идентификатор создающего действия.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра создающего действия.|  
|ActivityTypeName|xs:string|Имя типа выдающего действия.|  
|Аргументы|xs:string|Аргументы, которые были отслежены вместе с этим событием.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "argumentName" type="System.String"> argumentValue \</item> \</items> .  Если аргументы не были записаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .  Следующие типы хранятся в виде значения, возвращаемого методом ToString (); String, char, bool, int, Short, Long, uint, ushort, ulong, System. Single, float, Double, System. GUID, System. DateTimeOffset, System. DateTime.  Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Переменные|xs:string|Переменные, которые были отслежены совместно с этим событием.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "variableName" type="System.String"> вариаблевалуе \</item> \</items> .  Если переменные не были записаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения Variables на \<items> ... \</items> .  Следующие типы хранятся в виде значения, возвращаемого методом ToString (); String, char, bool, int, Short, Long, uint, ushort, ulong, System. Single, float, Double, System. GUID, System. DateTimeOffset, System. DateTime.  Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элементе в формате \<items> \< item  name = "annotationName" type="System.String"> аннотатионвалуе \</item> \</items> .  Если заметки не указаны, строка содержит \<items/> . Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает предел ETW, то событие усекается путем удаления заметок и замены значения аннотации на \<items> ... \</items> .|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName" example: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
