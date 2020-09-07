---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497946"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="1da78-101">PreviewLostKeyboardFocus вызывается повторно, если соответствующий обработчик выводит окно сообщения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1da78-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="1da78-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="1da78-102">Details</span></span>

<span data-ttu-id="1da78-103">Начиная с .NET Framework 4.5, вызов <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> из обработчика <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> приведет к повторному запуску обработчика после закрытия окна сообщения. В результате может начаться бесконечный цикл вывода окон сообщений.</span><span class="sxs-lookup"><span data-stu-id="1da78-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1da78-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="1da78-104">Suggestion</span></span>

<span data-ttu-id="1da78-105">Существует два способа решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="1da78-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="1da78-106">Ее можно избежать, вызвав <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> вместо <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1da78-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="1da78-107">Ее можно избежать, открыв окно сообщения из обработчика событий <xref:System.Windows.UIElement.LostKeyboardFocus> (в отличие от обработчика событий <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="1da78-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="1da78-108">name</span><span class="sxs-lookup"><span data-stu-id="1da78-108">Name</span></span>    | <span data-ttu-id="1da78-109">Значение</span><span class="sxs-lookup"><span data-stu-id="1da78-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1da78-110">Область</span><span class="sxs-lookup"><span data-stu-id="1da78-110">Scope</span></span>   |<span data-ttu-id="1da78-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="1da78-111">Edge</span></span>|
|<span data-ttu-id="1da78-112">Version</span><span class="sxs-lookup"><span data-stu-id="1da78-112">Version</span></span>|<span data-ttu-id="1da78-113">4.5</span><span class="sxs-lookup"><span data-stu-id="1da78-113">4.5</span></span>|
|<span data-ttu-id="1da78-114">Type</span><span class="sxs-lookup"><span data-stu-id="1da78-114">Type</span></span>|<span data-ttu-id="1da78-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="1da78-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1da78-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1da78-116">Affected APIs</span></span>

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
