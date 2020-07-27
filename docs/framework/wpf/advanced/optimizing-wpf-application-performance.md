---
title: Оптимизация производительности приложения
description: Используйте эти ресурсы для повышения производительности Windows Presentation Foundation приложений, таких как планирование производительности и использование преимуществ оборудования.
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 165caaf102a66988db0254839a947b8e262a386d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166335"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="7ed6e-103">Улучшение производительности приложений WPF</span><span class="sxs-lookup"><span data-stu-id="7ed6e-103">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="7ed6e-104">Этот раздел предназначен для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] разработчиков приложений, которые ищут способы улучшения производительности приложений.</span><span class="sxs-lookup"><span data-stu-id="7ed6e-104">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="7ed6e-105">Если вы являетесь разработчиком, который впервые работает с Microsoft .NET Framework и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , сначала ознакомьтесь с обеими платформами.</span><span class="sxs-lookup"><span data-stu-id="7ed6e-105">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="7ed6e-106">В этом разделе предполагается работа с базами знаний и написана для программистов, которые уже знакомы, чтобы заставить их работать.</span><span class="sxs-lookup"><span data-stu-id="7ed6e-106">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ed6e-107">Данные о производительности, приведенные в этом разделе, основаны на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениях, работающих на ПК с частотой 2,8 ГГц и 512 ОЗУ и графической карте ATI Radeon 9700.</span><span class="sxs-lookup"><span data-stu-id="7ed6e-107">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ed6e-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7ed6e-108">In This Section</span></span>  
 [<span data-ttu-id="7ed6e-109">Планирование производительности приложения</span><span class="sxs-lookup"><span data-stu-id="7ed6e-109">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="7ed6e-110">Использование преимуществ оборудования</span><span class="sxs-lookup"><span data-stu-id="7ed6e-110">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="7ed6e-111">Разметка и разработка</span><span class="sxs-lookup"><span data-stu-id="7ed6e-111">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="7ed6e-112">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="7ed6e-112">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="7ed6e-113">Поведение объекта</span><span class="sxs-lookup"><span data-stu-id="7ed6e-113">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="7ed6e-114">Ресурсы приложений</span><span class="sxs-lookup"><span data-stu-id="7ed6e-114">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="7ed6e-115">Текст</span><span class="sxs-lookup"><span data-stu-id="7ed6e-115">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="7ed6e-116">Привязка данных</span><span class="sxs-lookup"><span data-stu-id="7ed6e-116">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="7ed6e-117">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="7ed6e-117">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="7ed6e-118">Дополнительные рекомендации по повышению производительности</span><span class="sxs-lookup"><span data-stu-id="7ed6e-118">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="7ed6e-119">Время запуска приложения</span><span class="sxs-lookup"><span data-stu-id="7ed6e-119">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ed6e-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7ed6e-120">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="7ed6e-121">Уровни графической отрисовки</span><span class="sxs-lookup"><span data-stu-id="7ed6e-121">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="7ed6e-122">Общие сведения об отрисовке графики в WPF</span><span class="sxs-lookup"><span data-stu-id="7ed6e-122">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="7ed6e-123">Макет</span><span class="sxs-lookup"><span data-stu-id="7ed6e-123">Layout</span></span>](layout.md)
- [<span data-ttu-id="7ed6e-124">Деревья в WPF</span><span class="sxs-lookup"><span data-stu-id="7ed6e-124">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="7ed6e-125">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="7ed6e-125">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="7ed6e-126">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="7ed6e-126">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="7ed6e-127">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="7ed6e-127">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="7ed6e-128">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="7ed6e-128">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="7ed6e-129">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="7ed6e-129">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="7ed6e-130">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="7ed6e-130">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="7ed6e-131">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="7ed6e-131">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="7ed6e-132">Оформление в WPF</span><span class="sxs-lookup"><span data-stu-id="7ed6e-132">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="7ed6e-133">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="7ed6e-133">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7ed6e-134">Общие сведения о переходах</span><span class="sxs-lookup"><span data-stu-id="7ed6e-134">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="7ed6e-135">Советы и рекомендации по анимации</span><span class="sxs-lookup"><span data-stu-id="7ed6e-135">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="7ed6e-136">Пошаговое руководство. Кэширование данных приложения WPF</span><span class="sxs-lookup"><span data-stu-id="7ed6e-136">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
