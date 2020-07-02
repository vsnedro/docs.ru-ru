---
ms.openlocfilehash: 2aa6603e2ed77ffa94fbc6325cd5db50985bda6a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620679"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="03242-101">PreviewLostKeyboardFocus вызывается повторно, если соответствующий обработчик выводит окно сообщения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03242-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="03242-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="03242-102">Details</span></span>

<span data-ttu-id="03242-103">Начиная с .NET Framework 4.5, вызов <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> из обработчика <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> приведет к повторному запуску обработчика после закрытия окна сообщения. В результате может начаться бесконечный цикл вывода окон сообщений.</span><span class="sxs-lookup"><span data-stu-id="03242-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="03242-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="03242-104">Suggestion</span></span>

<span data-ttu-id="03242-105">Существует два способа решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="03242-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="03242-106">Ее можно избежать, вызвав <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> вместо <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="03242-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="03242-107">Ее можно избежать, открыв окно сообщения из обработчика событий <xref:System.Windows.UIElement.LostKeyboardFocus> (в отличие от обработчика событий <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="03242-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="03242-108">name</span><span class="sxs-lookup"><span data-stu-id="03242-108">Name</span></span>    | <span data-ttu-id="03242-109">Значение</span><span class="sxs-lookup"><span data-stu-id="03242-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="03242-110">Область</span><span class="sxs-lookup"><span data-stu-id="03242-110">Scope</span></span>   |<span data-ttu-id="03242-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="03242-111">Edge</span></span>|
|<span data-ttu-id="03242-112">Version</span><span class="sxs-lookup"><span data-stu-id="03242-112">Version</span></span>|<span data-ttu-id="03242-113">4.5</span><span class="sxs-lookup"><span data-stu-id="03242-113">4.5</span></span>|
|<span data-ttu-id="03242-114">Type</span><span class="sxs-lookup"><span data-stu-id="03242-114">Type</span></span>|<span data-ttu-id="03242-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="03242-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="03242-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="03242-116">Affected APIs</span></span>

-<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
