---
title: Практическое руководство. Рисование заполненного прямоугольника в Windows Forms
description: Узнайте, как программным путем нарисовать закрашенный прямоугольник в форме Windows. Также Узнайте о компиляции кода.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621643"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>Практическое руководство. Рисование заполненного прямоугольника в Windows Forms
В этом примере на форме рисуется закрашенный прямоугольник.  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Этот метод нельзя вызвать в <xref:System.Windows.Forms.Form.Load> обработчике событий. Нарисованное содержимое не будет перерисовано при изменении размера формы или его скрытии другой формой. Чтобы сделать содержимое автоматически перерисовкой, необходимо переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Всегда следует вызывать <xref:System.IDisposable.Dispose%2A> для всех объектов, использующих системные ресурсы, например <xref:System.Drawing.Brush> <xref:System.Drawing.Graphics> объекты и.  
  
## <a name="see-also"></a>См. также

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Приступая к программированию графики](getting-started-with-graphics-programming.md)
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Рисование линий и фигур с помощью пера](using-a-pen-to-draw-lines-and-shapes.md)
- [Кисти и закрашенные фигуры в GDI+](brushes-and-filled-shapes-in-gdi.md)
