---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 23262427c3da730eaf930a8b483c7c4d4ec3a3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289845"
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|3508|  
|Keywords|WFServices|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.  
  
## <a name="message"></a>Сообщение  

 Не найден TrackingProfile «%1» для ActivityDefinitionId «%2». Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|Имя профиля отслеживания.|  
|ActivityDefinitionId|xs:string|Идентификатор определения действия.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
