---
description: 'Дополнительные сведения о методе: Склстреамчарс. Write (char [], Int32, Int32)'
title: Метод Склстреамчарс. Write (char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 3031b57902215df01c5c30625281a99be73ba2d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802558"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>Метод Склстреамчарс. Write (char [], Int32, Int32)

При переопределении в производном классе записывает последовательность символов в текущий поток и перемещает текущую позицию в этом потоке вперед на число записанных символов. Сборка, содержащая этот метод, имеет дружественную связь с SQLAccess.dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Параметры

`buffer`  
Массив символов для записи.

`offset`  
Смещение относительно начала координат.

`count`  
Число символов, записываемых в текущий поток.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SqlStreamChars.Write`Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода для написания в рабочем приложении каких-либо обстоятельств.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
