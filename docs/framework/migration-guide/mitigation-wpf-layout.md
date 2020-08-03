---
title: Устранение рисков. Макет WPF
description: Узнайте, как устранить проблемы, возникающие в результате изменений в макете элементов управления WPF, таких как размещение объекта, перемещаемого на один пиксель.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: e4e4612f7b39eefbf0e76ac86c8eb644c257ba75
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475350"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="02ff7-103">Устранение рисков. Макет WPF</span><span class="sxs-lookup"><span data-stu-id="02ff7-103">Mitigation: WPF Layout</span></span>
<span data-ttu-id="02ff7-104">Макет элементов управления WPF может немного изменяться.</span><span class="sxs-lookup"><span data-stu-id="02ff7-104">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="02ff7-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="02ff7-105">Impact</span></span>  
 <span data-ttu-id="02ff7-106">В результате этого изменения:</span><span class="sxs-lookup"><span data-stu-id="02ff7-106">As a result of this change:</span></span>  
  
- <span data-ttu-id="02ff7-107">ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;</span><span class="sxs-lookup"><span data-stu-id="02ff7-107">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="02ff7-108">расположение объекта может измениться максимум на один пиксель;</span><span class="sxs-lookup"><span data-stu-id="02ff7-108">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="02ff7-109">выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.</span><span class="sxs-lookup"><span data-stu-id="02ff7-109">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="02ff7-110">По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="02ff7-110">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="02ff7-111">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="02ff7-111">Mitigation</span></span>  
 <span data-ttu-id="02ff7-112">Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел `<runtime>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="02ff7-112">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="02ff7-113">Для приложений, предназначенных для .NET Framework 4.6, для которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел `<runtime>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="02ff7-113">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="02ff7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="02ff7-114">See also</span></span>

- [<span data-ttu-id="02ff7-115">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="02ff7-115">Application compatibility</span></span>](application-compatibility.md)
