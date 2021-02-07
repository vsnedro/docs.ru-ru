---
description: 'Дополнительные сведения о свойстве: Пуледстреам. NetworkStream'
title: Свойство Пуледстреам. NetworkStream (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 8a4f1d6bd9297028e763ef73bf96f85cbbfdafd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699640"
---
# <a name="pooledstreamnetworkstream-property"></a>Пуледстреам. NetworkStream, свойство

Возвращает или задает сетевой поток для `PooledStream` сокета.

## <a name="syntax"></a>Синтаксис

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Net.Sockets.NetworkStream>  
Сетевой поток для `PooledStream` сокета.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `PooledStream.NetworkStream`Свойство является внутренним и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
