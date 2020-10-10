---
title: Метод Препарехеадердраг (System. Windows. Controls. Гридвиевхеадерровпресентер)
description: Сведения о закрытом методе WPF с именем Препарехеадердраг.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877792"
---
# <a name="prepareheaderdrag-method"></a><span data-ttu-id="e3529-103">Метод Препарехеадердраг</span><span class="sxs-lookup"><span data-stu-id="e3529-103">PrepareHeaderDrag method</span></span>

<span data-ttu-id="e3529-104">Подготавливает указанный заголовок столбца для изменения порядка.</span><span class="sxs-lookup"><span data-stu-id="e3529-104">Prepares the specified column header for reordering.</span></span>

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> <span data-ttu-id="e3529-105">Этот метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="e3529-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e3529-106">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="e3529-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="e3529-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3529-107">Parameters</span></span>

<span data-ttu-id="e3529-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span><span class="sxs-lookup"><span data-stu-id="e3529-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span></span>\
<span data-ttu-id="e3529-109">Заголовок столбца для подготовки к переупорядочению.</span><span class="sxs-lookup"><span data-stu-id="e3529-109">The column header to prepare for reordering.</span></span>

<span data-ttu-id="e3529-110">`pos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="e3529-110">`pos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="e3529-111">Позицию относительно <xref:System.Windows.Controls.GridViewHeaderRowPresenter> , где начинается перетаскивание.</span><span class="sxs-lookup"><span data-stu-id="e3529-111">The position, relative to <xref:System.Windows.Controls.GridViewHeaderRowPresenter>, where the dragging starts.</span></span>

<span data-ttu-id="e3529-112">`relativePos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="e3529-112">`relativePos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="e3529-113">Позицию относительно `header` , где начинается перетаскивание.</span><span class="sxs-lookup"><span data-stu-id="e3529-113">The position, relative to `header`, where the dragging starts.</span></span>

<span data-ttu-id="e3529-114">`cancelInvoke` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="e3529-114">`cancelInvoke` <xref:System.Boolean></span></span>\
<span data-ttu-id="e3529-115">`true` значение для отмены изменения порядка; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="e3529-115">`true` to cancel the reordering; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3529-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e3529-116">Requirements</span></span>

<span data-ttu-id="e3529-117">**Пространство имен:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="e3529-117">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="e3529-118">**Сборка:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="e3529-118">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="e3529-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e3529-119">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
