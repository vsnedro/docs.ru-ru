---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 17617e25c5cf8cecae608438529e9ce1a7d506f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251273"
---
# <a name="4203---renewlocksystemerror"></a>4203 - RenewLockSystemError

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4203|  
|Keywords|WFInstanceStore|  
|Level|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что поставщику SQL не удалось продлить срок блокировки либо из-за того, что срок блокировки уже истек, либо из-за того, что владелец блокировки был удален. SqlWorkflowInstanceStore будет прервано.  
  
## <a name="message"></a>Сообщение  

 Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален. Прерывание блокировки SqlWorkflowInstanceStore.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
