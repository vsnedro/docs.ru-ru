---
title: Практическое руководство. Рисование эллипса или круга
description: Научитесь рисовать эллипс или окружность с помощью вариантов толщины контура и внутреннего цвета в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: afa0e7d2af42aaee39dca164f23b1a1cacf430ca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853563"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="2bfd2-103">Практическое руководство. Рисование эллипса или круга</span><span class="sxs-lookup"><span data-stu-id="2bfd2-103">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="2bfd2-104">В этом примере показано, как рисовать эллипсы и окружности с помощью <xref:System.Windows.Shapes.Ellipse> элемента.</span><span class="sxs-lookup"><span data-stu-id="2bfd2-104">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="2bfd2-105">Чтобы нарисовать эллипс, создайте <xref:System.Windows.Shapes.Ellipse> элемент и укажите его свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="2bfd2-105">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="2bfd2-106">Используйте его <xref:System.Windows.Shapes.Shape.Fill%2A> свойство, чтобы указать <xref:System.Windows.Media.Brush> , используемое для заполнения внутренней части эллипса.</span><span class="sxs-lookup"><span data-stu-id="2bfd2-106">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="2bfd2-107">Используйте его <xref:System.Windows.Shapes.Shape.Stroke%2A> свойство, чтобы указать объект <xref:System.Windows.Media.Brush> , используемый для рисования контура эллипса.</span><span class="sxs-lookup"><span data-stu-id="2bfd2-107">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="2bfd2-108"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>Свойство задает толщину контура эллипса.</span><span class="sxs-lookup"><span data-stu-id="2bfd2-108">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="2bfd2-109">Чтобы нарисовать круг, сделайте <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> элемента, <xref:System.Windows.Shapes.Ellipse> равным друг другу.</span><span class="sxs-lookup"><span data-stu-id="2bfd2-109">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="2bfd2-110">В следующем примере показано рисование четырех <xref:System.Windows.Shapes.Ellipse> элементов в <xref:System.Windows.Controls.Canvas> .</span><span class="sxs-lookup"><span data-stu-id="2bfd2-110">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bfd2-111">Пример</span><span class="sxs-lookup"><span data-stu-id="2bfd2-111">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="2bfd2-112">Хотя в этом примере используется, <xref:System.Windows.Controls.Canvas> чтобы содержать многоточия, можно использовать элементы Ellipse (и все остальные элементы Shape) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающим нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="2bfd2-112">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="2bfd2-113">Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="2bfd2-113">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bfd2-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2bfd2-114">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="2bfd2-115">Пример элементов Shape</span><span class="sxs-lookup"><span data-stu-id="2bfd2-115">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
