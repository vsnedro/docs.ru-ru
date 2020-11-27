---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291119"
---
# <a name="activitytransfer"></a>ActivityTransfer

Событие перенаправления действия  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс ActivityTransfer не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  

 Класс ActivityTransfer имеет следующие свойства.  
  
### <a name="activityid"></a>Идентификатор действия  
  
- Тип данных: объект  
    Тип доступа: только для чтения  
  
- Идентификатор действия  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Тип данных: объект  
    Тип доступа: только для чтения  
  
- Связанный идентификатор действия  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
