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
# <a name="graphics-and-drawing-in-windows-forms"></a>Объекты Graphics и Drawing в Windows Forms
Среда CLR использует расширенную реализацию Windows интерфейс графических устройств (GDI) с именем GDI+. С помощью GDI+ можно создавать графики, рисовать текст и манипулировать графическими изображениями как объектами. Интерфейс GDI+ обеспечивает производительность и простоту использования. GDI+ можно использовать для отрисовки графических изображений на Windows Forms и элементы управления. Хотя вы не можете использовать GDI+ непосредственно в веб-формах, можно отображать графические изображения с помощью серверного веб-элемента управления Image.  
  
 В этом разделе вы найдете разделы, в которых представлены основные принципы программирования GDI+. Хотя он не является полным справочником, в нем содержатся сведения об объектах <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Color> и способах выполнения таких задач, как рисование фигур, создание текста, отображение рисунков. Дополнительные сведения см. в [справочнике по GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Если вы хотите немедленно приступить к работе, см. статью [Приступая к программированию графики](getting-started-with-graphics-programming.md). Она содержит разделы, посвященные использованию кода для рисования линий, фигур, текста и других элементов в формах Windows Forms.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения о графике](graphics-overview-windows-forms.md)  
 Общие сведения об управляемых классах, связанных с графикой.  
  
 [Управляемый код GDI+](about-gdi-managed-code.md)  
 Предоставляет сведения об управляемых классах GDI+.  
  
 [Использование управляемых графических классов](using-managed-graphics-classes.md)  
 Демонстрирует выполнение различных задач с помощью управляемых классов GDI+.  
  
## <a name="reference"></a>Справочник  
 <xref:System.Drawing>  
 Предоставляет доступ к функциональным возможностям графического интерфейса GDI+ Basic.  
  
 <xref:System.Drawing.Drawing2D>  
 Расширенные функциональные возможности для создания двухмерной и векторной графики.  
  
 <xref:System.Drawing.Imaging>  
 Предоставляет расширенные функции работы с образами GDI+.  
  
 <xref:System.Drawing.Text>  
 Предоставляет расширенные функции оформления GDI+. Классы в этом пространстве имен позволяют создавать и использовать коллекции шрифтов.  
  
 <xref:System.Drawing.Printing>  
 Функции печати.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Рисование и отрисовка пользовательского элемента управления](../controls/custom-control-painting-and-rendering.md)  
 Подробные сведения о способах написания кода для рисования элементов управления.
