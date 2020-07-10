---
title: Практическое руководство. Печать формы Windows Forms
description: Узнайте, как программно распечатать копию текущей формы Windows с помощью метода Копифромскрин.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174696"
---
# <a name="how-to-print-a-windows-form"></a>Практическое руководство. Печать формы Windows Forms
Как часть процесса разработки, обычно требуется распечатать копию формы Windows Forms. В следующем примере кода показано, как напечатать копию текущей формы с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метода.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
- У вас нет разрешения на доступ к принтеру.  
  
- Принтер не установлен.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  
 Чтобы запустить этот пример кода, необходимо иметь разрешение на доступ к принтеру, который используется на компьютере.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Printing.PrintDocument>
- [Практическое руководство. Отрисовка изображений с использованием GDI+](how-to-render-images-with-gdi.md)
- [Практическое руководство. Печать графических изображений в Windows Forms](how-to-print-graphics-in-windows-forms.md)
