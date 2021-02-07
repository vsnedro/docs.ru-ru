---
description: 'Дополнительные сведения: 4206-Унлоккинстанцеексцептион'
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 7c281b7471869fc2361b1c7fb158559e4c9fae65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676278"
---
# <a name="4206---unlockinstanceexception"></a>4206 - UnlockInstanceException

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4206|  
|Keywords|WFInstanceStore|  
|Уровень|Ошибка|  
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
