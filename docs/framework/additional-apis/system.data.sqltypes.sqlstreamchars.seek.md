---
description: 'Дополнительные сведения о методе: Склстреамчарс. Seek (Int64, SeekOrigin)'
title: Метод Склстреамчарс. Seek (Int64, SeekOrigin) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 00f71aff95045d566b7932aec3f7e18259b4dfa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802571"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>Метод Склстреамчарс. Seek (Int64, SeekOrigin)

При переопределении в производном классе задает позицию в текущем потоке. Сборка, содержащая этот метод, имеет дружественную связь с SQLAccess.dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Параметры

`offset`\
Смещение в байтах относительно `origin`.

`origin`\
Одно из значений перечисления, указывающее точку ссылки, из которой следует получить новую позицию.

## <a name="returns"></a>Возвращаемое значение

<xref:System.Int32>\
Новая позиция в текущем потоке.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SqlStreamChars.Seek`Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
