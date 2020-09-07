---
ms.openlocfilehash: 12fb72d5ee9fc0d6c57899589cb2b0da7db41f4a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496584"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="d1245-101">Метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда</span><span class="sxs-lookup"><span data-stu-id="d1245-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="d1245-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d1245-102">Details</span></span>

<span data-ttu-id="d1245-103">Начиная с версии .NET Framework 4.5, метод <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> экранирует символ амперсанда (&amp;).</span><span class="sxs-lookup"><span data-stu-id="d1245-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d1245-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="d1245-104">Suggestion</span></span>

<span data-ttu-id="d1245-105">Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d1245-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="d1245-106">name</span><span class="sxs-lookup"><span data-stu-id="d1245-106">Name</span></span>    | <span data-ttu-id="d1245-107">Значение</span><span class="sxs-lookup"><span data-stu-id="d1245-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d1245-108">Область</span><span class="sxs-lookup"><span data-stu-id="d1245-108">Scope</span></span>   |<span data-ttu-id="d1245-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="d1245-109">Minor</span></span>|
|<span data-ttu-id="d1245-110">Version</span><span class="sxs-lookup"><span data-stu-id="d1245-110">Version</span></span>|<span data-ttu-id="d1245-111">4.5</span><span class="sxs-lookup"><span data-stu-id="d1245-111">4.5</span></span>|
|<span data-ttu-id="d1245-112">Type</span><span class="sxs-lookup"><span data-stu-id="d1245-112">Type</span></span>|<span data-ttu-id="d1245-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d1245-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d1245-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d1245-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
