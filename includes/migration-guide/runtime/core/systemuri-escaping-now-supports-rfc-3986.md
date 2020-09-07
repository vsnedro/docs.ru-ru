---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496347"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="21da4-101">Экранирование System.Uri теперь поддерживает RFC 3986</span><span class="sxs-lookup"><span data-stu-id="21da4-101">System.Uri escaping now supports RFC 3986</span></span>

#### <a name="details"></a><span data-ttu-id="21da4-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="21da4-102">Details</span></span>

<span data-ttu-id="21da4-103">Экранирование URI изменилось в .NET Framework 4.5 для поддержки [RFC 3986](https://tools.ietf.org/html/rfc3986).</span><span class="sxs-lookup"><span data-stu-id="21da4-103">URI escaping has changed in .NET Framework 4.5 to support [RFC 3986](https://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="21da4-104">Внесены следующие конкретные изменения.</span><span class="sxs-lookup"><span data-stu-id="21da4-104">Specific changes include:</span></span><ul><li><span data-ttu-id="21da4-105">Метод <xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> преобразует в escape-последовательность зарезервированные символы в соответствии с RFC 3986.</span><span class="sxs-lookup"><span data-stu-id="21da4-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="21da4-106">Метод <xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> не преобразует в escape-последовательность зарезервированные символы.</span><span class="sxs-lookup"><span data-stu-id="21da4-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> does not escape reserved characters.</span></span></li><li><span data-ttu-id="21da4-107">Метод <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> не создает исключение, если ему встречается неверная escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="21da4-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="21da4-108">Преобразование незарезервированных символов в escape-символы отменяется.</span><span class="sxs-lookup"><span data-stu-id="21da4-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="21da4-109">Предложение</span><span class="sxs-lookup"><span data-stu-id="21da4-109">Suggestion</span></span>

<ul><li><span data-ttu-id="21da4-110">Обновления приложений не зависят от <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> для создания исключения в случае недопустимой escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="21da4-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="21da4-111">Такие последовательности должны обнаруживаться сразу же.</span><span class="sxs-lookup"><span data-stu-id="21da4-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="21da4-112">Аналогичным образом ожидается, что экранированные и неэкранированные URI и строки данных могут отличаться в .NET Framework 4.0 и .NET Framework 4.5 и их не следует сравнивать в версиях .NET напрямую.</span><span class="sxs-lookup"><span data-stu-id="21da4-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET Framework 4.0 and .NET Framework 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="21da4-113">Их необходимо проанализировать и нормализовать в одной версии .NET перед выполнением каких-либо сравнений.</span><span class="sxs-lookup"><span data-stu-id="21da4-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>

| <span data-ttu-id="21da4-114">name</span><span class="sxs-lookup"><span data-stu-id="21da4-114">Name</span></span>    | <span data-ttu-id="21da4-115">Значение</span><span class="sxs-lookup"><span data-stu-id="21da4-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="21da4-116">Область</span><span class="sxs-lookup"><span data-stu-id="21da4-116">Scope</span></span>   |<span data-ttu-id="21da4-117">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="21da4-117">Minor</span></span>|
|<span data-ttu-id="21da4-118">Version</span><span class="sxs-lookup"><span data-stu-id="21da4-118">Version</span></span>|<span data-ttu-id="21da4-119">4.5</span><span class="sxs-lookup"><span data-stu-id="21da4-119">4.5</span></span>|
|<span data-ttu-id="21da4-120">Type</span><span class="sxs-lookup"><span data-stu-id="21da4-120">Type</span></span>|<span data-ttu-id="21da4-121">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="21da4-121">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="21da4-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="21da4-122">Affected APIs</span></span>

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
