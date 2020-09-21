---
ms.openlocfilehash: 77e231f8ef1dde8a263b8622311099a4a404062d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606602"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a><span data-ttu-id="0d430-101">HwndHost теперь правильно изменяет размеры дочерних HWND во время изменений DPI</span><span class="sxs-lookup"><span data-stu-id="0d430-101">HwndHost now correctly resizes child-HWND during DPI changes</span></span>

#### <a name="details"></a><span data-ttu-id="0d430-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0d430-102">Details</span></span>

<span data-ttu-id="0d430-103">В .NET Framework 4.7.2 и более ранних версий при запуске WPF в режиме поддержки на уровне монитора элементы управления, размещенные в <xref:System.Windows.Interop.HwndHost>, имели неправильный размер после изменения DPI, например при перемещении приложений с одного монитора на другой.</span><span class="sxs-lookup"><span data-stu-id="0d430-103">In .NET Framework 4.7.2 and earlier versions, when WPF was run in Per-Monitor Aware mode, controls hosted within <xref:System.Windows.Interop.HwndHost> were not sized correctly after DPI changes, such as when moving applications from one monitor to another.</span></span> <span data-ttu-id="0d430-104">Это исправление гарантирует, что размещенные элементы управления правильно изменяют размер.</span><span class="sxs-lookup"><span data-stu-id="0d430-104">This fix ensures that hosted controls are sized appropriately.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0d430-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0d430-105">Suggestion</span></span>

<span data-ttu-id="0d430-106">Чтобы приложение могло использовать эти изменения, необходимо запустить его на платформе .NET Framework 4.7.2 или более поздней версии и включить это поведение, установив следующий [параметр AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе `<runtime>` файла конфигурации приложения в значение `false`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0d430-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later, and it must opt-in to this behavior by setting the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the `<runtime>` section of the app config file to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="0d430-107">name</span><span class="sxs-lookup"><span data-stu-id="0d430-107">Name</span></span>    | <span data-ttu-id="0d430-108">Значение</span><span class="sxs-lookup"><span data-stu-id="0d430-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0d430-109">Область</span><span class="sxs-lookup"><span data-stu-id="0d430-109">Scope</span></span>   | <span data-ttu-id="0d430-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="0d430-110">Major</span></span>       |
| <span data-ttu-id="0d430-111">Version</span><span class="sxs-lookup"><span data-stu-id="0d430-111">Version</span></span> | <span data-ttu-id="0d430-112">4.8</span><span class="sxs-lookup"><span data-stu-id="0d430-112">4.8</span></span>         |
| <span data-ttu-id="0d430-113">Type</span><span class="sxs-lookup"><span data-stu-id="0d430-113">Type</span></span>    | <span data-ttu-id="0d430-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="0d430-114">Retargeting</span></span> |
