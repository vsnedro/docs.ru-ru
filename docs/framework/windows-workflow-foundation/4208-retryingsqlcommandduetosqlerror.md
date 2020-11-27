---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280420"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a>4208 - RetryingSqlCommandDueToSqlError

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4208|  
|Keywords|WFInstanceStore|  
|Level|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что поставщик SQL повторяет команду SQL из-за ошибки SQL.  
  
## <a name="message"></a>Сообщение  

 Выполняется повтор команды SQL из-за ошибки SQL с номером %1.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Номер ошибки|xs:string|Номер ошибки SQL.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
