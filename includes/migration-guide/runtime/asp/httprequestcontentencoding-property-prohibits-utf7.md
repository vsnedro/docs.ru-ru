---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620135"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="eda1a-101">Свойство HttpRequest.ContentEncoding запрещает кодировку UTF7</span><span class="sxs-lookup"><span data-stu-id="eda1a-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="eda1a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="eda1a-102">Details</span></span>

<span data-ttu-id="eda1a-103">Начиная с .NET Framework 4.5 кодировка UTF-7 запрещена в теле <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="eda1a-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="eda1a-104">Данные для приложений, которые зависят от поступающих данных UTF-7, в некоторых случаях декодируются неверно.</span><span class="sxs-lookup"><span data-stu-id="eda1a-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eda1a-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="eda1a-105">Suggestion</span></span>

<span data-ttu-id="eda1a-106">В идеальном случае приложения необходимо обновить, чтобы они не использовали кодировку UTF-7 в <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="eda1a-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="eda1a-107">Кроме того, устаревшее поведение можно восстановить с помощью атрибута <code>aspnet:AllowUtf7RequestContentEncoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="eda1a-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="eda1a-108">name</span><span class="sxs-lookup"><span data-stu-id="eda1a-108">Name</span></span>    | <span data-ttu-id="eda1a-109">Значение</span><span class="sxs-lookup"><span data-stu-id="eda1a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eda1a-110">Область</span><span class="sxs-lookup"><span data-stu-id="eda1a-110">Scope</span></span>   |<span data-ttu-id="eda1a-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="eda1a-111">Edge</span></span>|
|<span data-ttu-id="eda1a-112">Version</span><span class="sxs-lookup"><span data-stu-id="eda1a-112">Version</span></span>|<span data-ttu-id="eda1a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="eda1a-113">4.5</span></span>|
|<span data-ttu-id="eda1a-114">Type</span><span class="sxs-lookup"><span data-stu-id="eda1a-114">Type</span></span>|<span data-ttu-id="eda1a-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="eda1a-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eda1a-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="eda1a-116">Affected APIs</span></span>

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
