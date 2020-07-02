---
ms.openlocfilehash: 135d59de135c8416d384b221379f912c8a9172ad
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622070"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="f6ce6-101">Неправильная составная обработка ASP.NET может привести к потере данных формы.</span><span class="sxs-lookup"><span data-stu-id="f6ce6-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="f6ce6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f6ce6-102">Details</span></span>

<span data-ttu-id="f6ce6-103">В приложениях, предназначенных для .NET Framework 4.7.2 и более ранних версий, ASP.Net может неправильно выполнять синтаксический анализ составных граничных значений, и это приведет к тому, что данные формы будут недоступны во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="f6ce6-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.Net might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="f6ce6-104">Приложения, предназначенные для .NET Framework 4.8 или более поздних версий, правильно выполняют синтаксический анализ составных данных, поэтому значения формы доступны во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="f6ce6-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f6ce6-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="f6ce6-105">Suggestion</span></span>

<span data-ttu-id="f6ce6-106">Начиная с приложений, выполняемых на .NET Framework 4.8, при нацеливании на .NET Framework 4.8 или более поздней версии с помощью элемента <code>targetFrameworkVersion</code> поведение по умолчанию меняется на удаление разделителей.</span><span class="sxs-lookup"><span data-stu-id="f6ce6-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="f6ce6-107">При нацеливании на предыдущие версии платформы или если <code>targetFrameworkVersion</code> не используется, конечные разделители для некоторых значений по-прежнему возвращаются. Этим поведением можно также явно управлять при помощи <code>appSetting</code>:</span><span class="sxs-lookup"><span data-stu-id="f6ce6-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f6ce6-108">name</span><span class="sxs-lookup"><span data-stu-id="f6ce6-108">Name</span></span>    | <span data-ttu-id="f6ce6-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f6ce6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f6ce6-110">Область</span><span class="sxs-lookup"><span data-stu-id="f6ce6-110">Scope</span></span>   |<span data-ttu-id="f6ce6-111">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="f6ce6-111">Unknown</span></span>|
|<span data-ttu-id="f6ce6-112">Version</span><span class="sxs-lookup"><span data-stu-id="f6ce6-112">Version</span></span>|<span data-ttu-id="f6ce6-113">4.8</span><span class="sxs-lookup"><span data-stu-id="f6ce6-113">4.8</span></span>|
|<span data-ttu-id="f6ce6-114">Type</span><span class="sxs-lookup"><span data-stu-id="f6ce6-114">Type</span></span>|<span data-ttu-id="f6ce6-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f6ce6-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f6ce6-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f6ce6-116">Affected APIs</span></span>

-<xref:System.Web.HttpRequest.Form?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.Files?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
