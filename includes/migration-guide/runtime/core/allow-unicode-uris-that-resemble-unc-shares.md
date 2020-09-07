---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496411"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="d6bce-101">Разрешение Юникода в URI, которые напоминают общие папки UNC</span><span class="sxs-lookup"><span data-stu-id="d6bce-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="d6bce-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d6bce-102">Details</span></span>

<span data-ttu-id="d6bce-103">В <xref:System.Uri?displayProperty=fullName> формирование URI файла, содержащего UNC-имя общей папки и символы Юникода, больше не приводит к созданию URI с недопустимым внутренним состоянием.</span><span class="sxs-lookup"><span data-stu-id="d6bce-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="d6bce-104">Это поведение изменится, только если выполняются все указанные ниже условия:</span><span class="sxs-lookup"><span data-stu-id="d6bce-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="d6bce-105">URI имеет схему <code>file:</code> и за ним следуют четыре или более косых черт;</span><span class="sxs-lookup"><span data-stu-id="d6bce-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="d6bce-106">имя узла начинается с символа подчеркивания или другого незарезервированного символа;</span><span class="sxs-lookup"><span data-stu-id="d6bce-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="d6bce-107">URI содержит символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="d6bce-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="d6bce-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="d6bce-108">Suggestion</span></span>

<span data-ttu-id="d6bce-109">Приложения, работающие с URI, в обязательном порядке содержащими символы Юникода, потенциально могли использовать это поведение для запрета ссылок на общие папки UNC.</span><span class="sxs-lookup"><span data-stu-id="d6bce-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="d6bce-110">Эти приложения должны использовать <xref:System.Uri.IsUnc>.</span><span class="sxs-lookup"><span data-stu-id="d6bce-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="d6bce-111">name</span><span class="sxs-lookup"><span data-stu-id="d6bce-111">Name</span></span>    | <span data-ttu-id="d6bce-112">Значение</span><span class="sxs-lookup"><span data-stu-id="d6bce-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d6bce-113">Область</span><span class="sxs-lookup"><span data-stu-id="d6bce-113">Scope</span></span>   |<span data-ttu-id="d6bce-114">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="d6bce-114">Edge</span></span>|
|<span data-ttu-id="d6bce-115">Version</span><span class="sxs-lookup"><span data-stu-id="d6bce-115">Version</span></span>|<span data-ttu-id="d6bce-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d6bce-116">4.7.2</span></span>|
|<span data-ttu-id="d6bce-117">Type</span><span class="sxs-lookup"><span data-stu-id="d6bce-117">Type</span></span>|<span data-ttu-id="d6bce-118">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d6bce-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d6bce-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d6bce-119">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
