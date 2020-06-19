---
title: Класс Маиладдресспарсер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.MailAddressParser
- System.Net.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 2c17970614ff9b6f1e6793a064a956da7248d693
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990510"
---
# <a name="mailaddressparser-class"></a>Класс Маиладдресспарсер

Анализирует адреса электронной почты, как описано в RFC 2822. Этот класс не может быть унаследован.

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="parseaddress-method"></a>Метод Парсеаддресс

Выполняет синтаксический анализ одного адреса электронной почты из указанной строки.

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a>Параметры

`data` <xref:System.String>

Строка, содержащая адрес электронной почты для синтаксического анализа.

### <a name="return-value"></a>Возвращаемое значение

<xref:System.Net.Mail.MailAddress>

Допустимый адрес электронной почты.

### <a name="exceptions"></a>Исключения

<xref:System.FormatException?displayProperty=nameWithType>

Недопустимый адрес электронной почты.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)
