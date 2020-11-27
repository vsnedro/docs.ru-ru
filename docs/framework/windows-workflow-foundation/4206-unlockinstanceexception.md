---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 48182d7c5fe8f29842a17f28c0ea296f93b31089
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251260"
---
# <a name="4206---unlockinstanceexception"></a>4206 - UnlockInstanceException

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4206|  
|Keywords|WFInstanceStore|  
|Level|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что при попытке разблокировать экземпляр возникло исключение.  
  
## <a name="message"></a>Сообщение  

 При попытке разблокировать экземпляр обнаружено исключение «%1».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|Текст сообщения из исключения SQL.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
