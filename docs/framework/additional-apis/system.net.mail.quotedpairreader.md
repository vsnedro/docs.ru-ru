---
description: 'Дополнительные сведения о: Куотедпаирреадер Class'
title: Класс Куотедпаирреадер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 810a7b02948a1b7aa542a179563af9a6d79dd763
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699666"
---
# <a name="quotedpairreader-class"></a>Класс QuotedPairReader

Определяет, какие символы в строке заключены в кавычки (экранированные). Этот класс не наследуется.

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="countquotedchars-method"></a>Метод Каунткуотедчарс

Подсчитывает количество последовательных заключенных в кавычки символов, включая несколько предшествующих кавычек, в указанной строке. Например, если задана строка `a\\\b` и индекс `4` , метод возвращает значение `4` , так как `b` заключено в кавычки и поэтому являются три предшествующих обратной косой черты.

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a>Параметры

- `data` <xref:System.String>

  Строка данных, в которой подсчитывается число последовательных символов в кавычках.

- `index` <xref:System.Int32>

  Строка в указанной строке до и включает в себя подсчет последовательных символов в кавычках.

- `permitUnicodeEscaping` <xref:System.Boolean>

  `true` значение для запрета экранирования символов Юникода; в противном случае — `false` .

### <a name="return-value"></a>Возвращаемое значение

<xref:System.Int32?displayProperty=nameWithType>

`0` значение, если символ по указанному индексу не экранирован; в противном случае — число последовательных символов в кавычках до символа, включая символ `index` .

### <a name="exceptions"></a>Исключения

<xref:System.FormatException?displayProperty=nameWithType>

Escape-символ Юникода найден, но не разрешен.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)
