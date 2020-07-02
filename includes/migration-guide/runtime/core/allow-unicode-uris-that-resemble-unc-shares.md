---
ms.openlocfilehash: 3e8601ba76dfb05e3d70b3af7440bd7e228768d0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621168"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="118cb-101">Разрешение Юникода в URI, которые напоминают общие папки UNC</span><span class="sxs-lookup"><span data-stu-id="118cb-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="118cb-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="118cb-102">Details</span></span>

<span data-ttu-id="118cb-103">В <xref:System.Uri?displayProperty=fullName> формирование URI файла, содержащего UNC-имя общей папки и символы Юникода, больше не приводит к созданию URI с недопустимым внутренним состоянием.</span><span class="sxs-lookup"><span data-stu-id="118cb-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="118cb-104">Это поведение изменится, только если выполняются все указанные ниже условия:</span><span class="sxs-lookup"><span data-stu-id="118cb-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="118cb-105">URI имеет схему <code>file:</code> и за ним следуют четыре или более косых черт;</span><span class="sxs-lookup"><span data-stu-id="118cb-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="118cb-106">имя узла начинается с символа подчеркивания или другого незарезервированного символа;</span><span class="sxs-lookup"><span data-stu-id="118cb-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="118cb-107">URI содержит символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="118cb-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="118cb-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="118cb-108">Suggestion</span></span>

<span data-ttu-id="118cb-109">Приложения, работающие с URI, в обязательном порядке содержащими символы Юникода, потенциально могли использовать это поведение для запрета ссылок на общие папки UNC.</span><span class="sxs-lookup"><span data-stu-id="118cb-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="118cb-110">Эти приложения должны использовать <xref:System.Uri.IsUnc>.</span><span class="sxs-lookup"><span data-stu-id="118cb-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="118cb-111">name</span><span class="sxs-lookup"><span data-stu-id="118cb-111">Name</span></span>    | <span data-ttu-id="118cb-112">Значение</span><span class="sxs-lookup"><span data-stu-id="118cb-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="118cb-113">Область</span><span class="sxs-lookup"><span data-stu-id="118cb-113">Scope</span></span>   |<span data-ttu-id="118cb-114">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="118cb-114">Edge</span></span>|
|<span data-ttu-id="118cb-115">Version</span><span class="sxs-lookup"><span data-stu-id="118cb-115">Version</span></span>|<span data-ttu-id="118cb-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="118cb-116">4.7.2</span></span>|
|<span data-ttu-id="118cb-117">Type</span><span class="sxs-lookup"><span data-stu-id="118cb-117">Type</span></span>|<span data-ttu-id="118cb-118">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="118cb-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="118cb-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="118cb-119">Affected APIs</span></span>

-<xref:System.Uri?displayProperty=nameWithType></li></ul>|
