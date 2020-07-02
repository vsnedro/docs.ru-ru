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
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Практическое руководство. Рисование эллипса или круга
В этом примере показано, как рисовать эллипсы и окружности с помощью <xref:System.Windows.Shapes.Ellipse> элемента. Чтобы нарисовать эллипс, создайте <xref:System.Windows.Shapes.Ellipse> элемент и укажите его свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> . Используйте его <xref:System.Windows.Shapes.Shape.Fill%2A> свойство, чтобы указать <xref:System.Windows.Media.Brush> , используемое для заполнения внутренней части эллипса. Используйте его <xref:System.Windows.Shapes.Shape.Stroke%2A> свойство, чтобы указать объект <xref:System.Windows.Media.Brush> , используемый для рисования контура эллипса. <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>Свойство задает толщину контура эллипса.  
  
 Чтобы нарисовать круг, сделайте <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> элемента, <xref:System.Windows.Shapes.Ellipse> равным друг другу.  
  
 В следующем примере показано рисование четырех <xref:System.Windows.Shapes.Ellipse> элементов в <xref:System.Windows.Controls.Canvas> .  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Хотя в этом примере используется, <xref:System.Windows.Controls.Canvas> чтобы содержать многоточия, можно использовать элементы Ellipse (и все остальные элементы Shape) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающим нетекстовое содержимое.  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Дополнительно

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
