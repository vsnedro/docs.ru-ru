---
ms.openlocfilehash: 14581b193fc000c7f805a0602e191cad688c014a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496424"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="66afe-101">Теперь в персидском календаре используется алгоритм солнечного календаря хиджры</span><span class="sxs-lookup"><span data-stu-id="66afe-101">Persian calendar now uses the Hijri solar algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="66afe-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="66afe-102">Details</span></span>

<span data-ttu-id="66afe-103">Начиная с .NET Framework 4.6 класс <xref:System.Globalization.PersianCalendar?displayProperty=fullName> использует алгоритм солнечного календаря хиджры.</span><span class="sxs-lookup"><span data-stu-id="66afe-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="66afe-104">Начиная с .NET Framework 4.6 при преобразовании дат между <xref:System.Globalization.PersianCalendar?displayProperty=fullName> и другими календарями может быть получен немного другой результат для дат, ранее 1800 г. или позднее 2023 г. (по григорианскому календарю). Кроме того, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> теперь <code>March 22, 0622</code> вместо <code>March 21, 0622</code>.</span><span class="sxs-lookup"><span data-stu-id="66afe-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="66afe-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="66afe-105">Suggestion</span></span>

<span data-ttu-id="66afe-106">Имейте в виду, что при использовании персидского календаря в .NET Framework 4.6 некоторые даты в прошлом или будущем могут несколько отличаться.</span><span class="sxs-lookup"><span data-stu-id="66afe-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="66afe-107">Кроме того, даты, сериализуемые между процессами, которые могут выполняться в различных версиях .NET Framework, не следует хранить в виде строк дат персидского календаря (поскольку эти значения могут быть разными).</span><span class="sxs-lookup"><span data-stu-id="66afe-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>

| <span data-ttu-id="66afe-108">name</span><span class="sxs-lookup"><span data-stu-id="66afe-108">Name</span></span>    | <span data-ttu-id="66afe-109">Значение</span><span class="sxs-lookup"><span data-stu-id="66afe-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="66afe-110">Область</span><span class="sxs-lookup"><span data-stu-id="66afe-110">Scope</span></span>   |<span data-ttu-id="66afe-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="66afe-111">Minor</span></span>|
|<span data-ttu-id="66afe-112">Version</span><span class="sxs-lookup"><span data-stu-id="66afe-112">Version</span></span>|<span data-ttu-id="66afe-113">4.6</span><span class="sxs-lookup"><span data-stu-id="66afe-113">4.6</span></span>|
|<span data-ttu-id="66afe-114">Type</span><span class="sxs-lookup"><span data-stu-id="66afe-114">Type</span></span>|<span data-ttu-id="66afe-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="66afe-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="66afe-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="66afe-116">Affected APIs</span></span>

- <xref:System.Globalization.PersianCalendar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Globalization.PersianCalendar`

-->
