---
ms.openlocfilehash: df6169289fb96df5f7daf8bd58ccaeebc33ad87c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556238"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="d1642-101">Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается</span><span class="sxs-lookup"><span data-stu-id="d1642-101">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="d1642-102">Параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, появившийся в .NET Framework 4.7.2, не поддерживается в Windows Forms в .NET Core и .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d1642-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d1642-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="d1642-103">Change description</span></span>

<span data-ttu-id="d1642-104">Начиная с версии .NET Framework 4.7.2 параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` позволяет разработчикам отказаться от нового поведения свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, которое теперь возвращает ссылку на систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="d1642-104">Starting with .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="d1642-105">Ранее это свойство возвращало `null`.</span><span class="sxs-lookup"><span data-stu-id="d1642-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="d1642-106">Дополнительные сведения см. в разделе [Элемент \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="d1642-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="d1642-107">В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d1642-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d1642-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="d1642-108">Version introduced</span></span>

<span data-ttu-id="d1642-109">3.0</span><span class="sxs-lookup"><span data-stu-id="d1642-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d1642-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="d1642-110">Recommended action</span></span>

<span data-ttu-id="d1642-111">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="d1642-111">Remove the switch.</span></span> <span data-ttu-id="d1642-112">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="d1642-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d1642-113">Категория</span><span class="sxs-lookup"><span data-stu-id="d1642-113">Category</span></span>

<span data-ttu-id="d1642-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1642-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d1642-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d1642-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
