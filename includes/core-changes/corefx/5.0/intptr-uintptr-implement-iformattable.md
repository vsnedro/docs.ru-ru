---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024707"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="df284-101">IntPtr и UIntPtr реализуют IFormattable</span><span class="sxs-lookup"><span data-stu-id="df284-101">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="df284-102"><xref:System.IntPtr> и <xref:System.UIntPtr> теперь реализуют <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="df284-102"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="df284-103">Функции, которые проверяют наличие поддержки <xref:System.IFormattable>, теперь могут возвращать разные результаты для этих типов, поскольку они могут передавать описатель формата, а также язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="df284-103">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

#### <a name="change-description"></a><span data-ttu-id="df284-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="df284-104">Change description</span></span>

<span data-ttu-id="df284-105">В предыдущих версиях .NET <xref:System.IntPtr> и <xref:System.UIntPtr> не реализуют <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="df284-105">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="df284-106">Функции, которые проверяют наличие поддержки <xref:System.IFormattable>, могут возвращаться к простому вызову <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> или <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, что означает, что описатели формата, а также языки и региональные параметры не учитываются.</span><span class="sxs-lookup"><span data-stu-id="df284-106">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="df284-107">В .NET 5.0 и более поздних версиях <xref:System.IntPtr> и <xref:System.UIntPtr> реализуют <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="df284-107">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="df284-108">Функции, которые проверяют наличие поддержки <xref:System.IFormattable>, теперь могут возвращать разные результаты для этих типов, поскольку они могут передавать описатель формата, а также язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="df284-108">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="df284-109">Это изменение влияет на такие сценарии, как интерполяция строк и <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df284-109">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="df284-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="df284-110">Reason for change</span></span>

<span data-ttu-id="df284-111"><xref:System.IntPtr> и <xref:System.UIntPtr> теперь имеют языковую поддержку в C# помощью ключевых слов `nint` и `nuint`.</span><span class="sxs-lookup"><span data-stu-id="df284-111"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="df284-112">Резервные типы были обновлены для обеспечения ближайшей четности (по возможности) с функциями, предоставляемыми другими примитивными типами, такими как <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df284-112">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="df284-113">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="df284-113">Version introduced</span></span>

<span data-ttu-id="df284-114">5.0, предварительная версия 4</span><span class="sxs-lookup"><span data-stu-id="df284-114">5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="df284-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="df284-115">Recommended action</span></span>

<span data-ttu-id="df284-116">Если вы не хотите использовать описатель формата или настраиваемые язык и региональные параметры при отображении значений этих типов, можно вызвать перегрузки <xref:System.IntPtr.ToString?displayProperty=nameWithType> и <xref:System.UIntPtr.ToString?displayProperty=nameWithType> для `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="df284-116">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

#### <a name="category"></a><span data-ttu-id="df284-117">Категория</span><span class="sxs-lookup"><span data-stu-id="df284-117">Category</span></span>

<span data-ttu-id="df284-118">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="df284-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="df284-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="df284-119">Affected APIs</span></span>

<span data-ttu-id="df284-120">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="df284-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
