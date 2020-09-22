---
ms.openlocfilehash: aadf5eb85c8736c29639d49bc8baf21545d2467c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606909"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="f333b-101">.NET COM успешно маршалирует параметры ByRef SafeArray в события</span><span class="sxs-lookup"><span data-stu-id="f333b-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="f333b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f333b-102">Details</span></span>

<span data-ttu-id="f333b-103">В .NET Framework 4.7.2 и более ранних версиях параметр ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) события COM не позволял выполнить маршалинг обратно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="f333b-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="f333b-104">Благодаря этому изменению [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) теперь успешно маршалируется.</span><span class="sxs-lookup"><span data-stu-id="f333b-104">With this change the [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="f333b-105">[x] Режим совместимости</span><span class="sxs-lookup"><span data-stu-id="f333b-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="f333b-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="f333b-106">Suggestion</span></span>

<span data-ttu-id="f333b-107">Если правильный маршалинг параметров ByRef SafeArray в событиях COM нарушает выполнение, этот код можно отключить, добавив следующий параметр конфигурации в файл конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="f333b-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f333b-108">name</span><span class="sxs-lookup"><span data-stu-id="f333b-108">Name</span></span>    | <span data-ttu-id="f333b-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f333b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f333b-110">Область</span><span class="sxs-lookup"><span data-stu-id="f333b-110">Scope</span></span>   |<span data-ttu-id="f333b-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f333b-111">Minor</span></span>|
|<span data-ttu-id="f333b-112">Version</span><span class="sxs-lookup"><span data-stu-id="f333b-112">Version</span></span>|<span data-ttu-id="f333b-113">4.8</span><span class="sxs-lookup"><span data-stu-id="f333b-113">4.8</span></span>|
|<span data-ttu-id="f333b-114">Type</span><span class="sxs-lookup"><span data-stu-id="f333b-114">Type</span></span>|<span data-ttu-id="f333b-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f333b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f333b-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f333b-116">Affected APIs</span></span>

<span data-ttu-id="f333b-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="f333b-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
