---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556222"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="e36c1-101">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="e36c1-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="e36c1-102">Параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается в Windows Forms в .NET Core или .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e36c1-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e36c1-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="e36c1-103">Change description</span></span>

<span data-ttu-id="e36c1-104">В .NET Framework параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` позволял приложению отказаться от проверки визуальных стилей, предоставленных в числовой форме.</span><span class="sxs-lookup"><span data-stu-id="e36c1-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="e36c1-105">В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e36c1-105">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e36c1-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e36c1-106">Version introduced</span></span>

<span data-ttu-id="e36c1-107">3.0</span><span class="sxs-lookup"><span data-stu-id="e36c1-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e36c1-108">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="e36c1-108">Recommended action</span></span>

<span data-ttu-id="e36c1-109">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="e36c1-109">Remove the switch.</span></span> <span data-ttu-id="e36c1-110">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="e36c1-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e36c1-111">Категория</span><span class="sxs-lookup"><span data-stu-id="e36c1-111">Category</span></span>

<span data-ttu-id="e36c1-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e36c1-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e36c1-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e36c1-113">Affected APIs</span></span>

- <span data-ttu-id="e36c1-114">None</span><span class="sxs-lookup"><span data-stu-id="e36c1-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
