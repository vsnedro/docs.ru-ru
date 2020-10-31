---
title: Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET], retrieving
- time zones [.NET], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: 598cd631fab1ddc115bc6153580351b1dc14d5bf
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063889"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="bca39-102">Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов</span><span class="sxs-lookup"><span data-stu-id="bca39-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="bca39-103"><xref:System.TimeZoneInfo>Класс предоставляет два свойства, <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A> , которые предоставляют коду доступ к предопределенным объектам часового пояса.</span><span class="sxs-lookup"><span data-stu-id="bca39-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="bca39-104">В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.</span><span class="sxs-lookup"><span data-stu-id="bca39-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="bca39-105">Получение объекта TimeZoneInfo времени UTC</span><span class="sxs-lookup"><span data-stu-id="bca39-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="bca39-106">Используйте `static` свойство ( `Shared` в Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> для доступа к всеобщему скоординированному времени.</span><span class="sxs-lookup"><span data-stu-id="bca39-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="bca39-107">Вместо того чтобы назначать <xref:System.TimeZoneInfo> объект, возвращаемый свойством, в объектную переменную, продолжайте обращаться к времени в формате UTC через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="bca39-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="bca39-108">Получение местного часового пояса</span><span class="sxs-lookup"><span data-stu-id="bca39-108">To access the local time zone</span></span>

1. <span data-ttu-id="bca39-109">Используйте `static` свойство ( `Shared` в Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> для доступа к часовому поясу локальной системы.</span><span class="sxs-lookup"><span data-stu-id="bca39-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="bca39-110">Вместо того чтобы назначать <xref:System.TimeZoneInfo> объект, возвращаемый свойством, в объектную переменную, продолжайте обращаться к местному часовому поясу через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="bca39-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="bca39-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bca39-111">Example</span></span>

<span data-ttu-id="bca39-112">В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.</span><span class="sxs-lookup"><span data-stu-id="bca39-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="bca39-113">Необходимо всегда обращаться к локальному часовому поясу через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство, а не назначать местный часовой пояс <xref:System.TimeZoneInfo> переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="bca39-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="bca39-114">Аналогичным образом следует всегда обращаться к всеобщему скоординированному времени через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство, не назначив часовой пояс в <xref:System.TimeZoneInfo> объектную переменную.</span><span class="sxs-lookup"><span data-stu-id="bca39-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="bca39-115">Это предотвращает <xref:System.TimeZoneInfo> недействительность аннулирования переменной объекта при вызове <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метода.</span><span class="sxs-lookup"><span data-stu-id="bca39-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="bca39-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bca39-116">Compiling the code</span></span>

<span data-ttu-id="bca39-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="bca39-117">This example requires:</span></span>

- <span data-ttu-id="bca39-118">, Что <xref:System> пространство имен должно быть импортировано с помощью `using` оператора (требуется в коде C#).</span><span class="sxs-lookup"><span data-stu-id="bca39-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="bca39-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bca39-119">See also</span></span>

- [<span data-ttu-id="bca39-120">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="bca39-120">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="bca39-121">Поиск часового пояса, заданного в локальной системе</span><span class="sxs-lookup"><span data-stu-id="bca39-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="bca39-122">Как создать объект TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="bca39-122">How to: Instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)
