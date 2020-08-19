---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062433"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="79ee4-101">Отсутствует проверка суффикса A/W на платформах, отличных от Windows</span><span class="sxs-lookup"><span data-stu-id="79ee4-101">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="79ee4-102">Среды выполнения .NET больше не добавляют суффиксы `A` или `W` к именам экспортируемых функций во время проверки для P/Invokes на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="79ee4-102">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="79ee4-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="79ee4-103">Version introduced</span></span>

<span data-ttu-id="79ee4-104">5.0, предварительная версия 4</span><span class="sxs-lookup"><span data-stu-id="79ee4-104">5.0 Preview 4</span></span>

#### <a name="change-description"></a><span data-ttu-id="79ee4-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="79ee4-105">Change description</span></span>

<span data-ttu-id="79ee4-106">[По соглашению Windows](/windows/win32/intl/conventions-for-function-prototypes), к именам функций Windows SDK, которые соответствуют кодовой странице Windows и версиям Юникода, добавляются суффиксы `A` и `W` соответственно.</span><span class="sxs-lookup"><span data-stu-id="79ee4-106">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="79ee4-107">В предыдущих версиях .NET в средах выполнения CoreCLR и Mono к именам экспорта добавлялись суффиксы `A` или `W` во время обнаружения экспорта для P/Invokes *на всех платформах*.</span><span class="sxs-lookup"><span data-stu-id="79ee4-107">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="79ee4-108">В .NET 5.0 и более поздней версии суффиксы `A` или `W` добавляется к именам экспорта во время обнаружения экспорта *только в Windows*.</span><span class="sxs-lookup"><span data-stu-id="79ee4-108">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="79ee4-109">На платформах UNIX суффикс не добавляется.</span><span class="sxs-lookup"><span data-stu-id="79ee4-109">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="79ee4-110">Семантика обеих сред выполнения на платформе Windows остается неизменной.</span><span class="sxs-lookup"><span data-stu-id="79ee4-110">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="79ee4-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="79ee4-111">Reason for change</span></span>

<span data-ttu-id="79ee4-112">Это изменение было внесено с целью упрощения проверки на нескольких платформах.</span><span class="sxs-lookup"><span data-stu-id="79ee4-112">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="79ee4-113">Это изменение не должно привести к дополнительным издержкам, так как платформы, отличные от Windows, не содержат такой семантики.</span><span class="sxs-lookup"><span data-stu-id="79ee4-113">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="79ee4-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="79ee4-114">Recommended action</span></span>

<span data-ttu-id="79ee4-115">Чтобы ослабить эффект этого изменения, можно вручную добавить требуемый суффикс на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="79ee4-115">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="79ee4-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="79ee4-116">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a><span data-ttu-id="79ee4-117">Категория</span><span class="sxs-lookup"><span data-stu-id="79ee4-117">Category</span></span>

<span data-ttu-id="79ee4-118">Interop</span><span class="sxs-lookup"><span data-stu-id="79ee4-118">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="79ee4-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="79ee4-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
