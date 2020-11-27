---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 0d6326889077e36ad49aa6267ae7285849c6818d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275870"
---
# <a name="4201---endsqlcommandexecute"></a>4201 - EndSqlCommandExecute

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4201|  
|Keywords|WFInstanceStore|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что команда SQL завершена.  
  
## <a name="message"></a>Сообщение  

 Окончание выполнения команды SQL: %1  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|SqlCommand|xs:string|Команда SQL, которая была выполнена.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
