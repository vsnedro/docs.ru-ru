---
title: Класс Маиладдресспарсер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051354"
---
# <a name="mailaddressparser-class"></a>Класс MailAddressParser

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
