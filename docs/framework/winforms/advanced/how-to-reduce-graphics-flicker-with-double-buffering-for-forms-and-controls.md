---
title: Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления
description: Узнайте, как уменьшить мерцание графики с помощью двойной буферизации для Windows Forms и использовать элементы управления для решения проблем мерцания, связанных с операциями рисования.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618133"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления
Двойная буферизация использует буфер памяти для решения проблем мерцания, связанных с несколькими операциями рисования. Если двойная буферизация включена, все операции рисования сначала обрабатываются в буфере памяти вместо области рисования на экране. После завершения всех операций рисования буфер памяти копируется непосредственно в связанную с ним область рисования. Поскольку на экране выполняется только одна графическая операция, мерцание изображения, связанного с сложными операциями рисования, исключается. Для большинства приложений для получения наилучших результатов используется двойная буферизация по умолчанию, предоставляемая .NET Framework. Стандартные элементы управления Windows Forms по умолчанию имеют двойную буферизацию. Вы можете включить двойную буферизацию по умолчанию в формах и созданных элементах управления двумя способами. Можно либо присвоить <xref:System.Windows.Forms.Control.DoubleBuffered%2A> свойству значение `true` , либо вызвать метод, <xref:System.Windows.Forms.Control.SetStyle%2A> чтобы установить для <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> флага значение `true` . Оба метода будут включать двойную буферизацию по умолчанию для формы или элемента управления и обеспечивать визуализацию графики без мерцания. Вызов <xref:System.Windows.Forms.Control.SetStyle%2A> метода рекомендуется только для пользовательских элементов управления, для которых написан весь код отрисовки.  
  
 Для более сложных сценариев двойного буферизации, таких как анимация или расширенное управление памятью, можно реализовать собственную логику двойной буферизации. Дополнительные сведения см. [в разделе руководство. Управление буферизованными графиками вручную](how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Уменьшение мерцания  
  
- Задайте для свойства <xref:System.Windows.Forms.Control.DoubleBuffered%2A> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- или -  
  
- Вызовите <xref:System.Windows.Forms.Control.SetStyle%2A> метод, чтобы задать <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> для флага значение `true` .  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [Двойная буферизация графики](double-buffered-graphics.md)
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
