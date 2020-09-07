---
ms.openlocfilehash: 6a6c0af9cc0f3e5d1bbc3a4462a9ff7eaa748a5f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496500"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="487c3-101">Изменение режима высокой контрастности ComboBox svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="487c3-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="487c3-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="487c3-102">Details</span></span>

<span data-ttu-id="487c3-103">В [программе Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) элементы управления ComboBox не отображались в правильном цвете в некоторых темах высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="487c3-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="487c3-104">Проблема устранена в .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="487c3-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="487c3-105">Но из-за требований обратной совместимости пакета SDK для .NET Framework исправление не видно клиентам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="487c3-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="487c3-106">.NET 4.8 предоставляет это изменение, добавив следующие [параметры конфигурации AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в файл конфигурации svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="487c3-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a><span data-ttu-id="487c3-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="487c3-107">Suggestion</span></span>

<ul><li><span data-ttu-id="487c3-108">Как отказаться от изменения. Если вы не хотите менять поведение тем с высокой контрастностью, отключите его, удалив из файла svcTraceViewer.exe.config следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="487c3-108">How to opt out of the change If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span></li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="487c3-109">name</span><span class="sxs-lookup"><span data-stu-id="487c3-109">Name</span></span>    | <span data-ttu-id="487c3-110">Значение</span><span class="sxs-lookup"><span data-stu-id="487c3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="487c3-111">Область</span><span class="sxs-lookup"><span data-stu-id="487c3-111">Scope</span></span>   |<span data-ttu-id="487c3-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="487c3-112">Edge</span></span>|
|<span data-ttu-id="487c3-113">Version</span><span class="sxs-lookup"><span data-stu-id="487c3-113">Version</span></span>|<span data-ttu-id="487c3-114">4.8</span><span class="sxs-lookup"><span data-stu-id="487c3-114">4.8</span></span>|
|<span data-ttu-id="487c3-115">Type</span><span class="sxs-lookup"><span data-stu-id="487c3-115">Type</span></span>|<span data-ttu-id="487c3-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="487c3-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="487c3-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="487c3-117">Affected APIs</span></span>

<span data-ttu-id="487c3-118">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="487c3-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
