---
description: 'Дополнительные сведения о: Хттпстатусдескриптион Class'
title: Класс Хттпстатусдескриптион (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fa135a6421397ce6b7be2af05d66aa8e81beafb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802506"
---
# <a name="httpstatusdescription-class"></a>Класс HttpStatusDescription

Предоставляет стандартные описания состояния HTTP. Этот класс не наследуется.

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="get-method"></a>Get - метод

Возвращает описание, связанное с указанным кодом состояния HTTP.

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a>Параметры

`code` <xref:System.Int32>

Код состояния HTTP, например `404` .

### <a name="return-value"></a>Возвращаемое значение

<xref:System.String?displayProperty=nameWithType>

Описание состояния HTTP.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)
