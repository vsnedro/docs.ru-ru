---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606205"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="9b112-101">Метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда</span><span class="sxs-lookup"><span data-stu-id="9b112-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="9b112-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="9b112-102">Details</span></span>

<span data-ttu-id="9b112-103">Начиная с версии .NET Framework 4.5, метод <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> экранирует символ амперсанда (&amp;).</span><span class="sxs-lookup"><span data-stu-id="9b112-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b112-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="9b112-104">Suggestion</span></span>

<span data-ttu-id="9b112-105">Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](/previous-versions/aspnet/hh975440(v=vs.120)) в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9b112-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="9b112-106">name</span><span class="sxs-lookup"><span data-stu-id="9b112-106">Name</span></span>    | <span data-ttu-id="9b112-107">Значение</span><span class="sxs-lookup"><span data-stu-id="9b112-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b112-108">Область</span><span class="sxs-lookup"><span data-stu-id="9b112-108">Scope</span></span>   |<span data-ttu-id="9b112-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="9b112-109">Minor</span></span>|
|<span data-ttu-id="9b112-110">Version</span><span class="sxs-lookup"><span data-stu-id="9b112-110">Version</span></span>|<span data-ttu-id="9b112-111">4.5</span><span class="sxs-lookup"><span data-stu-id="9b112-111">4.5</span></span>|
|<span data-ttu-id="9b112-112">Type</span><span class="sxs-lookup"><span data-stu-id="9b112-112">Type</span></span>|<span data-ttu-id="9b112-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="9b112-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9b112-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9b112-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
