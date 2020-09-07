---
ms.openlocfilehash: 1907c9b82c9685899d328f67da8001c0fa4fb697
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497242"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="8b910-101">.NET COM успешно маршалирует параметры ByRef SafeArray в события</span><span class="sxs-lookup"><span data-stu-id="8b910-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="8b910-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="8b910-102">Details</span></span>

<span data-ttu-id="8b910-103">В .NET Framework 4.7.2 и более ранних версиях параметр ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) события COM не позволял выполнить маршалинг обратно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="8b910-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="8b910-104">Благодаря этому изменению [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) теперь успешно маршалируется.</span><span class="sxs-lookup"><span data-stu-id="8b910-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="8b910-105">[x] Режим совместимости</span><span class="sxs-lookup"><span data-stu-id="8b910-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="8b910-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="8b910-106">Suggestion</span></span>

<span data-ttu-id="8b910-107">Если правильный маршалинг параметров ByRef SafeArray в событиях COM нарушает выполнение, этот код можно отключить, добавив следующий параметр конфигурации в файл конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="8b910-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8b910-108">name</span><span class="sxs-lookup"><span data-stu-id="8b910-108">Name</span></span>    | <span data-ttu-id="8b910-109">Значение</span><span class="sxs-lookup"><span data-stu-id="8b910-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8b910-110">Область</span><span class="sxs-lookup"><span data-stu-id="8b910-110">Scope</span></span>   |<span data-ttu-id="8b910-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="8b910-111">Minor</span></span>|
|<span data-ttu-id="8b910-112">Version</span><span class="sxs-lookup"><span data-stu-id="8b910-112">Version</span></span>|<span data-ttu-id="8b910-113">4.8</span><span class="sxs-lookup"><span data-stu-id="8b910-113">4.8</span></span>|
|<span data-ttu-id="8b910-114">Type</span><span class="sxs-lookup"><span data-stu-id="8b910-114">Type</span></span>|<span data-ttu-id="8b910-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="8b910-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8b910-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8b910-116">Affected APIs</span></span>

<span data-ttu-id="8b910-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="8b910-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
