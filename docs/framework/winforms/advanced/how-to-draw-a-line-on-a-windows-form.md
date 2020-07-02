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
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="03151-103">Практическое руководство. Рисование линии в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03151-103">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="03151-104">В этом примере рисуется линия на форме.</span><span class="sxs-lookup"><span data-stu-id="03151-104">This example draws a line on a form.</span></span> <span data-ttu-id="03151-105">Как правило, при рисовании на форме обрабатывается <xref:System.Windows.Forms.Control.Paint> событие формы и выполняется рисование с помощью <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> свойства объекта <xref:System.Windows.Forms.PaintEventArgs> , как показано в этом примере.</span><span class="sxs-lookup"><span data-stu-id="03151-105">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="03151-106">Пример</span><span class="sxs-lookup"><span data-stu-id="03151-106">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03151-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="03151-107">Compiling the Code</span></span>  
 <span data-ttu-id="03151-108">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="03151-108">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="03151-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="03151-109">Robust Programming</span></span>  
 <span data-ttu-id="03151-110">Всегда следует вызывать <xref:System.IDisposable.Dispose%2A> для любых объектов, использующих системные ресурсы, например <xref:System.Drawing.Pen> объекты.</span><span class="sxs-lookup"><span data-stu-id="03151-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03151-111">См. также</span><span class="sxs-lookup"><span data-stu-id="03151-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="03151-112">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="03151-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="03151-113">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="03151-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="03151-114">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03151-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
