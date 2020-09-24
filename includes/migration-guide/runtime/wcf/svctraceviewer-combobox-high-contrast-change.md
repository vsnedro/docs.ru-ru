---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770814"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="0c784-101">Изменение режима высокой контрастности ComboBox svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="0c784-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="0c784-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0c784-102">Details</span></span>

<span data-ttu-id="0c784-103">В [программе Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) элементы управления ComboBox не отображались в правильном цвете в некоторых темах высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="0c784-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="0c784-104">Проблема устранена в .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="0c784-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="0c784-105">Но из-за требований обратной совместимости пакета SDK для .NET Framework исправление не видно клиентам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0c784-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="0c784-106">.NET 4.8 предоставляет это изменение, добавив следующие [параметры конфигурации AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в файл конфигурации svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="0c784-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a><span data-ttu-id="0c784-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="0c784-107">Suggestion</span></span>

<span data-ttu-id="0c784-108">Если вы не хотите менять поведение тем с высокой контрастностью, отключите его, удалив из файла svcTraceViewer.exe.config следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="0c784-108">If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| <span data-ttu-id="0c784-109">name</span><span class="sxs-lookup"><span data-stu-id="0c784-109">Name</span></span>    | <span data-ttu-id="0c784-110">Значение</span><span class="sxs-lookup"><span data-stu-id="0c784-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="0c784-111">Область</span><span class="sxs-lookup"><span data-stu-id="0c784-111">Scope</span></span>   | <span data-ttu-id="0c784-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="0c784-112">Edge</span></span>    |
| <span data-ttu-id="0c784-113">Version</span><span class="sxs-lookup"><span data-stu-id="0c784-113">Version</span></span> | <span data-ttu-id="0c784-114">4.8</span><span class="sxs-lookup"><span data-stu-id="0c784-114">4.8</span></span>     |
| <span data-ttu-id="0c784-115">Type</span><span class="sxs-lookup"><span data-stu-id="0c784-115">Type</span></span>    | <span data-ttu-id="0c784-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0c784-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="0c784-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0c784-117">Affected APIs</span></span>

<span data-ttu-id="0c784-118">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="0c784-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
