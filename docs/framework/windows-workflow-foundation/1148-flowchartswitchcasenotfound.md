---
title: 1148 - FlowchartSwitchCaseNotFound
ms.date: 03/30/2017
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
ms.openlocfilehash: fb9f4be3dba0f8632f1ae074ad9ddb726c5d84ab
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241711"
---
# <a name="1148---flowchartswitchcasenotfound"></a>1148 - FlowchartSwitchCaseNotFound

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1148|  
|Keywords|WFActivities|  
|Level|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что в параметре блок-схемы не найден ни соответствующий вариант, ни вариант по умолчанию. Выполнение блок-схемы будет завершено.  
  
## <a name="message"></a>Сообщение  

 Блок-схема «%1»/FlowSwitch - не удалось найти ни действие Case, ни действие Default Case, соответствующее результату выражения Expression. Выполнение блок-схемы будет завершено.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Блок-схема|xs:string|Отображаемое имя блок-схемы.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
