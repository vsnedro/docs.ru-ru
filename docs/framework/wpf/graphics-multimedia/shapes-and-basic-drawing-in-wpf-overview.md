---
title: Общие сведения о фигурах и базовом рисовании
description: Улучшите пользовательский интерфейс с помощью готовых к использованию фигур и нескольких уровней служб отрисовки в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 41d8f2b87232740c8945bd6a6099aa86dbe77bc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853691"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Обзор фигур и базовых средств рисования в приложении WPF
В этом разделе приводятся общие сведения о том, как рисовать с помощью <xref:System.Windows.Shapes.Shape> объектов. <xref:System.Windows.Shapes.Shape>— Это тип <xref:System.Windows.UIElement> , который позволяет нарисовать форму на экране. Поскольку они являются элементами пользовательского интерфейса, <xref:System.Windows.Shapes.Shape> объекты могут использоваться внутри <xref:System.Windows.Controls.Panel> элементов и большинства элементов управления.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет несколько уровней доступа к службам для работы с графикой и службам рендеринга. На верхнем уровне <xref:System.Windows.Shapes.Shape> объекты просты в использовании и предоставляют множество полезных функций, таких как макет и участие в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] системе событий.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Объекты фигур  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет ряд готовых к использованию <xref:System.Windows.Shapes.Shape> объектов.  Все объекты Shape наследуются от <xref:System.Windows.Shapes.Shape> класса. Доступные объекты фигур: <xref:System.Windows.Shapes.Ellipse> , <xref:System.Windows.Shapes.Line> , <xref:System.Windows.Shapes.Path> , <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> и <xref:System.Windows.Shapes.Rectangle> . <xref:System.Windows.Shapes.Shape>объекты имеют следующие общие свойства.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: Описывает рисование контура фигуры.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Описывает толщину контура фигуры.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: Описывает, как рисуется внутренняя часть фигуры.  
  
- Свойства данных, определяющие координаты и вершины, измеряются в аппаратно-независимых пикселях.  
  
 Так как они являются производными от <xref:System.Windows.UIElement> , объекты Shape можно использовать внутри панелей и большинства элементов управления. <xref:System.Windows.Controls.Canvas>Панель является особенно хорошим выбором для создания сложных рисунков, так как она поддерживает абсолютное позиционирование дочерних объектов.  
  
 <xref:System.Windows.Shapes.Line>Класс позволяет нарисовать линию между двумя точками. В следующем примере показано несколько способов указания координат линии и свойств штриха.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 На следующем рисунке показан отображаемый объект <xref:System.Windows.Shapes.Line> .  
  
 ![Иллюстрация линии](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Несмотря на то <xref:System.Windows.Shapes.Line> , что класс предоставляет <xref:System.Windows.Shapes.Shape.Fill%2A> свойство, его установка не имеет результата, поскольку не <xref:System.Windows.Shapes.Line> имеет области.  
  
 Другой распространенной фигурой является <xref:System.Windows.Shapes.Ellipse> .  Создайте <xref:System.Windows.Shapes.Ellipse> , определив <xref:System.Windows.FrameworkElement.Width%2A> свойства фигуры и <xref:System.Windows.FrameworkElement.Height%2A> . Чтобы нарисовать круг, укажите, <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.FrameworkElement.Width%2A> значения и <xref:System.Windows.FrameworkElement.Height%2A> равны.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 На следующем рисунке показан пример отображаемого объекта <xref:System.Windows.Shapes.Ellipse> .  
  
 ![Иллюстрация эллипса](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>Использование путей и геометрических фигур  
 <xref:System.Windows.Shapes.Path>Класс позволяет рисовать кривые и сложные фигуры. Эти кривые и фигуры описываются с помощью <xref:System.Windows.Media.Geometry> объектов. Чтобы использовать <xref:System.Windows.Shapes.Path> , создайте <xref:System.Windows.Media.Geometry> и используйте его для задания <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Path.Data%2A> свойства объекта.  
  
 Существует множество <xref:System.Windows.Media.Geometry> объектов для выбора. <xref:System.Windows.Media.LineGeometry>Классы, <xref:System.Windows.Media.RectangleGeometry> и <xref:System.Windows.Media.EllipseGeometry> описывают относительно простые фигуры. Чтобы создать более сложные фигуры или создать кривые, используйте <xref:System.Windows.Media.PathGeometry> .  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>Классы PathGeometry и PathSegment  
 <xref:System.Windows.Media.PathGeometry>объекты состоят из одного или нескольких <xref:System.Windows.Media.PathFigure> объектов; каждый из них <xref:System.Windows.Media.PathFigure> представляет отдельную фигуру или форму. Каждый из них <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых представляет собой подключенную часть рисунка или фигуры. Типы сегментов включают следующие: <xref:System.Windows.Media.LineSegment> , <xref:System.Windows.Media.BezierSegment> и <xref:System.Windows.Media.ArcSegment> .  
  
 В следующем примере <xref:System.Windows.Shapes.Path> используется для отрисовки кривой Безье квадратичных кривых.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 На следующем рисунке показана преобразованная для просмотра фигура.  
  
 ![Иллюстрация пути](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Дополнительные сведения о <xref:System.Windows.Media.PathGeometry> и других <xref:System.Windows.Media.Geometry> классах см. в разделе [Общие сведения о геометрии](geometry-overview.md).  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>Сокращенный синтаксис XAML  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно также использовать специальный сокращенный синтаксис для описания <xref:System.Windows.Shapes.Path> . В следующем примере сокращенный синтаксис используется для рисования сложной фигуры.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 На следующем рисунке показан отображаемый объект <xref:System.Windows.Shapes.Path> .  
  
 ![Иллюстрация пути](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 <xref:System.Windows.Shapes.Path.Data%2A>Строка атрибута начинается с команды "MoveTo", обозначенной буквой M, которая устанавливает начальную точку для пути в системе координат <xref:System.Windows.Controls.Canvas> . <xref:System.Windows.Shapes.Path>в параметрах данных учитывается регистр. Прописная M указывает на абсолютное расположение новой текущей точки. Строчная буква m указывала бы относительные координаты. Первый сегмент представляет собой кубическую кривую Безье, которая начинается в точке (100, 200) и заканчивается в точке (400, 175). Эта кривая нарисована с помощью двух контрольных точек (100, 25) и (400, 350). Этот сегмент обозначается командой C в <xref:System.Windows.Shapes.Path.Data%2A> строке атрибута. Опять же, заглавная буква C указывает абсолютный путь; строчная буква c указывает относительный путь.  
  
 Второй сегмент начинается с команды lineto H, которая рисует горизонтальную линию от предыдущей точки пути (400, 175) до новой точки (280, 175). Так как это команда по горизонтали "lineto", указанное значение является координатой *x*.  
  
 Полный синтаксис пути см <xref:System.Windows.Shapes.Path.Data%2A> . в справочнике и [создании фигуры с помощью PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>Заполнение фигур  
 <xref:System.Windows.Media.Brush>объекты используются для заполнения фигур <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.Fill%2A> . В следующем примере задаются штрих и Fill элемента <xref:System.Windows.Shapes.Ellipse> . Обратите внимание, что значения свойств кисти могут задаваться только в формате ключевого слова или шестнадцатеричного значения цвета. Дополнительные сведения о доступных цветовых ключевых словах см <xref:System.Windows.Media.Colors> . в разделе Свойства класса в <xref:System.Windows.Media> пространстве имен.  
  
```xaml
<Canvas Background="LightGray">
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 На следующем рисунке показан отображаемый объект <xref:System.Windows.Shapes.Ellipse> .  
  
 ![Эллипс](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 Кроме того, можно использовать синтаксис элемента свойства для явного создания <xref:System.Windows.Media.SolidColorBrush> объекта, чтобы закрасить фигуру сплошным цветом.  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 На рисунке ниже показана фигура, преобразованная для просмотра.  
  
 ![Иллюстрация SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 Для заполнения фигуры также можно использовать штриховку, градиенты, изображения, шаблоны и многое другое. Дополнительные сведения см. в разделе [Общие сведения о рисовании с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>Растягиваемые фигуры  
 <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Polygon> Все классы,,, <xref:System.Windows.Shapes.Polyline> и <xref:System.Windows.Shapes.Rectangle> имеют <xref:System.Windows.Shapes.Shape.Stretch%2A> свойство. Это свойство определяет, как <xref:System.Windows.Shapes.Shape> содержимое объекта (рисуемая фигура) растягивается для заполнения <xref:System.Windows.Shapes.Shape> пространства макета объекта. <xref:System.Windows.Shapes.Shape>Пространство макета объекта — это объем пространства, <xref:System.Windows.Shapes.Shape> выделенного системой макета, из-за явной <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> настройки, или из-за <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> параметров и. Дополнительные сведения о макете в Windows Presentation Foundation см. в разделе Общие сведения о [макете](../advanced/layout.md) .  
  
 Свойство Stretch принимает одно из следующих значений.  
  
- <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> Содержимое объекта не растягивается.  
  
- <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается для заполнения пространства макета.  Пропорции не сохраняются.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается настолько, насколько возможно, для заполнения пространства макета с сохранением исходного пропорций.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается для полного заполнения пространства макета с сохранением исходного пропорций.  
  
 Обратите внимание, что при <xref:System.Windows.Shapes.Shape> растяжении содержимого объекта <xref:System.Windows.Shapes.Shape> контур объекта закрашивается после растяжения.  
  
 В следующем примере <xref:System.Windows.Shapes.Polygon> используется для рисования очень маленького треугольника с (0, 0) до (1, 1). <xref:System.Windows.Shapes.Polygon>Объект и имеет <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> значение 100, а свойство Stretch имеет значение Fill. В результате <xref:System.Windows.Shapes.Polygon> содержимое объекта (треугольник) растягивается для заполнения большего пространства.  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>
## <a name="transforming-shapes"></a>Преобразование фигур  
 <xref:System.Windows.Media.Transform>Класс предоставляет средства для преобразования фигур в двумерной плоскости.  К различным типам преобразований относятся вращение ( <xref:System.Windows.Media.RotateTransform> ), Scale ( <xref:System.Windows.Media.ScaleTransform> ), асимметрия ( <xref:System.Windows.Media.SkewTransform> ) и Translation ( <xref:System.Windows.Media.TranslateTransform> ).  
  
 Распространенным преобразованием фигуры является поворот.  Чтобы повернуть фигуру, создайте <xref:System.Windows.Media.RotateTransform> и укажите ее <xref:System.Windows.Media.RotateTransform.Angle%2A> . Значение, <xref:System.Windows.Media.RotateTransform.Angle%2A> равное 45, поворачивает элемент на 45 градусов по часовой стрелке; угол 90 поворачивает элемент на 90 градусов по часовой стрелке и т. д. Задайте <xref:System.Windows.Media.RotateTransform.CenterX%2A> Свойства и, <xref:System.Windows.Media.RotateTransform.CenterY%2A> Если требуется управлять точкой, вокруг которой поворачивается элемент. Эти значения свойств выражаются в системе координат преобразуемого элемента. <xref:System.Windows.Media.RotateTransform.CenterX%2A>и <xref:System.Windows.Media.RotateTransform.CenterY%2A> имеют нулевые значения по умолчанию. Наконец, примените <xref:System.Windows.Media.RotateTransform> к элементу. Если вы не хотите, чтобы преобразование влияло на макет, установите <xref:System.Windows.UIElement.RenderTransform%2A> свойство фигуры.  
  
 В следующем примере <xref:System.Windows.Media.RotateTransform> используется для поворота фигуры 45 градусов относительно левого верхнего угла фигуры (0, 0).  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 В следующем примере другая фигура поворачивается на 45 градусов, но на этот раз — вокруг точки (25, 50).  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 На следующем рисунке показаны результаты двух преобразований.  
  
 ![Повороты на 45 градусов с разными центральными точками](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 В предыдущих примерах к каждому объекту фигуры применяется одно преобразование. Чтобы применить несколько преобразований к фигуре (или любому другому элементу пользовательского интерфейса), используйте <xref:System.Windows.Media.TransformGroup> .  
  
## <a name="see-also"></a>Дополнительно

- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Общие сведения о классе Geometry](geometry-overview.md)
- [Пошаговое руководство: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md) (Пошаговое руководство. Создание классического приложения WPF)
- [Общие сведения об эффектах анимации](animation-overview.md)
