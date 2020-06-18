---
title: Практическое руководство. Создание графических объектов для рисования
description: Научитесь создавать графические объекты, необходимые для рисования линий и фигур, отображения текста, а также для отображения изображений и управления ими с помощью GDI+.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: 1a0884c1e9956dc6f4608e32372deeea24ef4670
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903211"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Практическое руководство. Создание графических объектов для рисования
Прежде чем рисовать линии и фигуры, отображать текст или отображать изображения и управлять ими с помощью GDI+, необходимо создать <xref:System.Drawing.Graphics> объект. <xref:System.Drawing.Graphics>Объект представляет поверхность рисования GDI+, а — объект, используемый для создания графических изображений.  
  
 Работа с графикой состоит из двух этапов.  
  
1. Создание <xref:System.Drawing.Graphics> объекта.  
  
2. Использование <xref:System.Drawing.Graphics> объекта для рисования линий и фигур, отображения текста или отображения изображений и управления ими.  
  
## <a name="creating-a-graphics-object"></a>Создание графического объекта  
 Графический объект может быть создан различными способами.  
  
#### <a name="to-create-a-graphics-object"></a>Создание графического объекта  
  
- Получение ссылки на графический объект в составе <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> события формы или элемента управления. Обычно это способ получения ссылки на графический объект при создании кода рисования для элемента управления. Аналогично, объект Graphics можно также получить как свойство объекта <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке <xref:System.Drawing.Printing.PrintDocument.PrintPage> события для <xref:System.Drawing.Printing.PrintDocument> .  
  
     -или-  
  
- Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы, чтобы получить ссылку на <xref:System.Drawing.Graphics> объект, представляющий поверхность рисования этого элемента управления или формы. Используйте этот метод, если требуется рисовать на форме или элементе управления, который уже существует.  
  
     -или-  
  
- Создайте <xref:System.Drawing.Graphics> объект из любого объекта, наследующего от <xref:System.Drawing.Image> . Этот подход удобен, если требуется изменить уже существующий образ.  
  
     Следующие разделы содержат сведения о каждом из этих процессов.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs в обработчике событий Paint  
 При программировании <xref:System.Windows.Forms.PaintEventHandler> для элементов управления или <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument> объект Graphics предоставляется как одно из свойств <xref:System.Windows.Forms.PaintEventArgs> или <xref:System.Drawing.Printing.PrintPageEventArgs> .  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Получение ссылки на объект Graphics из PaintEventArgs в событии Paint  
  
1. Объявите <xref:System.Drawing.Graphics> объект.  
  
2. Назначьте переменную для ссылки на <xref:System.Drawing.Graphics> объект, передаваемый как часть <xref:System.Windows.Forms.PaintEventArgs> .  
  
3. Вставка кода для заполнения формы или элемента управления.  
  
     В следующем примере показано, как ссылаться на <xref:System.Drawing.Graphics> объект из <xref:System.Windows.Forms.PaintEventArgs> в <xref:System.Windows.Forms.Control.Paint> событии.  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,
       System.Windows.Forms.PaintEventArgs pe)
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a>Метод CreateGraphics  
 Можно также использовать <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы для получения ссылки на <xref:System.Drawing.Graphics> объект, представляющий поверхность рисования этого элемента управления или формы.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Создание графического объекта с помощью метода CreateGraphics  
  
- Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод формы или элемента управления, для которого требуется отобразить графические объекты.  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a>Создание из объекта Image  
 Кроме того, можно создать графический объект из любого объекта, производного от <xref:System.Drawing.Image> класса.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Создание графического объекта из изображения  
  
- Вызовите <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> метод, указав имя переменной изображения, из которой нужно создать <xref:System.Drawing.Graphics> объект.  
  
     В следующем примере показано, как использовать <xref:System.Drawing.Bitmap> объект:  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
> Создавать объекты можно только <xref:System.Drawing.Graphics> из неиндексированных BMP-файлов, таких как 16-разрядные, 24-разрядные и 32-битовые BMP. Каждый пиксель неиндексированных BMP-файлов содержит цвет, в отличие от пикселов индексированных BMP-файлов, которые содержат индекс для таблицы цветов.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Рисование фигур и изображений и управление ими  
 После создания <xref:System.Drawing.Graphics> объект может использоваться для рисования линий и фигур, отображения текста или отображения изображений и управления ими. Объекты Principal, используемые с <xref:System.Drawing.Graphics> объектом:  
  
- <xref:System.Drawing.Pen>Класс, используемый для рисования линий, структурирования фигур или визуализации других геометрических представлений.  
  
- <xref:System.Drawing.Brush>Класс, используемый для заливки областей графических объектов, таких как заполненные фигуры, изображения или текст.  
  
- <xref:System.Drawing.Font>Класс — содержит описание фигур, используемых при отрисовке текста.  
  
- <xref:System.Drawing.Color>Структура — представляет различные отображаемые цвета.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Использование созданного объекта Graphics  
  
- Для рисования нужного объекта выполните действия с соответствующим объектом, приведенным выше.  
  
     Дополнительные сведения см. в следующих разделах:  
  
    |Для подготовки к просмотру|См.|  
    |---------------|---------|  
    |Линии|[Практическое руководство. Рисование линии в Windows Forms](how-to-draw-a-line-on-a-windows-form.md)|  
    |Фигуры|[Практическое руководство. Рисование линии или контурной фигуры](how-to-draw-an-outlined-shape.md)|  
    |текст|[Практическое руководство. Отрисовка текста в Windows Forms](how-to-draw-text-on-a-windows-form.md)|  
    |Изображения|[Практическое руководство. Отрисовка изображений с использованием GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>См. также раздел

- [Приступая к программированию графики](getting-started-with-graphics-programming.md)
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Прямые и кривые линии и фигуры](lines-curves-and-shapes.md)
- [Практическое руководство. Отрисовка изображений с использованием GDI+](how-to-render-images-with-gdi.md)
