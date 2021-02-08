---
description: 'Дополнительные сведения о методе: Склстреамчарс. SetLength (Int64)'
title: Метод Склстреамчарс. SetLength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d10ce55126ae09062fe895c3a686ce5d94174554
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804144"
---
# <a name="sqlstreamcharssetlengthint64-method"></a>Склстреамчарс. SetLength (Int64), метод

При переопределении в производном классе освобождает ресурсы, используемые потоком. Сборка, содержащая этот метод, имеет дружественную связь с SQLAccess.dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a>Параметры

`value`\
Нужная длина текущего потока в байтах.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SqlStreamChars.SetLength`Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
