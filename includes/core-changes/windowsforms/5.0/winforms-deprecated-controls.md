---
ms.openlocfilehash: c9720f51e40ada4cd2cf6997ba7006a232893553
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702465"
---
### <a name="removed-status-bar-controls"></a><span data-ttu-id="67cba-101">Удалены элементы управления строкой состояния</span><span class="sxs-lookup"><span data-stu-id="67cba-101">Removed status bar controls</span></span>

<span data-ttu-id="67cba-102">Начиная с предварительной версии 1 .NET 5.0 некоторые элементы управления Windows Forms больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="67cba-102">Starting in .NET 5.0 Preview 1, some Windows Forms controls are no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="67cba-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="67cba-103">Change description</span></span>

<span data-ttu-id="67cba-104">Начиная с предварительной версии 1 .NET 5.0 некоторые элементы управления Windows Forms, связанные со строкой состояния, больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="67cba-104">Starting with .NET 5.0 Preview 1, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="67cba-105">В .NET Framework 2.0 они были заменены элементами управления с улучшенной структурой и поддержкой.</span><span class="sxs-lookup"><span data-stu-id="67cba-105">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="67cba-106">Нерекомендуемые элементы управления были ранее удалены из панелей элементов конструктора, но по-прежнему были доступны для использования.</span><span class="sxs-lookup"><span data-stu-id="67cba-106">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="67cba-107">Теперь они окончательно удалены.</span><span class="sxs-lookup"><span data-stu-id="67cba-107">Now, they have been completely removed.</span></span>

<span data-ttu-id="67cba-108">Следующие типы больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="67cba-108">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

#### <a name="version-introduced"></a><span data-ttu-id="67cba-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="67cba-109">Version introduced</span></span>

<span data-ttu-id="67cba-110">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="67cba-110">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="67cba-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="67cba-111">Recommended action</span></span>

<span data-ttu-id="67cba-112">Перейдите к замещающим API для этих элементов управления и их сценариев:</span><span class="sxs-lookup"><span data-stu-id="67cba-112">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="67cba-113">Старый элемент управления (API)</span><span class="sxs-lookup"><span data-stu-id="67cba-113">Old Control (API)</span></span> | <span data-ttu-id="67cba-114">Рекомендуемая замена</span><span class="sxs-lookup"><span data-stu-id="67cba-114">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="67cba-115">StatusBar</span><span class="sxs-lookup"><span data-stu-id="67cba-115">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="67cba-116">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="67cba-116">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

#### <a name="category"></a><span data-ttu-id="67cba-117">Категория</span><span class="sxs-lookup"><span data-stu-id="67cba-117">Category</span></span>

<span data-ttu-id="67cba-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67cba-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="67cba-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="67cba-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle` 

-->
