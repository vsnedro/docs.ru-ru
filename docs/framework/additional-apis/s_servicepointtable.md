---
title: Поле ServicePointManager. s_ServicePointTable
description: Прочитайте о поле ServicePointManager. s_ServicePointTable в .NET. Это поле хэш-таблицы содержит активные HTTP-соединения (Сервицепоинтс) в домене приложения.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989549"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager. s \_ Сервицепоинттабле поле

`ServicePointManager.s_ServicePointTable`значение типа <xref:System.Collections.Hashtable> , содержащее список активных HTTP-соединений <xref:System.Net.ServicePoint> в <xref:System.AppDomain> .

## <a name="syntax"></a>Синтаксис
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> `ServicePointManager.s_ServicePointTable`Поле является закрытым и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого поля в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)

**.NET Framework версии:** Доступно с 2,0.
