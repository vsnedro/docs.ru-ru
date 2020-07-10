---
title: Практическое руководство. Создание растрового изображения во время выполнения
description: Узнайте, как создать растровый объект и отобразить его в существующем Windows Forms элементе управления PictureBox.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], creating
- bitmaps [Windows Forms], examples [Visual Basic]
ms.assetid: 737bae30-e599-4e1d-bf30-bab8280b32be
ms.openlocfilehash: e18f58abb93744aeb567ec8dc1a41004565c2bd3
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174722"
---
# <a name="how-to-create-a-bitmap-at-run-time"></a>Практическое руководство. Создание растрового изображения во время выполнения
В этом примере создается и рисуется <xref:System.Drawing.Bitmap> объект, который отображается в существующем <xref:System.Windows.Forms.PictureBox> элементе управления Windows Forms.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Drawing.CreateBitmapAtRuntime#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CreateBitmapAtRuntime/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.CreateBitmapAtRuntime#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CreateBitmapAtRuntime/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- Форма Windows Forms, которая импортирует сборки System, System. Drawing и System. Windows. Forms.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Bitmap>
- [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](images-bitmaps-and-metafiles.md)
