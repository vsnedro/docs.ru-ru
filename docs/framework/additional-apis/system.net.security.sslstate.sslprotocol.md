---
description: 'Дополнительные сведения о свойстве: Сслстате. Сслпротокол'
title: Свойство Сслстате. Сслпротокол (System .NET. Security)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: b0b9bebf23fcd8d643d06f1cff10c260c77a7c08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699627"
---
# <a name="sslstatesslprotocol-property"></a>Сслстате. Сслпротокол, свойство

Возвращает версии протокола SSL.

## <a name="syntax"></a>Синтаксис

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Security.Authentication.SslProtocols>  
Побитовое сочетание значений перечисления, определяющих версии протокола SSL.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `SslState.SslProtocol`Свойство является внутренним и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net.Security>

**Сборка:** Система (в System.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.
