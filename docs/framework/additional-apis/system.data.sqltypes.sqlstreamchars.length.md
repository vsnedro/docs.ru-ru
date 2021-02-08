---
description: Дополнительные сведения о свойстве Склстреамчарс. length
title: Склстреамчарс. length, свойство (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b0a9686cadc6d4018c7f291f0326b71195fd5cf5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802597"
---
# <a name="sqlstreamcharslength-property"></a>Склстреамчарс. length, свойство

При переопределении в производном классе получает длину текущего потока. Сборка, содержащая это свойство, имеет дружественную связь с SQLAccess.dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

## <a name="syntax"></a>Синтаксис

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Int64>\
Длина потока.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SqlStreamChars.Length`Свойство является закрытым и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
