---
ms.openlocfilehash: 77e9d28d79a92cf1523e4ef5779d78394b00ae80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622085"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="f5afe-101">.NET COM успешно маршалирует параметры ByRef SafeArray в события</span><span class="sxs-lookup"><span data-stu-id="f5afe-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="f5afe-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f5afe-102">Details</span></span>

<span data-ttu-id="f5afe-103">В .NET Framework 4.7.2 и более ранних версиях параметр ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) события COM не позволял выполнить маршалинг обратно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="f5afe-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="f5afe-104">Благодаря этому изменению [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) теперь успешно маршалируется.</span><span class="sxs-lookup"><span data-stu-id="f5afe-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="f5afe-105">[x] Режим совместимости</span><span class="sxs-lookup"><span data-stu-id="f5afe-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="f5afe-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="f5afe-106">Suggestion</span></span>

<span data-ttu-id="f5afe-107">Если правильный маршалинг параметров ByRef SafeArray в событиях COM нарушает выполнение, этот код можно отключить, добавив следующий параметр конфигурации в файл конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="f5afe-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f5afe-108">name</span><span class="sxs-lookup"><span data-stu-id="f5afe-108">Name</span></span>    | <span data-ttu-id="f5afe-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f5afe-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f5afe-110">Область</span><span class="sxs-lookup"><span data-stu-id="f5afe-110">Scope</span></span>   |<span data-ttu-id="f5afe-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f5afe-111">Minor</span></span>|
|<span data-ttu-id="f5afe-112">Version</span><span class="sxs-lookup"><span data-stu-id="f5afe-112">Version</span></span>|<span data-ttu-id="f5afe-113">4.8</span><span class="sxs-lookup"><span data-stu-id="f5afe-113">4.8</span></span>|
|<span data-ttu-id="f5afe-114">Type</span><span class="sxs-lookup"><span data-stu-id="f5afe-114">Type</span></span>|<span data-ttu-id="f5afe-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f5afe-115">Runtime</span></span>|
