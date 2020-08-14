---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556233"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="16449-101">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="16449-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="16449-102">Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` поддерживается в Windows Forms в .NET Framework 4.6 и более поздних версиях, но не поддерживается в .NET Core,а также в .NET Core 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="16449-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="16449-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="16449-103">Change description</span></span>

<span data-ttu-id="16449-104">В .NET Framework 4.6 и более поздних версиях при выборе вкладки ее коллекция элементов управления переупорядочивается.</span><span class="sxs-lookup"><span data-stu-id="16449-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="16449-105">Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` позволяет приложению отменить переупорядочивание, если оно не требуется.</span><span class="sxs-lookup"><span data-stu-id="16449-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="16449-106">В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="16449-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="16449-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="16449-107">Version introduced</span></span>

<span data-ttu-id="16449-108">3.0</span><span class="sxs-lookup"><span data-stu-id="16449-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="16449-109">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="16449-109">Recommended action</span></span>

<span data-ttu-id="16449-110">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="16449-110">Remove the switch.</span></span> <span data-ttu-id="16449-111">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="16449-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="16449-112">Категория</span><span class="sxs-lookup"><span data-stu-id="16449-112">Category</span></span>

<span data-ttu-id="16449-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16449-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="16449-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="16449-114">Affected APIs</span></span>

- <span data-ttu-id="16449-115">None</span><span class="sxs-lookup"><span data-stu-id="16449-115">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
