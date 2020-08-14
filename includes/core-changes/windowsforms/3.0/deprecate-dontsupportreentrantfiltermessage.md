---
ms.openlocfilehash: 95aa243a5790d4201c7871e617dbe4ccafb7c1a1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556246"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="1d432-101">Параметр совместимости DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="1d432-101">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="1d432-102">Параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, появившийся в .NET Framework 4.6.1, не поддерживается в Windows Forms в .NET Core и .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="1d432-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core and .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1d432-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="1d432-103">Change description</span></span>

<span data-ttu-id="1d432-104">Начиная с .NET Framework 4.6.1, параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` устраняет возможные исключения <xref:System.IndexOutOfRangeException> при вызове сообщения <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> с пользовательской реализацией <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d432-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="1d432-105">Дополнительные сведения см. в разделе [Устранение рисков: пользовательские реализации IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span><span class="sxs-lookup"><span data-stu-id="1d432-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="1d432-106">В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1d432-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1d432-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="1d432-107">Version introduced</span></span>

<span data-ttu-id="1d432-108">3.0</span><span class="sxs-lookup"><span data-stu-id="1d432-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1d432-109">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="1d432-109">Recommended action</span></span>

<span data-ttu-id="1d432-110">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="1d432-110">Remove the switch.</span></span> <span data-ttu-id="1d432-111">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="1d432-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="1d432-112">Категория</span><span class="sxs-lookup"><span data-stu-id="1d432-112">Category</span></span>

<span data-ttu-id="1d432-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1d432-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1d432-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1d432-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
