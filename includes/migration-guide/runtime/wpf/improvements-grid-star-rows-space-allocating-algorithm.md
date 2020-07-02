---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622095"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="2f162-101">Усовершенствования алгоритма выделения пространства для строк со звездами в сетке</span><span class="sxs-lookup"><span data-stu-id="2f162-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="2f162-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2f162-102">Details</span></span>

<span data-ttu-id="2f162-103">Исправлена ошибка в [алгоритме выделения размеров для ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) в <xref:System.Windows.Controls.Grid>, представленном в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="2f162-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="2f162-104">В некоторых случаях, например в сетке с <code>Height=&quot;Auto&quot;</code>, которая содержит пустые строки, строки были расположены в неправильном положении, возможно, даже за пределами сетки.</span><span class="sxs-lookup"><span data-stu-id="2f162-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2f162-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="2f162-105">Suggestion</span></span>

<span data-ttu-id="2f162-106">Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.8 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2f162-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="2f162-107">name</span><span class="sxs-lookup"><span data-stu-id="2f162-107">Name</span></span>    | <span data-ttu-id="2f162-108">Значение</span><span class="sxs-lookup"><span data-stu-id="2f162-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2f162-109">Область</span><span class="sxs-lookup"><span data-stu-id="2f162-109">Scope</span></span>   |<span data-ttu-id="2f162-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="2f162-110">Major</span></span>|
|<span data-ttu-id="2f162-111">Version</span><span class="sxs-lookup"><span data-stu-id="2f162-111">Version</span></span>|<span data-ttu-id="2f162-112">4.8</span><span class="sxs-lookup"><span data-stu-id="2f162-112">4.8</span></span>|
|<span data-ttu-id="2f162-113">Type</span><span class="sxs-lookup"><span data-stu-id="2f162-113">Type</span></span>|<span data-ttu-id="2f162-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2f162-114">Runtime</span></span>|
