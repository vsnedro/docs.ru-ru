---
description: 'Дополнительные сведения: 4212-Локкретритимеаут'
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: a2299d0d9643fb60ff420519fb43199e3f747c69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667087"
---
# <a name="4212---lockretrytimeout"></a>4212 - LockRetryTimeout

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4212|  
|Keywords|WFInstanceStore|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.  
  
## <a name="message"></a>Сообщение  

 Истекло время ожидания при попытке получить блокировку экземпляра.  Не удалось выполнить операцию за выделенное время ожидания %1. Возможно, выделенное для этой операции время было частью более длительного времени ожидания.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Задержка|xs:string|Задержка между повторными попытками.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
