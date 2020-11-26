---
title: 1102 - WorkflowActivityStop
ms.date: 03/30/2017
ms.assetid: 285e5cb8-e90d-4914-ac06-e9b176ffefa2
ms.openlocfilehash: 7b5c7874946ae494f41e73f3e7c90f3944a3521d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238695"
---
# <a name="1102---workflowactivitystop"></a>1102 - WorkflowActivityStop

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1102|  
|Keywords|WFRuntime|  
|Level|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что действия рабочего процесса остановлены.  
  
## <a name="message"></a>Сообщение  

 Элемент WorkflowInstance с идентификатором «%1», действие E2E  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Идентификатор экземпляра рабочего процесса.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
