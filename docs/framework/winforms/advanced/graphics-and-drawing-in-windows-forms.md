---
title: Графика и рисование
description: Сведения об объектах графики, пера, кисти и цветах, а также о том, как выполнять такие задачи, как Рисование фигур, Рисование текста или отображение изображений в Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 58d8cde6aa102225cf9e3c342efe37218c818307
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618406"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="2775c-103">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2775c-103">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="2775c-104">Среда CLR использует расширенную реализацию Windows интерфейс графических устройств (GDI) с именем GDI+.</span><span class="sxs-lookup"><span data-stu-id="2775c-104">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="2775c-105">С помощью GDI+ можно создавать графики, рисовать текст и манипулировать графическими изображениями как объектами.</span><span class="sxs-lookup"><span data-stu-id="2775c-105">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="2775c-106">Интерфейс GDI+ обеспечивает производительность и простоту использования.</span><span class="sxs-lookup"><span data-stu-id="2775c-106">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="2775c-107">GDI+ можно использовать для отрисовки графических изображений на Windows Forms и элементы управления.</span><span class="sxs-lookup"><span data-stu-id="2775c-107">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="2775c-108">Хотя вы не можете использовать GDI+ непосредственно в веб-формах, можно отображать графические изображения с помощью серверного веб-элемента управления Image.</span><span class="sxs-lookup"><span data-stu-id="2775c-108">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="2775c-109">В этом разделе вы найдете разделы, в которых представлены основные принципы программирования GDI+.</span><span class="sxs-lookup"><span data-stu-id="2775c-109">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="2775c-110">Хотя он не является полным справочником, в нем содержатся сведения об объектах <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Color> и способах выполнения таких задач, как рисование фигур, создание текста, отображение рисунков.</span><span class="sxs-lookup"><span data-stu-id="2775c-110">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="2775c-111">Дополнительные сведения см. в [справочнике по GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="2775c-111">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="2775c-112">Если вы хотите немедленно приступить к работе, см. статью [Приступая к программированию графики](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="2775c-112">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="2775c-113">Она содержит разделы, посвященные использованию кода для рисования линий, фигур, текста и других элементов в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2775c-113">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2775c-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2775c-114">In This Section</span></span>  
 [<span data-ttu-id="2775c-115">Общие сведения о графике</span><span class="sxs-lookup"><span data-stu-id="2775c-115">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="2775c-116">Общие сведения об управляемых классах, связанных с графикой.</span><span class="sxs-lookup"><span data-stu-id="2775c-116">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="2775c-117">Управляемый код GDI+</span><span class="sxs-lookup"><span data-stu-id="2775c-117">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="2775c-118">Предоставляет сведения об управляемых классах GDI+.</span><span class="sxs-lookup"><span data-stu-id="2775c-118">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="2775c-119">Использование управляемых графических классов</span><span class="sxs-lookup"><span data-stu-id="2775c-119">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="2775c-120">Демонстрирует выполнение различных задач с помощью управляемых классов GDI+.</span><span class="sxs-lookup"><span data-stu-id="2775c-120">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2775c-121">Справочник</span><span class="sxs-lookup"><span data-stu-id="2775c-121">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="2775c-122">Предоставляет доступ к функциональным возможностям графического интерфейса GDI+ Basic.</span><span class="sxs-lookup"><span data-stu-id="2775c-122">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="2775c-123">Расширенные функциональные возможности для создания двухмерной и векторной графики.</span><span class="sxs-lookup"><span data-stu-id="2775c-123">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="2775c-124">Предоставляет расширенные функции работы с образами GDI+.</span><span class="sxs-lookup"><span data-stu-id="2775c-124">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="2775c-125">Предоставляет расширенные функции оформления GDI+.</span><span class="sxs-lookup"><span data-stu-id="2775c-125">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="2775c-126">Классы в этом пространстве имен позволяют создавать и использовать коллекции шрифтов.</span><span class="sxs-lookup"><span data-stu-id="2775c-126">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="2775c-127">Функции печати.</span><span class="sxs-lookup"><span data-stu-id="2775c-127">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2775c-128">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2775c-128">Related Sections</span></span>  
 [<span data-ttu-id="2775c-129">Рисование и отрисовка пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="2775c-129">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="2775c-130">Подробные сведения о способах написания кода для рисования элементов управления.</span><span class="sxs-lookup"><span data-stu-id="2775c-130">Details how to provide code for painting controls.</span></span>
