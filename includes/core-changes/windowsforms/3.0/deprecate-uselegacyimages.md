---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556225"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="97f16-101">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="97f16-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="97f16-102">Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.8, не поддерживается в Windows Forms в .NET Core и .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="97f16-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="97f16-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="97f16-103">Change description</span></span>

<span data-ttu-id="97f16-104">Начиная с .NET Framework 4.8 параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages` устраняет возможные проблемы с масштабированием изображений в сценариях ClickOnce в средах с высоким DPI.</span><span class="sxs-lookup"><span data-stu-id="97f16-104">Starting with .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="97f16-105">Если задано значение `true`, параметр позволяет пользователю восстановить прежний способ масштабирования изображений при высоком уровне DPI, когда масштаб составляет более 100 %.</span><span class="sxs-lookup"><span data-stu-id="97f16-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="97f16-106">Дополнительные сведения см. в [заметках о выпуске .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="97f16-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="97f16-107">В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.UseLegacyImages` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="97f16-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="97f16-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="97f16-108">Version introduced</span></span>

<span data-ttu-id="97f16-109">3.0</span><span class="sxs-lookup"><span data-stu-id="97f16-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="97f16-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="97f16-110">Recommended action</span></span>

<span data-ttu-id="97f16-111">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="97f16-111">Remove the switch.</span></span> <span data-ttu-id="97f16-112">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="97f16-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="97f16-113">Категория</span><span class="sxs-lookup"><span data-stu-id="97f16-113">Category</span></span>

<span data-ttu-id="97f16-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97f16-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="97f16-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="97f16-115">Affected APIs</span></span>

- <span data-ttu-id="97f16-116">None</span><span class="sxs-lookup"><span data-stu-id="97f16-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
