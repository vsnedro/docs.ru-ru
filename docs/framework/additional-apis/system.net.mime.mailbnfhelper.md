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
# <a name="mailbnfhelper-class"></a><span data-ttu-id="b8ba7-102">Класс Маилбнфхелпер</span><span class="sxs-lookup"><span data-stu-id="b8ba7-102">MailBnfHelper class</span></span>

<span data-ttu-id="b8ba7-103">Содержит служебные методы для синтаксического анализа строк в формате сообщений Интернета.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-103">Contains utility methods for parsing internet message-formatted strings.</span></span> <span data-ttu-id="b8ba7-104">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> <span data-ttu-id="b8ba7-105">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b8ba7-106">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="ascii7bitmaxvalue-field"></a><span data-ttu-id="b8ba7-107">Поле Ascii7bitMaxValue</span><span class="sxs-lookup"><span data-stu-id="b8ba7-107">Ascii7bitMaxValue field</span></span>

<span data-ttu-id="b8ba7-108">Представляет максимальное 7-разрядное значение ASCII.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-108">Represents the maximum 7-bit Ascii value.</span></span>

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a><span data-ttu-id="b8ba7-109">Поле аТекст</span><span class="sxs-lookup"><span data-stu-id="b8ba7-109">Atext field</span></span>

<span data-ttu-id="b8ba7-110">Представляет символы, разрешенные в атомах.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-110">Represents the characters allowed in atoms.</span></span>

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a><span data-ttu-id="b8ba7-111">Поле CR</span><span class="sxs-lookup"><span data-stu-id="b8ba7-111">CR field</span></span>

<span data-ttu-id="b8ba7-112">Представляет символ возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-112">Represents the carriage-return character.</span></span>

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a><span data-ttu-id="b8ba7-113">Поле столбец ctext</span><span class="sxs-lookup"><span data-stu-id="b8ba7-113">Ctext field</span></span>

<span data-ttu-id="b8ba7-114">Представляет символы, разрешенные внутри комментариев.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-114">Represents the characters allowed inside of comments.</span></span>

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a><span data-ttu-id="b8ba7-115">Поле точки</span><span class="sxs-lookup"><span data-stu-id="b8ba7-115">Dot field</span></span>

<span data-ttu-id="b8ba7-116">Представляет символ полной позиции ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="b8ba7-116">Represents the full-stop character (`.`).</span></span>

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a><span data-ttu-id="b8ba7-117">Поле Ендкоммент</span><span class="sxs-lookup"><span data-stu-id="b8ba7-117">EndComment field</span></span>

<span data-ttu-id="b8ba7-118">Представляет символ, указывающий конец комментария.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-118">Represents the character that specifies the end of a comment.</span></span>

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a><span data-ttu-id="b8ba7-119">Поле LF</span><span class="sxs-lookup"><span data-stu-id="b8ba7-119">LF field</span></span>

<span data-ttu-id="b8ba7-120">Представляет символ перевода строки.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-120">Represents the line-feed character.</span></span>

```csharp
internal static readonly char LF
```

## <a name="space-field"></a><span data-ttu-id="b8ba7-121">Поле пробела</span><span class="sxs-lookup"><span data-stu-id="b8ba7-121">Space field</span></span>

<span data-ttu-id="b8ba7-122">Представляет символ пробела.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-122">Represents the space character.</span></span>

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a><span data-ttu-id="b8ba7-123">Поле Старткоммент</span><span class="sxs-lookup"><span data-stu-id="b8ba7-123">StartComment field</span></span>

<span data-ttu-id="b8ba7-124">Представляет символ, указывающий начало комментария.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-124">Represents the character that specifies the start of a comment.</span></span>

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a><span data-ttu-id="b8ba7-125">Поле вкладки</span><span class="sxs-lookup"><span data-stu-id="b8ba7-125">Tab field</span></span>

<span data-ttu-id="b8ba7-126">Представляет символ табуляции.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-126">Represents the tab character.</span></span>

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a><span data-ttu-id="b8ba7-127">Требования</span><span class="sxs-lookup"><span data-stu-id="b8ba7-127">Requirements</span></span>

<span data-ttu-id="b8ba7-128">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b8ba7-128">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b8ba7-129">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="b8ba7-129">**Assembly:** System (in System.dll)</span></span>
