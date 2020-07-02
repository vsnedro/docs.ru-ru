---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621191"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="22b25-101">Теперь поддерживаются категории стандартной версии Юникода 8.0</span><span class="sxs-lookup"><span data-stu-id="22b25-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="22b25-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="22b25-102">Details</span></span>

<span data-ttu-id="22b25-103">В .NET Framework 4.6.2 данные Юникода были обновлены со стандартной версии 6.3 до версии 8.0.</span><span class="sxs-lookup"><span data-stu-id="22b25-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="22b25-104">При запросе категорий символов Юникода в .NET Framework 4.6.2 некоторые результаты могут не соответствовать результатам в предыдущих версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22b25-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="22b25-105">Это изменение в первую очередь влияет на слоги языка чероки, а также знаки гласных и обозначения тонов в новой письменности Тай-Лю.</span><span class="sxs-lookup"><span data-stu-id="22b25-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="22b25-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="22b25-106">Suggestion</span></span>

<span data-ttu-id="22b25-107">Просмотрите код и удалите или измените логику, зависящую от жестко заданных категорий символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="22b25-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="22b25-108">name</span><span class="sxs-lookup"><span data-stu-id="22b25-108">Name</span></span>    | <span data-ttu-id="22b25-109">Значение</span><span class="sxs-lookup"><span data-stu-id="22b25-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="22b25-110">Область</span><span class="sxs-lookup"><span data-stu-id="22b25-110">Scope</span></span>   |<span data-ttu-id="22b25-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="22b25-111">Minor</span></span>|
|<span data-ttu-id="22b25-112">Version</span><span class="sxs-lookup"><span data-stu-id="22b25-112">Version</span></span>|<span data-ttu-id="22b25-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="22b25-113">4.6.2</span></span>|
|<span data-ttu-id="22b25-114">Type</span><span class="sxs-lookup"><span data-stu-id="22b25-114">Type</span></span>|<span data-ttu-id="22b25-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="22b25-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="22b25-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="22b25-116">Affected APIs</span></span>

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
