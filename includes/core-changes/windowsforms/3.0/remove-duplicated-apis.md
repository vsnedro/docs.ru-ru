---
ms.openlocfilehash: 3dfacadb5127319d4ce27f367803637cfb1ed00f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720971"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="35775-101">Дублированные API удалены из Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35775-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="35775-102">В .NET Core 3.0 RC1 были удалены некоторые API, которые случайно дублируются в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName> начиная с версии .NET Core 3.0, предварительная версия 4.</span><span class="sxs-lookup"><span data-stu-id="35775-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="35775-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="35775-103">Change description</span></span>

<span data-ttu-id="35775-104">В .NET Core 3.0, предварительная версия 4, случайно дублировались несколько типов в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName>, которые уже существовали в пространстве имен <xref:System.ComponentModel.Design?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="35775-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="35775-105">Начиная с .NET Core 3.0 RC1 эти дублирующиеся типы больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="35775-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="35775-106">В следующей таблице приводится список исходного типа и его повторяющегося типа:</span><span class="sxs-lookup"><span data-stu-id="35775-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="35775-107">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="35775-107">Original type</span></span>|<span data-ttu-id="35775-108">Повторяющийся тип</span><span class="sxs-lookup"><span data-stu-id="35775-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="35775-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="35775-109">Version introduced</span></span>

<span data-ttu-id="35775-110">3.0 RC1 (релиз-кандидат 1)</span><span class="sxs-lookup"><span data-stu-id="35775-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="35775-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="35775-111">Recommended action</span></span>

<span data-ttu-id="35775-112">Обновите код, чтобы он ссылался на исходный тип, как показано в столбце **Исходный тип**.</span><span class="sxs-lookup"><span data-stu-id="35775-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="35775-113">Категория</span><span class="sxs-lookup"><span data-stu-id="35775-113">Category</span></span>

<span data-ttu-id="35775-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35775-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="35775-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="35775-115">Affected APIs</span></span>

- <span data-ttu-id="35775-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="35775-116">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis.

-->
