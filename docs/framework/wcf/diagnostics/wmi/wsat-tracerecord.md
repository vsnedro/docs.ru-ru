---
description: 'Дополнительные сведения: WSAT_TraceRecord'
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 67202c5d2910783c40b934d2da6108e6b514a728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756881"
---
# <a name="wsat_tracerecord"></a>WSAT_TraceRecord

WSAT_TraceRecord  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс WSAT_TraceRecord не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс WSAT_TraceRecord имеет следующие свойства.  
  
### <a name="activityid"></a>Идентификатор действия  

 Тип данных: объект  
Тип доступа: только для чтения  
  
 ИД активности записи трассировки.  
  
### <a name="eventid"></a>EventID  

 Тип данных: sint32  
Тип доступа: только для чтения  
  
 ИД события записи трассировки.  
  
### <a name="tracerecord"></a>TraceRecord  

 Тип данных: строка  
Тип доступа: только для чтения  
  
 Запись трассировки  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
