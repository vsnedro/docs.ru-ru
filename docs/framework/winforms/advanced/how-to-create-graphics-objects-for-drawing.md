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
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="e3e95-103">Практическое руководство. Создание графических объектов для рисования</span><span class="sxs-lookup"><span data-stu-id="e3e95-103">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="e3e95-104">Прежде чем рисовать линии и фигуры, отображать текст или отображать изображения и управлять ими с помощью GDI+, необходимо создать <xref:System.Drawing.Graphics> объект.</span><span class="sxs-lookup"><span data-stu-id="e3e95-104">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e3e95-105"><xref:System.Drawing.Graphics>Объект представляет поверхность рисования GDI+, а — объект, используемый для создания графических изображений.</span><span class="sxs-lookup"><span data-stu-id="e3e95-105">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="e3e95-106">Работа с графикой состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="e3e95-106">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="e3e95-107">Создание <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="e3e95-107">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="e3e95-108">Использование <xref:System.Drawing.Graphics> объекта для рисования линий и фигур, отображения текста или отображения изображений и управления ими.</span><span class="sxs-lookup"><span data-stu-id="e3e95-108">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="e3e95-109">Создание графического объекта</span><span class="sxs-lookup"><span data-stu-id="e3e95-109">Creating a Graphics Object</span></span>  
 <span data-ttu-id="e3e95-110">Графический объект может быть создан различными способами.</span><span class="sxs-lookup"><span data-stu-id="e3e95-110">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="e3e95-111">Создание графического объекта</span><span class="sxs-lookup"><span data-stu-id="e3e95-111">To create a graphics object</span></span>  
  
- <span data-ttu-id="e3e95-112">Получение ссылки на графический объект в составе <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> события формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e3e95-112">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="e3e95-113">Обычно это способ получения ссылки на графический объект при создании кода рисования для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e3e95-113">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="e3e95-114">Аналогично, объект Graphics можно также получить как свойство объекта <xref:System.Drawing.Printing.PrintPageEventArgs> при обработке <xref:System.Drawing.Printing.PrintDocument.PrintPage> события для <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="e3e95-114">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="e3e95-115">-или-</span><span class="sxs-lookup"><span data-stu-id="e3e95-115">-or-</span></span>  
  
- <span data-ttu-id="e3e95-116">Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы, чтобы получить ссылку на <xref:System.Drawing.Graphics> объект, представляющий поверхность рисования этого элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="e3e95-116">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="e3e95-117">Используйте этот метод, если требуется рисовать на форме или элементе управления, который уже существует.</span><span class="sxs-lookup"><span data-stu-id="e3e95-117">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="e3e95-118">-или-</span><span class="sxs-lookup"><span data-stu-id="e3e95-118">-or-</span></span>  
  
- <span data-ttu-id="e3e95-119">Создайте <xref:System.Drawing.Graphics> объект из любого объекта, наследующего от <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="e3e95-119">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="e3e95-120">Этот подход удобен, если требуется изменить уже существующий образ.</span><span class="sxs-lookup"><span data-stu-id="e3e95-120">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="e3e95-121">Следующие разделы содержат сведения о каждом из этих процессов.</span><span class="sxs-lookup"><span data-stu-id="e3e95-121">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="e3e95-122">PaintEventArgs в обработчике событий Paint</span><span class="sxs-lookup"><span data-stu-id="e3e95-122">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="e3e95-123">При программировании <xref:System.Windows.Forms.PaintEventHandler> для элементов управления или <xref:System.Drawing.Printing.PrintDocument.PrintPage> для <xref:System.Drawing.Printing.PrintDocument> объект Graphics предоставляется как одно из свойств <xref:System.Windows.Forms.PaintEventArgs> или <xref:System.Drawing.Printing.PrintPageEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="e3e95-123">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="e3e95-124">Получение ссылки на объект Graphics из PaintEventArgs в событии Paint</span><span class="sxs-lookup"><span data-stu-id="e3e95-124">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="e3e95-125">Объявите <xref:System.Drawing.Graphics> объект.</span><span class="sxs-lookup"><span data-stu-id="e3e95-125">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="e3e95-126">Назначьте переменную для ссылки на <xref:System.Drawing.Graphics> объект, передаваемый как часть <xref:System.Windows.Forms.PaintEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="e3e95-126">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="e3e95-127">Вставка кода для заполнения формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e3e95-127">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="e3e95-128">В следующем примере показано, как ссылаться на <xref:System.Drawing.Graphics> объект из <xref:System.Windows.Forms.PaintEventArgs> в <xref:System.Windows.Forms.Control.Paint> событии.</span><span class="sxs-lookup"><span data-stu-id="e3e95-128">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="e3e95-129">Метод CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="e3e95-129">CreateGraphics Method</span></span>  
 <span data-ttu-id="e3e95-130">Можно также использовать <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод элемента управления или формы для получения ссылки на <xref:System.Drawing.Graphics> объект, представляющий поверхность рисования этого элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="e3e95-130">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="e3e95-131">Создание графического объекта с помощью метода CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="e3e95-131">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="e3e95-132">Вызовите <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод формы или элемента управления, для которого требуется отобразить графические объекты.</span><span class="sxs-lookup"><span data-stu-id="e3e95-132">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="e3e95-133">Создание из объекта Image</span><span class="sxs-lookup"><span data-stu-id="e3e95-133">Create from an Image Object</span></span>  
 <span data-ttu-id="e3e95-134">Кроме того, можно создать графический объект из любого объекта, производного от <xref:System.Drawing.Image> класса.</span><span class="sxs-lookup"><span data-stu-id="e3e95-134">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="e3e95-135">Создание графического объекта из изображения</span><span class="sxs-lookup"><span data-stu-id="e3e95-135">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="e3e95-136">Вызовите <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> метод, указав имя переменной изображения, из которой нужно создать <xref:System.Drawing.Graphics> объект.</span><span class="sxs-lookup"><span data-stu-id="e3e95-136">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="e3e95-137">В следующем примере показано, как использовать <xref:System.Drawing.Bitmap> объект:</span><span class="sxs-lookup"><span data-stu-id="e3e95-137">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="e3e95-138">Создавать объекты можно только <xref:System.Drawing.Graphics> из неиндексированных BMP-файлов, таких как 16-разрядные, 24-разрядные и 32-битовые BMP.</span><span class="sxs-lookup"><span data-stu-id="e3e95-138">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="e3e95-139">Каждый пиксель неиндексированных BMP-файлов содержит цвет, в отличие от пикселов индексированных BMP-файлов, которые содержат индекс для таблицы цветов.</span><span class="sxs-lookup"><span data-stu-id="e3e95-139">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="e3e95-140">Рисование фигур и изображений и управление ими</span><span class="sxs-lookup"><span data-stu-id="e3e95-140">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="e3e95-141">После создания <xref:System.Drawing.Graphics> объект может использоваться для рисования линий и фигур, отображения текста или отображения изображений и управления ими.</span><span class="sxs-lookup"><span data-stu-id="e3e95-141">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="e3e95-142">Объекты Principal, используемые с <xref:System.Drawing.Graphics> объектом:</span><span class="sxs-lookup"><span data-stu-id="e3e95-142">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="e3e95-143"><xref:System.Drawing.Pen>Класс, используемый для рисования линий, структурирования фигур или визуализации других геометрических представлений.</span><span class="sxs-lookup"><span data-stu-id="e3e95-143">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="e3e95-144"><xref:System.Drawing.Brush>Класс, используемый для заливки областей графических объектов, таких как заполненные фигуры, изображения или текст.</span><span class="sxs-lookup"><span data-stu-id="e3e95-144">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="e3e95-145"><xref:System.Drawing.Font>Класс — содержит описание фигур, используемых при отрисовке текста.</span><span class="sxs-lookup"><span data-stu-id="e3e95-145">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="e3e95-146"><xref:System.Drawing.Color>Структура — представляет различные отображаемые цвета.</span><span class="sxs-lookup"><span data-stu-id="e3e95-146">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="e3e95-147">Использование созданного объекта Graphics</span><span class="sxs-lookup"><span data-stu-id="e3e95-147">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="e3e95-148">Для рисования нужного объекта выполните действия с соответствующим объектом, приведенным выше.</span><span class="sxs-lookup"><span data-stu-id="e3e95-148">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="e3e95-149">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="e3e95-149">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="e3e95-150">Для подготовки к просмотру</span><span class="sxs-lookup"><span data-stu-id="e3e95-150">To render</span></span>|<span data-ttu-id="e3e95-151">См.</span><span class="sxs-lookup"><span data-stu-id="e3e95-151">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="e3e95-152">Линии</span><span class="sxs-lookup"><span data-stu-id="e3e95-152">Lines</span></span>|[<span data-ttu-id="e3e95-153">Практическое руководство. Рисование линии в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e3e95-153">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="e3e95-154">Фигуры</span><span class="sxs-lookup"><span data-stu-id="e3e95-154">Shapes</span></span>|[<span data-ttu-id="e3e95-155">Практическое руководство. Рисование линии или контурной фигуры</span><span class="sxs-lookup"><span data-stu-id="e3e95-155">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="e3e95-156">текст</span><span class="sxs-lookup"><span data-stu-id="e3e95-156">Text</span></span>|[<span data-ttu-id="e3e95-157">Практическое руководство. Отрисовка текста в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e3e95-157">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="e3e95-158">Изображения</span><span class="sxs-lookup"><span data-stu-id="e3e95-158">Images</span></span>|[<span data-ttu-id="e3e95-159">Практическое руководство. Отрисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="e3e95-159">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="e3e95-160">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e3e95-160">See also</span></span>

- [<span data-ttu-id="e3e95-161">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="e3e95-161">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e3e95-162">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e3e95-162">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e3e95-163">Прямые и кривые линии и фигуры</span><span class="sxs-lookup"><span data-stu-id="e3e95-163">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="e3e95-164">Практическое руководство. Отрисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="e3e95-164">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
