---
title: Практическое руководство. Рисование линии в Windows Forms
description: Узнайте, как рисовать линию в форме, обрабатывая событие Paint, а затем выполнив Рисование с помощью свойства Graphics объекта PaintEventArgs.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621630"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Практическое руководство. Рисование линии в Windows Forms
В этом примере рисуется линия на форме. Как правило, при рисовании на форме обрабатывается <xref:System.Windows.Forms.Control.Paint> событие формы и выполняется рисование с помощью <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> свойства объекта <xref:System.Windows.Forms.PaintEventArgs> , как показано в этом примере.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Всегда следует вызывать <xref:System.IDisposable.Dispose%2A> для любых объектов, использующих системные ресурсы, например <xref:System.Drawing.Pen> объекты.  
  
## <a name="see-also"></a>См. также

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Приступая к программированию графики](getting-started-with-graphics-programming.md)
- [Рисование линий и фигур с помощью пера](using-a-pen-to-draw-lines-and-shapes.md)
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
