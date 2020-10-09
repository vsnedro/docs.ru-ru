---
ms.openlocfilehash: d61a3b3dd855d783d7bff7cb74e5b84969e60860
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608056"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="e5ea9-101">Неправильная составная обработка ASP.NET может привести к потере данных формы.</span><span class="sxs-lookup"><span data-stu-id="e5ea9-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="e5ea9-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e5ea9-102">Details</span></span>

<span data-ttu-id="e5ea9-103">В приложениях, предназначенных для .NET Framework 4.7.2 и более ранних версий, ASP.NET может неправильно выполнять синтаксический анализ составных граничных значений, и это приведет к тому, что данные формы будут недоступны во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="e5ea9-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.NET might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="e5ea9-104">Приложения, предназначенные для .NET Framework 4.8 или более поздних версий, правильно выполняют синтаксический анализ составных данных, поэтому значения формы доступны во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="e5ea9-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e5ea9-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e5ea9-105">Suggestion</span></span>

<span data-ttu-id="e5ea9-106">Начиная с приложений, выполняемых на .NET Framework 4.8, при нацеливании на .NET Framework 4.8 или более поздней версии с помощью элемента <code>targetFrameworkVersion</code> поведение по умолчанию меняется на удаление разделителей.</span><span class="sxs-lookup"><span data-stu-id="e5ea9-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="e5ea9-107">При нацеливании на предыдущие версии платформы или если <code>targetFrameworkVersion</code> не используется, конечные разделители для некоторых значений по-прежнему возвращаются. Этим поведением можно также явно управлять при помощи <code>appSetting</code>:</span><span class="sxs-lookup"><span data-stu-id="e5ea9-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="e5ea9-108">name</span><span class="sxs-lookup"><span data-stu-id="e5ea9-108">Name</span></span>    | <span data-ttu-id="e5ea9-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e5ea9-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e5ea9-110">Область</span><span class="sxs-lookup"><span data-stu-id="e5ea9-110">Scope</span></span>   |<span data-ttu-id="e5ea9-111">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="e5ea9-111">Unknown</span></span>|
|<span data-ttu-id="e5ea9-112">Version</span><span class="sxs-lookup"><span data-stu-id="e5ea9-112">Version</span></span>|<span data-ttu-id="e5ea9-113">4.8</span><span class="sxs-lookup"><span data-stu-id="e5ea9-113">4.8</span></span>|
|<span data-ttu-id="e5ea9-114">Type</span><span class="sxs-lookup"><span data-stu-id="e5ea9-114">Type</span></span>|<span data-ttu-id="e5ea9-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e5ea9-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e5ea9-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e5ea9-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
