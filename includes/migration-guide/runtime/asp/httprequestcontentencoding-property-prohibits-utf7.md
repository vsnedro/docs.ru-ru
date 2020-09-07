---
ms.openlocfilehash: cf34c5df1badcfd86d8a07bafdf1b759234712e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496914"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="5a578-101">Свойство HttpRequest.ContentEncoding запрещает кодировку UTF7</span><span class="sxs-lookup"><span data-stu-id="5a578-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="5a578-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5a578-102">Details</span></span>

<span data-ttu-id="5a578-103">Начиная с .NET Framework 4.5 кодировка UTF-7 запрещена в теле <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5a578-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="5a578-104">Данные для приложений, которые зависят от поступающих данных UTF-7, в некоторых случаях декодируются неверно.</span><span class="sxs-lookup"><span data-stu-id="5a578-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5a578-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="5a578-105">Suggestion</span></span>

<span data-ttu-id="5a578-106">В идеальном случае приложения необходимо обновить, чтобы они не использовали кодировку UTF-7 в <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5a578-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="5a578-107">Кроме того, устаревшее поведение можно восстановить с помощью атрибута <code>aspnet:AllowUtf7RequestContentEncoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5a578-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="5a578-108">name</span><span class="sxs-lookup"><span data-stu-id="5a578-108">Name</span></span>    | <span data-ttu-id="5a578-109">Значение</span><span class="sxs-lookup"><span data-stu-id="5a578-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5a578-110">Область</span><span class="sxs-lookup"><span data-stu-id="5a578-110">Scope</span></span>   |<span data-ttu-id="5a578-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="5a578-111">Edge</span></span>|
|<span data-ttu-id="5a578-112">Version</span><span class="sxs-lookup"><span data-stu-id="5a578-112">Version</span></span>|<span data-ttu-id="5a578-113">4.5</span><span class="sxs-lookup"><span data-stu-id="5a578-113">4.5</span></span>|
|<span data-ttu-id="5a578-114">Type</span><span class="sxs-lookup"><span data-stu-id="5a578-114">Type</span></span>|<span data-ttu-id="5a578-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="5a578-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5a578-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5a578-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.ContentEncoding`

-->
