---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: d3f27c6ed28efe9d099dcedfc676b839ae9b1dee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275844"
---
# <a name="4202---startsqlcommandexecute"></a>4202 - StartSqlCommandExecute

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4202|  
|Keywords|WFInstanceStore|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что команда SQL выполняется.  
  
## <a name="message"></a>Сообщение  

 Запуск выполнения команды SQL: %1  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|SqlCommand|xs:string|Команда SQL, которая была выполнена.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
