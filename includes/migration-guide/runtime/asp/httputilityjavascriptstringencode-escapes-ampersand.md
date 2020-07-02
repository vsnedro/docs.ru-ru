---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620147"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="ffeb6-101">Метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда</span><span class="sxs-lookup"><span data-stu-id="ffeb6-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="ffeb6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ffeb6-102">Details</span></span>

<span data-ttu-id="ffeb6-103">Начиная с версии .NET Framework 4.5, метод <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> экранирует символ амперсанда (&amp;).</span><span class="sxs-lookup"><span data-stu-id="ffeb6-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ffeb6-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="ffeb6-104">Suggestion</span></span>

<span data-ttu-id="ffeb6-105">Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="ffeb6-106">name</span><span class="sxs-lookup"><span data-stu-id="ffeb6-106">Name</span></span>    | <span data-ttu-id="ffeb6-107">Значение</span><span class="sxs-lookup"><span data-stu-id="ffeb6-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ffeb6-108">Область</span><span class="sxs-lookup"><span data-stu-id="ffeb6-108">Scope</span></span>   |<span data-ttu-id="ffeb6-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ffeb6-109">Minor</span></span>|
|<span data-ttu-id="ffeb6-110">Version</span><span class="sxs-lookup"><span data-stu-id="ffeb6-110">Version</span></span>|<span data-ttu-id="ffeb6-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ffeb6-111">4.5</span></span>|
|<span data-ttu-id="ffeb6-112">Type</span><span class="sxs-lookup"><span data-stu-id="ffeb6-112">Type</span></span>|<span data-ttu-id="ffeb6-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ffeb6-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ffeb6-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ffeb6-114">Affected APIs</span></span>

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
