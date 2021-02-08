---
description: 'Дополнительные сведения о методе: Склстреамчарс. Dispose (Boolean)'
title: Метод Склстреамчарс. Dispose (Boolean) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ce24cc885d87a3ff0bbcdbea7992ca78ee592454
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802610"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a>Метод Склстреамчарс. Dispose (логический)

При переопределении в производном классе освобождает ресурсы, используемые потоком. Сборка, содержащая этот метод, имеет дружественную связь с SQLAccess.dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a>Параметры

`disposing`\
Значение `true` позволяет освободить как управляемые, так и неуправляемые ресурсы; значение `false` освобождает только неуправляемые ресурсы.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SqlStreamChars.Dispose`Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
