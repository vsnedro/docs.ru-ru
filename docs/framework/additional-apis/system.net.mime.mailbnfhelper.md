---
title: Класс Маилбнфхелпер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990501"
---
# <a name="mailbnfhelper-class"></a>Класс Маилбнфхелпер

Содержит служебные методы для синтаксического анализа строк в формате сообщений Интернета. Этот класс не может быть унаследован.

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="ascii7bitmaxvalue-field"></a>Поле Ascii7bitMaxValue

Представляет максимальное 7-разрядное значение ASCII.

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a>Поле аТекст

Представляет символы, разрешенные в атомах.

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a>Поле CR

Представляет символ возврата каретки.

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a>Поле столбец ctext

Представляет символы, разрешенные внутри комментариев.

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a>Поле точки

Представляет символ полной позиции ( `.` ).

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a>Поле Ендкоммент

Представляет символ, указывающий конец комментария.

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a>Поле LF

Представляет символ перевода строки.

```csharp
internal static readonly char LF
```

## <a name="space-field"></a>Поле пробела

Представляет символ пробела.

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a>Поле Старткоммент

Представляет символ, указывающий начало комментария.

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a>Поле вкладки

Представляет символ табуляции.

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)
