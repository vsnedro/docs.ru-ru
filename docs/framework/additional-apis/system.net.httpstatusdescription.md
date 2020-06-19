---
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
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990514"
---
# <a name="httpstatusdescription-class"></a>Класс Хттпстатусдескриптион

Предоставляет стандартные описания состояния HTTP. Этот класс не может быть унаследован.

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
