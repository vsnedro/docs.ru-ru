---
ms.openlocfilehash: c980b0c0be9f4d6a529baa0743dec9ac16ca0d7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720957"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="f0b5a-101">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="f0b5a-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="f0b5a-102">Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.8, не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f0b5a-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f0b5a-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="f0b5a-103">Change description</span></span>

<span data-ttu-id="f0b5a-104">Начиная с .NET Framework 4.8, параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages` устраняет возможные проблемы с масштабированием изображений в сценариях ClickOnce в средах с высоким DPI.</span><span class="sxs-lookup"><span data-stu-id="f0b5a-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="f0b5a-105">Если задано значение `true`, параметр позволяет пользователю восстановить прежний способ масштабирования изображений при высоком уровне DPI, когда масштаб составляет более 100 %.</span><span class="sxs-lookup"><span data-stu-id="f0b5a-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="f0b5a-106">Дополнительные сведения см. в [заметках о выпуске .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="f0b5a-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="f0b5a-107">В .NET Core параметр `Switch.System.Windows.Forms.UseLegacyImages` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f0b5a-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f0b5a-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="f0b5a-108">Version introduced</span></span>

<span data-ttu-id="f0b5a-109">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="f0b5a-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f0b5a-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="f0b5a-110">Recommended action</span></span>

<span data-ttu-id="f0b5a-111">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="f0b5a-111">Remove the switch.</span></span> <span data-ttu-id="f0b5a-112">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="f0b5a-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="f0b5a-113">Категория</span><span class="sxs-lookup"><span data-stu-id="f0b5a-113">Category</span></span>

<span data-ttu-id="f0b5a-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0b5a-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f0b5a-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f0b5a-115">Affected APIs</span></span>

- <span data-ttu-id="f0b5a-116">None</span><span class="sxs-lookup"><span data-stu-id="f0b5a-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
