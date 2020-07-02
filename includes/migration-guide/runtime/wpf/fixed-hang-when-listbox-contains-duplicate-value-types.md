---
ms.openlocfilehash: 5d5423d18091545ad9d50325900f5a9a4fff6dd9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622115"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a><span data-ttu-id="cc504-101">Исправлено зависание, если ListBox содержит повторяющиеся типы значений</span><span class="sxs-lookup"><span data-stu-id="cc504-101">Fixed a hang when ListBox contains duplicate value-types</span></span>

#### <a name="details"></a><span data-ttu-id="cc504-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="cc504-102">Details</span></span>

<span data-ttu-id="cc504-103">Устранена проблема, при которой виртуализация <xref:System.Windows.Controls.ItemsControl> приводила к зависанию при прокрутке, когда коллекция элементов содержит повторяющиеся объекты типов значений.</span><span class="sxs-lookup"><span data-stu-id="cc504-103">Fixed a problem where a virtualizing<xref:System.Windows.Controls.ItemsControl> can hang during scrolling when its Items collection contains duplicate value-typed objects.</span></span>

| <span data-ttu-id="cc504-104">name</span><span class="sxs-lookup"><span data-stu-id="cc504-104">Name</span></span>    | <span data-ttu-id="cc504-105">Значение</span><span class="sxs-lookup"><span data-stu-id="cc504-105">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cc504-106">Область</span><span class="sxs-lookup"><span data-stu-id="cc504-106">Scope</span></span>   |<span data-ttu-id="cc504-107">Значительно</span><span class="sxs-lookup"><span data-stu-id="cc504-107">Major</span></span>|
|<span data-ttu-id="cc504-108">Version</span><span class="sxs-lookup"><span data-stu-id="cc504-108">Version</span></span>|<span data-ttu-id="cc504-109">4.8</span><span class="sxs-lookup"><span data-stu-id="cc504-109">4.8</span></span>|
|<span data-ttu-id="cc504-110">Type</span><span class="sxs-lookup"><span data-stu-id="cc504-110">Type</span></span>|<span data-ttu-id="cc504-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="cc504-111">Runtime</span></span>|
