---
title: Разработка пользовательских элементов управления
description: Сведения о элементах управления Windows Form. В частности, вы научитесь объединять существующие элементы управления, расширять существующие элементы управления и создавать собственные пользовательские элементы управления.
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
ms.openlocfilehash: 12013496c9650489fdd7512206317000fc0ec78c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618380"
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="a8a51-104">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a8a51-104">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="a8a51-105">Элементы управления Windows Forms — это многократно используемые компоненты, которые инкапсулируют функциональность пользовательского интерфейса и используются в клиентских приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="a8a51-105">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="a8a51-106">Windows Forms предоставляет не только множество готовых к использованию элементов управления, но и инфраструктуру для разработки собственных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a8a51-106">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="a8a51-107">Вы можете объединять существующие элементы управления, расширять существующие или создавать пользовательские элементы управления.</span><span class="sxs-lookup"><span data-stu-id="a8a51-107">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="a8a51-108">В этом разделе приводятся дополнительные сведения и образцы, которые помогут вам в разработке элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a8a51-108">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8a51-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a8a51-109">In This Section</span></span>  
 [<span data-ttu-id="a8a51-110">Общие сведения об использовании элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8a51-110">Overview of Using Controls in Windows Forms</span></span>](overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="a8a51-111">Освещены главные особенности использования элементов управления в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a8a51-111">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="a8a51-112">Создание собственных элементов управления</span><span class="sxs-lookup"><span data-stu-id="a8a51-112">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="a8a51-113">Описываются различные типы пользовательских элементов управления, которые можно создать с помощью пространства имен <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8a51-113">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="a8a51-114">Основы разработки элементов управления форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8a51-114">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)  
 <span data-ttu-id="a8a51-115">Обсуждаются первые шаги в разработке элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a8a51-115">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="a8a51-116">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8a51-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)  
 <span data-ttu-id="a8a51-117">Показано, как добавлять свойства в элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a8a51-117">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="a8a51-118">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8a51-118">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)  
 <span data-ttu-id="a8a51-119">Показано, как обрабатывать и определять события в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a8a51-119">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="a8a51-120">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8a51-120">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="a8a51-121">Описываются атрибуты, которые можно применять к свойствам или другим членам пользовательских элементов управления и компонентов.</span><span class="sxs-lookup"><span data-stu-id="a8a51-121">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="a8a51-122">Рисование и отрисовка пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="a8a51-122">Custom Control Painting and Rendering</span></span>](custom-control-painting-and-rendering.md)  
 <span data-ttu-id="a8a51-123">Показано, как настраивать внешний вид элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a8a51-123">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="a8a51-124">Размещение элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8a51-124">Layout in Windows Forms Controls</span></span>](layout-in-windows-forms-controls.md)  
 <span data-ttu-id="a8a51-125">Показано, как создавать сложные макеты для элементов управления и форм.</span><span class="sxs-lookup"><span data-stu-id="a8a51-125">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="a8a51-126">Многопоточность в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8a51-126">Multithreading in Windows Forms Controls</span></span>](multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="a8a51-127">Показано, как реализовать многопоточные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="a8a51-127">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a8a51-128">Справочник</span><span class="sxs-lookup"><span data-stu-id="a8a51-128">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="a8a51-129">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="a8a51-129">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="a8a51-130">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="a8a51-130">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a8a51-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a8a51-131">Related Sections</span></span>  
 <span data-ttu-id="a8a51-132">[Атрибуты времени разработки для компонентов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a8a51-132">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="a8a51-133">Перечислены атрибуты метаданных, которые нужно применить к компонентам и элементам управления, чтобы они корректно отображались в режиме разработки в визуальных конструкторах.</span><span class="sxs-lookup"><span data-stu-id="a8a51-133">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="a8a51-134">[Расширения поддержки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a8a51-134">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="a8a51-135">Описывается, как реализовать такие классы, как редакторы и конструкторы, обеспечивающие поддержку во время разработки.</span><span class="sxs-lookup"><span data-stu-id="a8a51-135">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 <span data-ttu-id="a8a51-136">[Практическое руководство. Лицензирование компонентов и элементов управления](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a8a51-136">[How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span></span>  
 <span data-ttu-id="a8a51-137">Описывается, как реализовать лицензирование в элементе управления или компоненте.</span><span class="sxs-lookup"><span data-stu-id="a8a51-137">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="a8a51-138">См. также [Создание элементов управления Windows Forms во время разработки](developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="a8a51-138">Also see [Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md).</span></span>
