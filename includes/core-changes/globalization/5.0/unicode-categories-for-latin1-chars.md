---
ms.openlocfilehash: 48d2f1b5fa2eced30d3c9fb65804268904f11ab8
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065072"
---
### <a name="unicode-category-changed-for-some-latin-1-characters"></a><span data-ttu-id="c13c4-101">Для некоторых символов латиницы-1 изменилась категория Юникода</span><span class="sxs-lookup"><span data-stu-id="c13c4-101">Unicode category changed for some Latin-1 characters</span></span>

<span data-ttu-id="c13c4-102">Методы <xref:System.Char> теперь возвращают правильную категорию Юникода для символов в диапазоне латиницы-1.</span><span class="sxs-lookup"><span data-stu-id="c13c4-102"><xref:System.Char> methods now return the correct Unicode category for characters in the Latin-1 range.</span></span> <span data-ttu-id="c13c4-103">Категория соответствует стандарту Юникода.</span><span class="sxs-lookup"><span data-stu-id="c13c4-103">The category matches that of the Unicode standard.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c13c4-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="c13c4-104">Change description</span></span>

<span data-ttu-id="c13c4-105">В предыдущих версиях .NET методы <xref:System.Char> использовали фиксированный список категорий Юникода для символов в диапазоне латиницы-1.</span><span class="sxs-lookup"><span data-stu-id="c13c4-105">In previous .NET versions, <xref:System.Char> methods used a fixed list of Unicode categories for characters in the Latin-1 range.</span></span> <span data-ttu-id="c13c4-106">Однако в стандарте Юникода категории некоторых из этих символов были изменены, так как эти API были реализованы, что создает расхождение.</span><span class="sxs-lookup"><span data-stu-id="c13c4-106">However, the Unicode standard has changed the categories of some of these characters since those APIs were implemented, creating a discrepancy.</span></span> <span data-ttu-id="c13c4-107">Кроме того, существует несоответствие между API <xref:System.Char> и <xref:System.Globalization.CharUnicodeInfo>, которые следуют стандарту Юникода.</span><span class="sxs-lookup"><span data-stu-id="c13c4-107">In addition, there was also a discrepancy between <xref:System.Char> and <xref:System.Globalization.CharUnicodeInfo> APIs, which follow the Unicode standard.</span></span> <span data-ttu-id="c13c4-108">В .NET 5.0 и более поздних версиях методы <xref:System.Char> используют и возвращают категорию Юникода, которая соответствует стандарту Юникода для всех символов.</span><span class="sxs-lookup"><span data-stu-id="c13c4-108">In .NET 5.0 and later versions, <xref:System.Char> methods use and return the Unicode category that matches the Unicode standard for all characters.</span></span>

<span data-ttu-id="c13c4-109">В следующей таблице показаны символы, чьи категории Юникода изменились в .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="c13c4-109">The following table shows the characters whose Unicode categories have changed in .NET 5.0:</span></span>

| <span data-ttu-id="c13c4-110">Символ</span><span class="sxs-lookup"><span data-stu-id="c13c4-110">Character</span></span>    | <span data-ttu-id="c13c4-111">Категория Юникода</span><span class="sxs-lookup"><span data-stu-id="c13c4-111">Unicode category</span></span><br><span data-ttu-id="c13c4-112">в предыдущих версиях .NET</span><span class="sxs-lookup"><span data-stu-id="c13c4-112">in previous .NET versions</span></span> | <span data-ttu-id="c13c4-113">Категория Юникода</span><span class="sxs-lookup"><span data-stu-id="c13c4-113">Unicode category</span></span><br><span data-ttu-id="c13c4-114">в .NET 5.0 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="c13c4-114">in .NET 5.0 and later versions</span></span> |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| <span data-ttu-id="c13c4-115">§ (\u00a7)</span><span class="sxs-lookup"><span data-stu-id="c13c4-115">§ (\u00a7)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="c13c4-116">ª (\u00aa)</span><span class="sxs-lookup"><span data-stu-id="c13c4-116">ª (\u00aa)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |
| <span data-ttu-id="c13c4-117">SHY (\u00ad)</span><span class="sxs-lookup"><span data-stu-id="c13c4-117">SHY (\u00ad)</span></span> | `DashPunctuation`                             | `Format`                                           |
| <span data-ttu-id="c13c4-118">¶ (\u00b6)</span><span class="sxs-lookup"><span data-stu-id="c13c4-118">¶ (\u00b6)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="c13c4-119">º (\u00ba)</span><span class="sxs-lookup"><span data-stu-id="c13c4-119">º (\u00ba)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |

#### <a name="version-introduced"></a><span data-ttu-id="c13c4-120">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c13c4-120">Version introduced</span></span>

<span data-ttu-id="c13c4-121">.NET 5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="c13c4-121">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c13c4-122">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="c13c4-122">Recommended action</span></span>

<span data-ttu-id="c13c4-123">Если у вас есть код, который получает категорию символов Юникода с помощью класса <xref:System.Char> и предполагает, что категория никогда не изменится, может потребоваться обновить его.</span><span class="sxs-lookup"><span data-stu-id="c13c4-123">If you have any code that gets the Unicode character category by using the <xref:System.Char> class and assumes the category will never change, you may need to update it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c13c4-124">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="c13c4-124">Reason for change</span></span>

<span data-ttu-id="c13c4-125">Это изменение было сделано таким образом, чтобы категории, возвращаемые типом <xref:System.Char>, соответствовали стандарту Unicode и типу <xref:System.Globalization.CharUnicodeInfo>.</span><span class="sxs-lookup"><span data-stu-id="c13c4-125">This change was made so that the categories returned by the <xref:System.Char> type are consistent with both the Unicode standard and the <xref:System.Globalization.CharUnicodeInfo> type.</span></span>

#### <a name="category"></a><span data-ttu-id="c13c4-126">Категория</span><span class="sxs-lookup"><span data-stu-id="c13c4-126">Category</span></span>

- <span data-ttu-id="c13c4-127">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="c13c4-127">Core .NET libraries</span></span>
- <span data-ttu-id="c13c4-128">Глобализация</span><span class="sxs-lookup"><span data-stu-id="c13c4-128">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c13c4-129">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c13c4-129">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

<span data-ttu-id="c13c4-130">Кроме того, это изменение затрагивает любой класс, зависящий от <xref:System.Char> для получения категории символов Юникода, например <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="c13c4-130">Additionally, any class that depends on <xref:System.Char> to obtain the Unicode character category, for example, <xref:System.Text.RegularExpressions.Regex>, is affected by this change.</span></span>

<!--

#### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

-->
