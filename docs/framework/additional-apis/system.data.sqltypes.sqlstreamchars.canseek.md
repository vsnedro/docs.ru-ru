---
description: 'Дополнительные сведения о свойстве: Склстреамчарс. CanSeek'
title: Свойство Склстреамчарс. CanSeek (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5919a66bef9ac31e0ef15ad4af64b456700605f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802623"
---
# <a name="sqlstreamcharscanseek-property"></a>Склстреамчарс. CanSeek, свойство

При переопределении в производном классе получает значение, указывающее, поддерживает ли текущий Steam операцию Seek. Сборка, содержащая это свойство, имеет дружественную связь с SQLAccess.dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Boolean>\
`true` значение, если текущий Steam поддерживает операцию Seek; в противном случае — `false` .

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SqlStreamChars.CanSeek`Свойство является закрытым и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
