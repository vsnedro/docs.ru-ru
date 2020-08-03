---
title: Устранение рисков. Отрисовка окна WPF
description: Узнайте о последствии и устранении рисков при отрисовке содержимого окна WPF в .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий.
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: d624478d17a4076107438f71b0a86eeb6d9f3ea4
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475337"
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="d211d-103">Устранение рисков. Отрисовка окна WPF</span><span class="sxs-lookup"><span data-stu-id="d211d-103">Mitigation: WPF Window Rendering</span></span>

<span data-ttu-id="d211d-104">В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов.</span><span class="sxs-lookup"><span data-stu-id="d211d-104">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>

## <a name="impact"></a><span data-ttu-id="d211d-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="d211d-105">Impact</span></span>

<span data-ttu-id="d211d-106">Как правило, отображение всего окна на нескольких мониторах без усечения является ожидаемым поведением.</span><span class="sxs-lookup"><span data-stu-id="d211d-106">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="d211d-107">Тем не менее, в Windows 7 и более ранних версий окна WPF обрезаются в случае выхода за пределы одного экрана, так как отрисовка части окна на втором мониторе значительно снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="d211d-107">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>

<span data-ttu-id="d211d-108">Из-за влияния большого числа факторов невозможно указать точные сведения о том, как отображение окон WPF на нескольких мониторах в Windows 8 и более поздних версий воздействует на производительность.</span><span class="sxs-lookup"><span data-stu-id="d211d-108">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="d211d-109">В некоторых случаях это по-прежнему может оказывать нежелательное влияние на производительность, особенно для пользователей, запускающих приложения, которые обрабатывают большие объемы графических данных, с разнесением окон на несколько мониторов.</span><span class="sxs-lookup"><span data-stu-id="d211d-109">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="d211d-110">В других случаях может просто требоваться согласованное поведение разных версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d211d-110">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>

## <a name="mitigation"></a><span data-ttu-id="d211d-111">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="d211d-111">Mitigation</span></span>

<span data-ttu-id="d211d-112">Можно отключить это изменение и вернуться к предыдущему поведению обрезки окна WPF, когда оно выходит за пределы одного экрана.</span><span class="sxs-lookup"><span data-stu-id="d211d-112">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="d211d-113">Это можно сделать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="d211d-113">There are two ways to do this:</span></span>

- <span data-ttu-id="d211d-114">Добавив элемент `<EnableMultiMonitorDisplayClipping>` в раздел `<appSettings>` файла конфигурации приложения, можно включить или отключить это поведение для приложений, выполняющихся в Windows 8 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d211d-114">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="d211d-115">Например, следующий раздел конфигурации отключает отрисовку без обрезки.</span><span class="sxs-lookup"><span data-stu-id="d211d-115">For example, the following configuration section disables rendering without clipping:</span></span>

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  <span data-ttu-id="d211d-116">Параметр конфигурации `<EnableMultiMonitorDisplayClipping>` может иметь одно из двух значений:</span><span class="sxs-lookup"><span data-stu-id="d211d-116">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>

  - <span data-ttu-id="d211d-117">`true` — для включения обрезки окон по границам монитора во время отрисовки;</span><span class="sxs-lookup"><span data-stu-id="d211d-117">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>

  - <span data-ttu-id="d211d-118">`false` — для отключения обрезки окон по границам монитора во время отрисовки.</span><span class="sxs-lookup"><span data-stu-id="d211d-118">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>

- <span data-ttu-id="d211d-119">Путем задания значения `true` для свойства <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="d211d-119">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>

## <a name="see-also"></a><span data-ttu-id="d211d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d211d-120">See also</span></span>

- [<span data-ttu-id="d211d-121">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="d211d-121">Application compatibility</span></span>](application-compatibility.md)
