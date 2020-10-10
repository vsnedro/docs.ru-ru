---
title: Метод Финдхеадербиколумн (System. Windows. Controls. Гридвиевхеадерровпресентер)
description: Сведения о закрытом методе WPF с именем Финдхеадербиколумн.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877801"
---
# <a name="findheaderbycolumn-method"></a><span data-ttu-id="e401f-103">Метод Финдхеадербиколумн</span><span class="sxs-lookup"><span data-stu-id="e401f-103">FindHeaderByColumn method</span></span>

<span data-ttu-id="e401f-104">Находит заголовок столбца для указанного столбца в визуальном дереве.</span><span class="sxs-lookup"><span data-stu-id="e401f-104">Finds the column header for the specified column in the visual tree.</span></span>

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> <span data-ttu-id="e401f-105">Этот метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="e401f-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e401f-106">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="e401f-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="e401f-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e401f-107">Parameters</span></span>

<span data-ttu-id="e401f-108">`column` <xref:System.Windows.Controls.GridViewColumn></span><span class="sxs-lookup"><span data-stu-id="e401f-108">`column` <xref:System.Windows.Controls.GridViewColumn></span></span>\
<span data-ttu-id="e401f-109">Столбец, заголовок которого должен быть найден и возвращен.</span><span class="sxs-lookup"><span data-stu-id="e401f-109">The column whose header should be found and returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="e401f-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e401f-110">Return value</span></span>

<xref:System.Windows.Controls.GridViewColumnHeader>\
<span data-ttu-id="e401f-111">Заголовок указанного столбца или `null` значение, если указанный столбец не существует.</span><span class="sxs-lookup"><span data-stu-id="e401f-111">The header of the specified column, or `null` if the specified column doesn't exist.</span></span>

## <a name="requirements"></a><span data-ttu-id="e401f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e401f-112">Requirements</span></span>

<span data-ttu-id="e401f-113">**Пространство имен:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="e401f-113">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="e401f-114">**Сборка:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="e401f-114">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="e401f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e401f-115">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
