---
description: 'Дополнительные сведения о: Активититрансфер'
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 28f7d1c0d1056327313e7aa6be293eb325d8f265
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99758012"
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
