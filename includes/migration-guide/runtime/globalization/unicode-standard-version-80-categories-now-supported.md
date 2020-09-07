---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497426"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="bec08-101">Теперь поддерживаются категории стандартной версии Юникода 8.0</span><span class="sxs-lookup"><span data-stu-id="bec08-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="bec08-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="bec08-102">Details</span></span>

<span data-ttu-id="bec08-103">В .NET Framework 4.6.2 данные Юникода были обновлены со стандартной версии 6.3 до версии 8.0.</span><span class="sxs-lookup"><span data-stu-id="bec08-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="bec08-104">При запросе категорий символов Юникода в .NET Framework 4.6.2 некоторые результаты могут не соответствовать результатам в предыдущих версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bec08-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="bec08-105">Это изменение в первую очередь влияет на слоги языка чероки, а также знаки гласных и обозначения тонов в новой письменности Тай-Лю.</span><span class="sxs-lookup"><span data-stu-id="bec08-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bec08-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="bec08-106">Suggestion</span></span>

<span data-ttu-id="bec08-107">Просмотрите код и удалите или измените логику, зависящую от жестко заданных категорий символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="bec08-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="bec08-108">Имя</span><span class="sxs-lookup"><span data-stu-id="bec08-108">Name</span></span>    | <span data-ttu-id="bec08-109">Значение</span><span class="sxs-lookup"><span data-stu-id="bec08-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bec08-110">Область</span><span class="sxs-lookup"><span data-stu-id="bec08-110">Scope</span></span>   |<span data-ttu-id="bec08-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="bec08-111">Minor</span></span>|
|<span data-ttu-id="bec08-112">Version</span><span class="sxs-lookup"><span data-stu-id="bec08-112">Version</span></span>|<span data-ttu-id="bec08-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="bec08-113">4.6.2</span></span>|
|<span data-ttu-id="bec08-114">Type</span><span class="sxs-lookup"><span data-stu-id="bec08-114">Type</span></span>|<span data-ttu-id="bec08-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="bec08-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bec08-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="bec08-116">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
