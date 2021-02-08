---
description: 'Дополнительные сведения: 3503-Дупликатекоррелатионкуери'
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: a8e1e41aad3aa1b273d8f8a5d7b0768fabe4e658
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778078"
---
# <a name="3503---duplicatecorrelationquery"></a>3503 - DuplicateCorrelationQuery

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|3503|  
|Keywords|WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Указывает, что обнаружен повторяющийся запрос CorrelationQuery. Повторяющийся запрос не будет использоваться при расчете корреляции.  
  
## <a name="message"></a>Сообщение  

 Обнаружен повторяющийся запрос CorrelationQuery с параметром Where=«%1». Это дубликат не будет использоваться при расчете корреляции.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Where|xs:string|Часть Where в запросе корреляции.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
