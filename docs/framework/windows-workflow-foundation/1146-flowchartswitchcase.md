---
description: 'Дополнительные сведения: 1146-Фловчартсвитчкасе'
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: f6e9b33f9c068b51695d3ac46cda51fb6d9f8b3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667074"
---
# <a name="1146---flowchartswitchcase"></a>1146 - FlowchartSwitchCase

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1146|  
|Keywords|WFActivities|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, какой вариант (Case) был выбран в параметре блок-схемы.  
  
## <a name="message"></a>Сообщение  

 Блок-схема «%1»/FlowSwitch: выбран вариант Case «%2».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Блок-схема|xs:string|Отображаемое имя блок-схемы.|  
|Случай|xs:string|Выбранный вариант Case.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
