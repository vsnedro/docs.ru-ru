---
description: 'Дополнительные сведения о методе: Склстреамчарс. Read (char [], Int32, Int32)'
title: Метод Склстреамчарс. Read (char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: a899ddff7b7242fcc32aaf7b7f7794970596027b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802584"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>Метод Склстреамчарс. Read (char [], Int32, Int32)

При переопределении в производном классе считывает следующий набор символов из входного потока. Сборка, содержащая этот метод, имеет дружественную связь с SQLAccess.dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Параметры

`buffer`\
Массив символов для чтения.

`offset`\
Смещение относительно начала координат.

`count`\
Число символов, считываемых из текущего потока.

## <a name="returns"></a>Возвращаемое значение

<xref:System.Int32>\
Общее количество символов, считанных в буфер.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SqlStreamChars.Read`Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
