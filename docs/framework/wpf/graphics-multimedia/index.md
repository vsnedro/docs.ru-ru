---
title: Графика и мультимедиа
description: Обнаружение мультимедийных функций Windows Presentation Foundation (WPF). Добавление графики, эффектов перехода, звука и видео в приложения.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: ba52e78564484f7714ab0035a5e1861766b72bbf
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853684"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="a8335-104">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a8335-104">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="a8335-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает поддержку мультимедиа, векторную графику, анимацию и композицию содержимого, делая создание интересных пользовательских интерфейсов и содержимого простым делом для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="a8335-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="a8335-106">С помощью Visual Studio можно создавать векторную графику или сложную анимацию и интегрировать мультимедиа в приложения.</span><span class="sxs-lookup"><span data-stu-id="a8335-106">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="a8335-107">В этом разделе представлены возможности графики, анимации и мультимедиа в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые позволяют добавлять в приложения рисунки, эффекты перехода, звук и видео.</span><span class="sxs-lookup"><span data-stu-id="a8335-107">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="a8335-108">Использование типов WPF в службе Windows настоятельно не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a8335-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="a8335-109">При попытке использовать типы WPF в службе Windows, службы могут не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="a8335-109">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="a8335-110">Новые графические и мультимедийные возможности в WPF 4</span><span class="sxs-lookup"><span data-stu-id="a8335-110">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="a8335-111">В части графики и анимации были сделаны некоторые изменения.</span><span class="sxs-lookup"><span data-stu-id="a8335-111">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="a8335-112">Округление макета</span><span class="sxs-lookup"><span data-stu-id="a8335-112">Layout Rounding</span></span>

  <span data-ttu-id="a8335-113">Когда граница объекта попадает в середину пикселя устройства, не зависящая от разрешения система графики может создавать артефакты отрисовки, например нечеткие или полупрозрачные границы.</span><span class="sxs-lookup"><span data-stu-id="a8335-113">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="a8335-114">Предыдущие версии WPF для обработки таких случаев включали функцию привязки пикселей.</span><span class="sxs-lookup"><span data-stu-id="a8335-114">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="a8335-115">В Silverlight 2 появилось округление макета, являющееся другим способом перемещения элементов так, чтобы границы попадали между пикселями.</span><span class="sxs-lookup"><span data-stu-id="a8335-115">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="a8335-116">Теперь WPF поддерживает округление макета с <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> присоединенным свойством для <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="a8335-116">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="a8335-117">Кэшированная композиция</span><span class="sxs-lookup"><span data-stu-id="a8335-117">Cached Composition</span></span>

  <span data-ttu-id="a8335-118">С помощью новых <xref:System.Windows.Media.BitmapCache> классов и <xref:System.Windows.Media.BitmapCacheBrush> можно кэшировать сложную часть визуального дерева в виде точечного рисунка и значительно увеличить время отрисовки.</span><span class="sxs-lookup"><span data-stu-id="a8335-118">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="a8335-119">Растровое изображение продолжает реагировать на действия пользователя, например на щелчки мыши, и им можно рисовать на других элементах, как любой кистью.</span><span class="sxs-lookup"><span data-stu-id="a8335-119">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="a8335-120">Поддержка построителя текстур 3</span><span class="sxs-lookup"><span data-stu-id="a8335-120">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="a8335-121">Платформа WPF 4 построена на основе <xref:System.Windows.Media.Effects.ShaderEffect> поддержки, представленной в WPF 3,5 с пакетом обновления 1 (SP1), позволяя приложениям писать эффекты с помощью пиксельного шейдера (PS) версии 3,0.</span><span class="sxs-lookup"><span data-stu-id="a8335-121">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="a8335-122">Шейдерная модель PS 3.0 сложнее, чем PS 2.0, что позволяет реализовать гораздо больше эффектов на поддерживаемом оборудовании.</span><span class="sxs-lookup"><span data-stu-id="a8335-122">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="a8335-123">Функции плавности</span><span class="sxs-lookup"><span data-stu-id="a8335-123">Easing Functions</span></span>

  <span data-ttu-id="a8335-124">Можно усовершенствовать анимацию с помощью функций плавности, которые обеспечивают дополнительный контроль над поведением анимации.</span><span class="sxs-lookup"><span data-stu-id="a8335-124">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="a8335-125">Например, можно применить <xref:System.Windows.Media.Animation.ElasticEase> к анимации, чтобы сделать анимацию высокоэффектной.</span><span class="sxs-lookup"><span data-stu-id="a8335-125">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="a8335-126">Дополнительные сведения см. в разделе Типы замедления в <xref:System.Windows.Media.Animation> пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="a8335-126">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="a8335-127">Графика и отрисовка</span><span class="sxs-lookup"><span data-stu-id="a8335-127">Graphics and Rendering</span></span>

<span data-ttu-id="a8335-128">WPF включает поддержку высококачественной двухмерной графики.</span><span class="sxs-lookup"><span data-stu-id="a8335-128">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="a8335-129">Возможности включают кисти, геометрические объекты, изображения, фигуры и преобразования.</span><span class="sxs-lookup"><span data-stu-id="a8335-129">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="a8335-130">Дополнительные сведения см. в разделе [Графика](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-130">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="a8335-131">Отрисовка графических элементов основана на <xref:System.Windows.Media.Visual> классе.</span><span class="sxs-lookup"><span data-stu-id="a8335-131">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="a8335-132">Структура визуальных объектов на экране описывается визуальным деревом.</span><span class="sxs-lookup"><span data-stu-id="a8335-132">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="a8335-133">Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-133">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="a8335-134">Двумерные фигуры</span><span class="sxs-lookup"><span data-stu-id="a8335-134">2D Shapes</span></span>

<span data-ttu-id="a8335-135">WPF предоставляет библиотеку часто используемых векторно-рисуемых плоских фигур, таких как прямоугольники и эллипсы, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a8335-135">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Диаграмма, на которой показаны многоточие и прямоугольники.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="a8335-137">Эти встроенные фигуры WPF не просто являются фигурами: они являются программируемыми элементами, которые реализуют многие из наиболее распространенных элементов управления, в том числе ввод с клавиатуры и с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="a8335-137">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="a8335-138">В следующем примере показано, как обработано <xref:System.Windows.UIElement.MouseUp> событие, вызванное щелчком <xref:System.Windows.Shapes.Ellipse> элемента.</span><span class="sxs-lookup"><span data-stu-id="a8335-138">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

<span data-ttu-id="a8335-139">На следующем рисунке показан результат выполнения предыдущей разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода.</span><span class="sxs-lookup"><span data-stu-id="a8335-139">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Окно сообщения "вы щелкнули многоточие!"](./media/index/messagebox-text-output.png)

<span data-ttu-id="a8335-141">Более подробную информацию см. в разделе [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-141">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="a8335-142">Вводный пример см. в разделе [Пример элементов-фигур](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="a8335-142">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="a8335-143">Двумерные геометрические объекты</span><span class="sxs-lookup"><span data-stu-id="a8335-143">2D Geometries</span></span>

<span data-ttu-id="a8335-144">Если плоские фигуры, предоставляемые WPF, недостаточно, можно использовать поддержку WPF для геометрических схем и путей, чтобы создать собственные.</span><span class="sxs-lookup"><span data-stu-id="a8335-144">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="a8335-145">На следующем рисунке показано, как можно использовать геометрические объекты для создания фигур, в качестве кисти рисования и для обрезки других элементов WPF.</span><span class="sxs-lookup"><span data-stu-id="a8335-145">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![Снимок экрана, показывающий, как можно использовать геометрические фигуры для создания фигур.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="a8335-147">Дополнительные сведения см. в разделе [Общие сведения о геометрии](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-147">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="a8335-148">Вводный пример в разделе [Примеры геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="a8335-148">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="a8335-149">Двумерные эффекты</span><span class="sxs-lookup"><span data-stu-id="a8335-149">2D Effects</span></span>

<span data-ttu-id="a8335-150">WPF предоставляет библиотеку двумерных классов, которую можно использовать для создания различных эффектов.</span><span class="sxs-lookup"><span data-stu-id="a8335-150">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="a8335-151">Возможность двухмерной отрисовки WPF позволяет закрашивать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы, имеющие градиенты, растровые изображения, рисунки и видео, а также управлять ими с помощью вращения, масштабирования и наклона.</span><span class="sxs-lookup"><span data-stu-id="a8335-151">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="a8335-152">На следующем рисунке приводится пример многих эффектов, которые можно достичь с помощью кистей WPF.</span><span class="sxs-lookup"><span data-stu-id="a8335-152">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![Иллюстрация, демонстрирующая различные кисти и элементы Paint WPF.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="a8335-154">Дополнительные сведения см. в разделе [Общие сведения о кистях WPF](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-154">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="a8335-155">Вводный пример см. в разделе [Пример использования кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="a8335-155">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="a8335-156">Трехмерная отрисовка</span><span class="sxs-lookup"><span data-stu-id="a8335-156">3D Rendering</span></span>

<span data-ttu-id="a8335-157">WPF предоставляет набор возможностей трехмерной отрисовки, которые интегрируются с поддержкой двухмерной графики в WPF, чтобы создавать более привлекательные макеты, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и визуализации данных.</span><span class="sxs-lookup"><span data-stu-id="a8335-157">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="a8335-158">На одном конце спектра WPF позволяет визуализировать 2D-изображения на поверхности трехмерных фигур, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a8335-158">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![Снимок экрана примера, показывающего трехмерные фигуры с разными текстурами.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="a8335-160">Дополнительные сведения см. в разделе [Обзор трехмерной графики](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-160">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="a8335-161">Вводный пример см. в разделе [Пример трехмерных твердых](https://go.microsoft.com/fwlink/?LinkID=159964)массивов.</span><span class="sxs-lookup"><span data-stu-id="a8335-161">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="a8335-162">Анимация</span><span class="sxs-lookup"><span data-stu-id="a8335-162">Animation</span></span>

<span data-ttu-id="a8335-163">Использование анимации позволяет применять к элементам управления и графическим элементам такие эффекты, как увеличение, дрожание, вращение и исчезание, создавать интересные эффекты смены страниц и другие эффекты.</span><span class="sxs-lookup"><span data-stu-id="a8335-163">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="a8335-164">Поскольку WPF позволяет анимировать большинство свойств, а не только анимацию большинства объектов WPF, можно также использовать WPF для анимации создаваемых пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="a8335-164">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![Снимок экрана: анимированный куб.](./media/index/animate-custom-objects.png)

<span data-ttu-id="a8335-166">Дополнительные сведения см. в разделе [Общие сведения об анимации](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-166">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="a8335-167">Вводный пример в разделе [Коллекция примеров анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="a8335-167">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="a8335-168">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a8335-168">Media</span></span>

<span data-ttu-id="a8335-169">Изображения, видео и аудио являются мультимедийными способами передачи информации и взаимодействия с пользователями.</span><span class="sxs-lookup"><span data-stu-id="a8335-169">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="a8335-170">Изображения</span><span class="sxs-lookup"><span data-stu-id="a8335-170">Images</span></span>

<span data-ttu-id="a8335-171">Изображения, которые включают значки, фоновые рисунки и даже части анимаций, являются одним из основных элементов большинства приложений.</span><span class="sxs-lookup"><span data-stu-id="a8335-171">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="a8335-172">Поскольку часто приходится использовать образы, WPF предоставляет возможность работать с ними различными способами.</span><span class="sxs-lookup"><span data-stu-id="a8335-172">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="a8335-173">На следующем рисунке показан один из таких способов.</span><span class="sxs-lookup"><span data-stu-id="a8335-173">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="a8335-174">![Снимок экрана: пример стилизации](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="a8335-174">![Styling sample screenshot](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="a8335-175">Дополнительные сведения см. в разделе [Общие сведения о работе с образами](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-175">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="a8335-176">Видео и звук</span><span class="sxs-lookup"><span data-stu-id="a8335-176">Video and Audio</span></span>

<span data-ttu-id="a8335-177">Основной функцией графических возможностей WPF является предоставление собственной поддержки для работы с мультимедиа, включая видео и аудио.</span><span class="sxs-lookup"><span data-stu-id="a8335-177">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="a8335-178">Следующий пример демонстрирует вставку в приложение медиапроигрывателя.</span><span class="sxs-lookup"><span data-stu-id="a8335-178">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="a8335-179"><xref:System.Windows.Controls.MediaElement>может воспроизводить видео и аудио, а также достаточно расширяемое, чтобы обеспечить простое создание пользовательских интерфейсов пользователя.</span><span class="sxs-lookup"><span data-stu-id="a8335-179"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="a8335-180">Дополнительные сведения см. в разделе [Общие сведения о мультимедиа](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8335-180">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8335-181">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a8335-181">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="a8335-182">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="a8335-182">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="a8335-183">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="a8335-183">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="a8335-184">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="a8335-184">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="a8335-185">Рисование с помощью объектов Image, Drawing и Visual</span><span class="sxs-lookup"><span data-stu-id="a8335-185">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="a8335-186">Разделы руководства по анимации и таймерам</span><span class="sxs-lookup"><span data-stu-id="a8335-186">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="a8335-187">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="a8335-187">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="a8335-188">Общие сведения о мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a8335-188">Multimedia Overview</span></span>](multimedia-overview.md)
