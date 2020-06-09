---
title: Графика и мультимедиа
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
ms.openlocfilehash: ecc54ad9453343f6306b0133fa180abd0db46f82
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596426"
---
# <a name="graphics-and-multimedia"></a>Графика и мультимедиа

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает поддержку мультимедиа, векторную графику, анимацию и композицию содержимого, делая создание интересных пользовательских интерфейсов и содержимого простым делом для разработчиков. С помощью Visual Studio можно создавать векторную графику или сложную анимацию и интегрировать мультимедиа в приложения.

В этом разделе представлены возможности графики, анимации и мультимедиа в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые позволяют добавлять в приложения рисунки, эффекты перехода, звук и видео.

> [!NOTE]
> Использование типов WPF в службе Windows настоятельно не рекомендуется. При попытке использовать типы WPF в службе Windows, службы могут не работать должным образом.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Новые графические и мультимедийные возможности в WPF 4

В части графики и анимации были сделаны некоторые изменения.

- Округление макета

  Когда граница объекта попадает в середину пикселя устройства, не зависящая от разрешения система графики может создавать артефакты отрисовки, например нечеткие или полупрозрачные границы. Предыдущие версии WPF для обработки таких случаев включали функцию привязки пикселей. В Silverlight 2 появилось округление макета, являющееся другим способом перемещения элементов так, чтобы границы попадали между пикселями. Теперь WPF поддерживает округление макета с <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> присоединенным свойством для <xref:System.Windows.FrameworkElement> .

- Кэшированная композиция

  С помощью новых <xref:System.Windows.Media.BitmapCache> классов и <xref:System.Windows.Media.BitmapCacheBrush> можно кэшировать сложную часть визуального дерева в виде точечного рисунка и значительно увеличить время отрисовки. Растровое изображение продолжает реагировать на действия пользователя, например на щелчки мыши, и им можно рисовать на других элементах, как любой кистью.

- Поддержка построителя текстур 3

  Платформа WPF 4 построена на основе <xref:System.Windows.Media.Effects.ShaderEffect> поддержки, представленной в WPF 3,5 с пакетом обновления 1 (SP1), позволяя приложениям писать эффекты с помощью пиксельного шейдера (PS) версии 3,0. Шейдерная модель PS 3.0 сложнее, чем PS 2.0, что позволяет реализовать гораздо больше эффектов на поддерживаемом оборудовании.

- Функции плавности

  Можно усовершенствовать анимацию с помощью функций плавности, которые обеспечивают дополнительный контроль над поведением анимации. Например, можно применить <xref:System.Windows.Media.Animation.ElasticEase> к анимации, чтобы сделать анимацию высокоэффектной. Дополнительные сведения см. в разделе Типы замедления в <xref:System.Windows.Media.Animation> пространстве имен.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Графика и отрисовка

WPF включает поддержку высококачественной двухмерной графики. Возможности включают кисти, геометрические объекты, изображения, фигуры и преобразования. Дополнительные сведения см. в разделе [Графика](graphics.md). Отрисовка графических элементов основана на <xref:System.Windows.Media.Visual> классе. Структура визуальных объектов на экране описывается визуальным деревом. Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md).

### <a name="2d-shapes"></a>Двумерные фигуры

WPF предоставляет библиотеку часто используемых векторно-рисуемых плоских фигур, таких как прямоугольники и эллипсы, показанные на следующем рисунке.

![Диаграмма, на которой показаны многоточие и прямоугольники.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Эти встроенные фигуры WPF не просто являются фигурами: они являются программируемыми элементами, которые реализуют многие из наиболее распространенных элементов управления, в том числе ввод с клавиатуры и с помощью мыши. В следующем примере показано, как обработано <xref:System.Windows.UIElement.MouseUp> событие, вызванное щелчком <xref:System.Windows.Shapes.Ellipse> элемента.

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

На следующем рисунке показан результат выполнения предыдущей разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода.

![Окно сообщения "вы щелкнули многоточие!"](./media/index/messagebox-text-output.png)

Более подробную информацию см. в разделе [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md). Вводный пример см. в разделе [Пример элементов-фигур](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).

### <a name="2d-geometries"></a>Двумерные геометрические объекты

Если плоские фигуры, предоставляемые WPF, недостаточно, можно использовать поддержку WPF для геометрических схем и путей, чтобы создать собственные. На следующем рисунке показано, как можно использовать геометрические объекты для создания фигур, в качестве кисти рисования и для обрезки других элементов WPF.

![Снимок экрана, показывающий, как можно использовать геометрические фигуры для создания фигур.](./media/index/use-geometries-create-shapes.png)

Дополнительные сведения см. в разделе [Общие сведения о геометрии](geometry-overview.md). Вводный пример в разделе [Примеры геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).

### <a name="2d-effects"></a>Двумерные эффекты

WPF предоставляет библиотеку двумерных классов, которую можно использовать для создания различных эффектов. Возможность двухмерной отрисовки WPF позволяет закрашивать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы, имеющие градиенты, растровые изображения, рисунки и видео, а также управлять ими с помощью вращения, масштабирования и наклона. На следующем рисунке приводится пример многих эффектов, которые можно достичь с помощью кистей WPF.

![Иллюстрация, демонстрирующая различные кисти и элементы Paint WPF.](./media/index/brushes-paint-elements.png)

Дополнительные сведения см. в разделе [Общие сведения о кистях WPF](wpf-brushes-overview.md). Вводный пример см. в разделе [Пример использования кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).

<a name="rendering"></a>

## <a name="3d-rendering"></a>Трехмерная отрисовка

WPF предоставляет набор возможностей трехмерной отрисовки, которые интегрируются с поддержкой двухмерной графики в WPF, чтобы создавать более привлекательные макеты, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и визуализации данных. На одном конце спектра WPF позволяет визуализировать 2D-изображения на поверхности трехмерных фигур, как показано на следующем рисунке.

![Снимок экрана примера, показывающего трехмерные фигуры с разными текстурами.](./media/index/visual-three-dimensional-shape.png)

Дополнительные сведения см. в разделе [Обзор трехмерной графики](3-d-graphics-overview.md). Вводный пример см. в разделе [Пример трехмерных твердых](https://go.microsoft.com/fwlink/?LinkID=159964)массивов.

<a name="animation"></a>

## <a name="animation"></a>Анимация

Использование анимации позволяет применять к элементам управления и графическим элементам такие эффекты, как увеличение, дрожание, вращение и исчезание, создавать интересные эффекты смены страниц и другие эффекты. Поскольку WPF позволяет анимировать большинство свойств, а не только анимацию большинства объектов WPF, можно также использовать WPF для анимации создаваемых пользовательских объектов.

![Снимок экрана: анимированный куб.](./media/index/animate-custom-objects.png)

Дополнительные сведения см. в разделе [Общие сведения об анимации](animation-overview.md). Вводный пример в разделе [Коллекция примеров анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).

<a name="media"></a>

## <a name="media"></a>Мультимедиа

Изображения, видео и аудио являются мультимедийными способами передачи информации и взаимодействия с пользователями.

### <a name="images"></a>Изображения

Изображения, которые включают значки, фоновые рисунки и даже части анимаций, являются одним из основных элементов большинства приложений. Поскольку часто приходится использовать образы, WPF предоставляет возможность работать с ними различными способами. На следующем рисунке показан один из таких способов.

![Снимок экрана: пример стилизации](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Дополнительные сведения см. в разделе [Общие сведения о работе с образами](imaging-overview.md).

### <a name="video-and-audio"></a>Видео и звук

Основной функцией графических возможностей WPF является предоставление собственной поддержки для работы с мультимедиа, включая видео и аудио. Следующий пример демонстрирует вставку в приложение медиапроигрывателя.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>может воспроизводить видео и аудио, а также достаточно расширяемое, чтобы обеспечить простое создание пользовательских интерфейсов пользователя.

Дополнительные сведения см. в разделе [Общие сведения о мультимедиа](multimedia-overview.md).

## <a name="see-also"></a>Дополнительно

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Рисование с помощью объектов Image, Drawing и Visual](painting-with-images-drawings-and-visuals.md)
- [Разделы руководства по анимации и таймерам](animation-and-timing-how-to-topics.md)
- [Обзор трехмерной графики](3-d-graphics-overview.md)
- [Общие сведения о мультимедиа](multimedia-overview.md)
