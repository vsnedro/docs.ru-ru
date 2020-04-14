---
title: Практическое руководство. Вывод текста по контуру
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278929"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="c9a50-102">Как: Создать изложенный текст</span><span class="sxs-lookup"><span data-stu-id="c9a50-102">How to: Create outlined text</span></span>

<span data-ttu-id="c9a50-103">В большинстве случаев, когда вы добавляете орнамент в текстовые строки в приложении, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] вы используете текст с точки зрения коллекции дискретных символов, или глифов.</span><span class="sxs-lookup"><span data-stu-id="c9a50-103">In most cases, when you're adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="c9a50-104">Например, можно создать линейную градиентную <xref:System.Windows.Controls.Control.Foreground%2A> кисть <xref:System.Windows.Controls.TextBox> и применить ее к свойству объекта.</span><span class="sxs-lookup"><span data-stu-id="c9a50-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="c9a50-105">При отображении или редактировании текстового окна линейная кисти градиента автоматически наносится на текущий набор символов в текстовой строке.</span><span class="sxs-lookup"><span data-stu-id="c9a50-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![Текст, отображенный при помощи кисти линейного градиента](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="c9a50-107">Тем не менее, вы <xref:System.Windows.Media.Geometry> также можете преобразовать текст в объекты, что позволяет создавать другие типы визуально богатого текста.</span><span class="sxs-lookup"><span data-stu-id="c9a50-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="c9a50-108">Например, можно создать <xref:System.Windows.Media.Geometry> объект на основе контура строки текста.</span><span class="sxs-lookup"><span data-stu-id="c9a50-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="c9a50-110">Когда текст преобразуется <xref:System.Windows.Media.Geometry> в объект, он больше не представляет собой набор символов, вы не можете изменить символы в строке текста.</span><span class="sxs-lookup"><span data-stu-id="c9a50-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="c9a50-111">Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки.</span><span class="sxs-lookup"><span data-stu-id="c9a50-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="c9a50-112">Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста.</span><span class="sxs-lookup"><span data-stu-id="c9a50-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="c9a50-113">Следующие примеры иллюстрируют несколько способов создания визуальных эффектов путем изменения штриха и заполнения преобразованного текста.</span><span class="sxs-lookup"><span data-stu-id="c9a50-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![Текст с различными цветами для заполнения штриха](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="c9a50-116">Также можно изменить прямоугольник ящика или выделить преобразованный текст.</span><span class="sxs-lookup"><span data-stu-id="c9a50-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="c9a50-117">Следующий пример иллюстрирует способ создания визуальных эффектов путем изменения штриха и выделения преобразованного текста.</span><span class="sxs-lookup"><span data-stu-id="c9a50-117">The following example illustrates a way to create visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![Текст с изображением кисти, нанесенной на штрих и выделение](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="c9a50-119">Пример</span><span class="sxs-lookup"><span data-stu-id="c9a50-119">Example</span></span>  
 <span data-ttu-id="c9a50-120">Ключом к преобразованию <xref:System.Windows.Media.Geometry> текста в <xref:System.Windows.Media.FormattedText> объект является использование объекта.</span><span class="sxs-lookup"><span data-stu-id="c9a50-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="c9a50-121">После создания этого объекта можно использовать <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> методы для преобразования <xref:System.Windows.Media.Geometry> текста в объекты.</span><span class="sxs-lookup"><span data-stu-id="c9a50-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="c9a50-122">Первый метод возвращает геометрию отформатированный текст; второй метод возвращает геометрию ограниченного окна отформатированный текст.</span><span class="sxs-lookup"><span data-stu-id="c9a50-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="c9a50-123">Следующий пример кода показывает, <xref:System.Windows.Media.FormattedText> как создать объект и получить геометрию отформатированного текста и его ограничивающего окна.</span><span class="sxs-lookup"><span data-stu-id="c9a50-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="c9a50-124">Для отображения <xref:System.Windows.Media.Geometry> извлеченных объектов необходимо <xref:System.Windows.Media.DrawingContext> получить доступ к объекту, отображаемому преобразованный текст.</span><span class="sxs-lookup"><span data-stu-id="c9a50-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that's displaying the converted text.</span></span> <span data-ttu-id="c9a50-125">В этих примерах кода этот доступ достигается путем создания пользовательского объекта управления, полученного из класса, поддерживающего пользовательскую визуализацию.</span><span class="sxs-lookup"><span data-stu-id="c9a50-125">In these code examples, this access is achieved by creating a custom control object that's derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="c9a50-126">Для <xref:System.Windows.Media.Geometry> отображения объектов в пользовательском элементе управления предоставьте переопределение для метода. <xref:System.Windows.UIElement.OnRender%2A></span><span class="sxs-lookup"><span data-stu-id="c9a50-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="c9a50-127">Ваш перекрывшийся <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> метод должен <xref:System.Windows.Media.Geometry> использовать метод для рисования объектов.</span><span class="sxs-lookup"><span data-stu-id="c9a50-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="c9a50-128">Для источника пользовательского объекта пользовательского управления можно найти [OutlineTextControl.cs для C-и](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) [OutlineTextControl.vb для Visual Basic.](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)</span><span class="sxs-lookup"><span data-stu-id="c9a50-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c9a50-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c9a50-129">See also</span></span>

- [<span data-ttu-id="c9a50-130">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="c9a50-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
