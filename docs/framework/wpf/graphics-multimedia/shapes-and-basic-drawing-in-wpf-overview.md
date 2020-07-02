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
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="e0762-103">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="e0762-103">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="e0762-104">В этом разделе приводятся общие сведения о том, как рисовать с помощью <xref:System.Windows.Shapes.Shape> объектов.</span><span class="sxs-lookup"><span data-stu-id="e0762-104">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="e0762-105"><xref:System.Windows.Shapes.Shape>— Это тип <xref:System.Windows.UIElement> , который позволяет нарисовать форму на экране.</span><span class="sxs-lookup"><span data-stu-id="e0762-105">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="e0762-106">Поскольку они являются элементами пользовательского интерфейса, <xref:System.Windows.Shapes.Shape> объекты могут использоваться внутри <xref:System.Windows.Controls.Panel> элементов и большинства элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e0762-106">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="e0762-107">предоставляет несколько уровней доступа к службам для работы с графикой и службам рендеринга.</span><span class="sxs-lookup"><span data-stu-id="e0762-107">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="e0762-108">На верхнем уровне <xref:System.Windows.Shapes.Shape> объекты просты в использовании и предоставляют множество полезных функций, таких как макет и участие в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] системе событий.</span><span class="sxs-lookup"><span data-stu-id="e0762-108">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>
## <a name="shape-objects"></a><span data-ttu-id="e0762-109">Объекты фигур</span><span class="sxs-lookup"><span data-stu-id="e0762-109">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="e0762-110">предоставляет ряд готовых к использованию <xref:System.Windows.Shapes.Shape> объектов.</span><span class="sxs-lookup"><span data-stu-id="e0762-110">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="e0762-111">Все объекты Shape наследуются от <xref:System.Windows.Shapes.Shape> класса.</span><span class="sxs-lookup"><span data-stu-id="e0762-111">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="e0762-112">Доступные объекты фигур: <xref:System.Windows.Shapes.Ellipse> , <xref:System.Windows.Shapes.Line> , <xref:System.Windows.Shapes.Path> , <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> и <xref:System.Windows.Shapes.Rectangle> .</span><span class="sxs-lookup"><span data-stu-id="e0762-112">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="e0762-113"><xref:System.Windows.Shapes.Shape>объекты имеют следующие общие свойства.</span><span class="sxs-lookup"><span data-stu-id="e0762-113"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="e0762-114"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Описывает рисование контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-114"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="e0762-115"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Описывает толщину контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-115"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="e0762-116"><xref:System.Windows.Shapes.Shape.Fill%2A>: Описывает, как рисуется внутренняя часть фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-116"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="e0762-117">Свойства данных, определяющие координаты и вершины, измеряются в аппаратно-независимых пикселях.</span><span class="sxs-lookup"><span data-stu-id="e0762-117">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="e0762-118">Так как они являются производными от <xref:System.Windows.UIElement> , объекты Shape можно использовать внутри панелей и большинства элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e0762-118">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="e0762-119"><xref:System.Windows.Controls.Canvas>Панель является особенно хорошим выбором для создания сложных рисунков, так как она поддерживает абсолютное позиционирование дочерних объектов.</span><span class="sxs-lookup"><span data-stu-id="e0762-119">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="e0762-120"><xref:System.Windows.Shapes.Line>Класс позволяет нарисовать линию между двумя точками.</span><span class="sxs-lookup"><span data-stu-id="e0762-120">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="e0762-121">В следующем примере показано несколько способов указания координат линии и свойств штриха.</span><span class="sxs-lookup"><span data-stu-id="e0762-121">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="e0762-122">На следующем рисунке показан отображаемый объект <xref:System.Windows.Shapes.Line> .</span><span class="sxs-lookup"><span data-stu-id="e0762-122">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="e0762-123">![Иллюстрация линии](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="e0762-123">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="e0762-124">Несмотря на то <xref:System.Windows.Shapes.Line> , что класс предоставляет <xref:System.Windows.Shapes.Shape.Fill%2A> свойство, его установка не имеет результата, поскольку не <xref:System.Windows.Shapes.Line> имеет области.</span><span class="sxs-lookup"><span data-stu-id="e0762-124">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="e0762-125">Другой распространенной фигурой является <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="e0762-125">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="e0762-126">Создайте <xref:System.Windows.Shapes.Ellipse> , определив <xref:System.Windows.FrameworkElement.Width%2A> свойства фигуры и <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="e0762-126">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="e0762-127">Чтобы нарисовать круг, укажите, <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.FrameworkElement.Width%2A> значения и <xref:System.Windows.FrameworkElement.Height%2A> равны.</span><span class="sxs-lookup"><span data-stu-id="e0762-127">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="e0762-128">На следующем рисунке показан пример отображаемого объекта <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="e0762-128">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="e0762-129">![Иллюстрация эллипса](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="e0762-129">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a><span data-ttu-id="e0762-130">Использование путей и геометрических фигур</span><span class="sxs-lookup"><span data-stu-id="e0762-130">Using Paths and Geometries</span></span>  
 <span data-ttu-id="e0762-131"><xref:System.Windows.Shapes.Path>Класс позволяет рисовать кривые и сложные фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-131">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="e0762-132">Эти кривые и фигуры описываются с помощью <xref:System.Windows.Media.Geometry> объектов.</span><span class="sxs-lookup"><span data-stu-id="e0762-132">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="e0762-133">Чтобы использовать <xref:System.Windows.Shapes.Path> , создайте <xref:System.Windows.Media.Geometry> и используйте его для задания <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Path.Data%2A> свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="e0762-133">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="e0762-134">Существует множество <xref:System.Windows.Media.Geometry> объектов для выбора.</span><span class="sxs-lookup"><span data-stu-id="e0762-134">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="e0762-135"><xref:System.Windows.Media.LineGeometry>Классы, <xref:System.Windows.Media.RectangleGeometry> и <xref:System.Windows.Media.EllipseGeometry> описывают относительно простые фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-135">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="e0762-136">Чтобы создать более сложные фигуры или создать кривые, используйте <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="e0762-136">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="e0762-137">Классы PathGeometry и PathSegment</span><span class="sxs-lookup"><span data-stu-id="e0762-137">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="e0762-138"><xref:System.Windows.Media.PathGeometry>объекты состоят из одного или нескольких <xref:System.Windows.Media.PathFigure> объектов; каждый из них <xref:System.Windows.Media.PathFigure> представляет отдельную фигуру или форму.</span><span class="sxs-lookup"><span data-stu-id="e0762-138"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="e0762-139">Каждый из них <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых представляет собой подключенную часть рисунка или фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-139">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="e0762-140">Типы сегментов включают следующие: <xref:System.Windows.Media.LineSegment> , <xref:System.Windows.Media.BezierSegment> и <xref:System.Windows.Media.ArcSegment> .</span><span class="sxs-lookup"><span data-stu-id="e0762-140">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="e0762-141">В следующем примере <xref:System.Windows.Shapes.Path> используется для отрисовки кривой Безье квадратичных кривых.</span><span class="sxs-lookup"><span data-stu-id="e0762-141">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="e0762-142">На следующем рисунке показана преобразованная для просмотра фигура.</span><span class="sxs-lookup"><span data-stu-id="e0762-142">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="e0762-143">![Иллюстрация пути](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="e0762-143">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="e0762-144">Дополнительные сведения о <xref:System.Windows.Media.PathGeometry> и других <xref:System.Windows.Media.Geometry> классах см. в разделе [Общие сведения о геометрии](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0762-144">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="e0762-145">Сокращенный синтаксис XAML</span><span class="sxs-lookup"><span data-stu-id="e0762-145">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="e0762-146">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно также использовать специальный сокращенный синтаксис для описания <xref:System.Windows.Shapes.Path> .</span><span class="sxs-lookup"><span data-stu-id="e0762-146">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="e0762-147">В следующем примере сокращенный синтаксис используется для рисования сложной фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-147">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="e0762-148">На следующем рисунке показан отображаемый объект <xref:System.Windows.Shapes.Path> .</span><span class="sxs-lookup"><span data-stu-id="e0762-148">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="e0762-149">![Иллюстрация пути](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="e0762-149">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="e0762-150"><xref:System.Windows.Shapes.Path.Data%2A>Строка атрибута начинается с команды "MoveTo", обозначенной буквой M, которая устанавливает начальную точку для пути в системе координат <xref:System.Windows.Controls.Canvas> .</span><span class="sxs-lookup"><span data-stu-id="e0762-150">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e0762-151"><xref:System.Windows.Shapes.Path>в параметрах данных учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="e0762-151"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="e0762-152">Прописная M указывает на абсолютное расположение новой текущей точки.</span><span class="sxs-lookup"><span data-stu-id="e0762-152">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="e0762-153">Строчная буква m указывала бы относительные координаты.</span><span class="sxs-lookup"><span data-stu-id="e0762-153">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="e0762-154">Первый сегмент представляет собой кубическую кривую Безье, которая начинается в точке (100, 200) и заканчивается в точке (400, 175). Эта кривая нарисована с помощью двух контрольных точек (100, 25) и (400, 350).</span><span class="sxs-lookup"><span data-stu-id="e0762-154">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="e0762-155">Этот сегмент обозначается командой C в <xref:System.Windows.Shapes.Path.Data%2A> строке атрибута.</span><span class="sxs-lookup"><span data-stu-id="e0762-155">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="e0762-156">Опять же, заглавная буква C указывает абсолютный путь; строчная буква c указывает относительный путь.</span><span class="sxs-lookup"><span data-stu-id="e0762-156">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="e0762-157">Второй сегмент начинается с команды lineto H, которая рисует горизонтальную линию от предыдущей точки пути (400, 175) до новой точки (280, 175).</span><span class="sxs-lookup"><span data-stu-id="e0762-157">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="e0762-158">Так как это команда по горизонтали "lineto", указанное значение является координатой *x*.</span><span class="sxs-lookup"><span data-stu-id="e0762-158">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="e0762-159">Полный синтаксис пути см <xref:System.Windows.Shapes.Path.Data%2A> . в справочнике и [создании фигуры с помощью PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="e0762-159">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a><span data-ttu-id="e0762-160">Заполнение фигур</span><span class="sxs-lookup"><span data-stu-id="e0762-160">Painting Shapes</span></span>  
 <span data-ttu-id="e0762-161"><xref:System.Windows.Media.Brush>объекты используются для заполнения фигур <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.Fill%2A> .</span><span class="sxs-lookup"><span data-stu-id="e0762-161"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="e0762-162">В следующем примере задаются штрих и Fill элемента <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="e0762-162">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="e0762-163">Обратите внимание, что значения свойств кисти могут задаваться только в формате ключевого слова или шестнадцатеричного значения цвета.</span><span class="sxs-lookup"><span data-stu-id="e0762-163">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="e0762-164">Дополнительные сведения о доступных цветовых ключевых словах см <xref:System.Windows.Media.Colors> . в разделе Свойства класса в <xref:System.Windows.Media> пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="e0762-164">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
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
  
 <span data-ttu-id="e0762-165">На следующем рисунке показан отображаемый объект <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="e0762-165">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="e0762-166">![Эллипс](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="e0762-166">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="e0762-167">Кроме того, можно использовать синтаксис элемента свойства для явного создания <xref:System.Windows.Media.SolidColorBrush> объекта, чтобы закрасить фигуру сплошным цветом.</span><span class="sxs-lookup"><span data-stu-id="e0762-167">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
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
  
 <span data-ttu-id="e0762-168">На рисунке ниже показана фигура, преобразованная для просмотра.</span><span class="sxs-lookup"><span data-stu-id="e0762-168">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="e0762-169">![Иллюстрация SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="e0762-169">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="e0762-170">Для заполнения фигуры также можно использовать штриховку, градиенты, изображения, шаблоны и многое другое.</span><span class="sxs-lookup"><span data-stu-id="e0762-170">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="e0762-171">Дополнительные сведения см. в разделе [Общие сведения о рисовании с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0762-171">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a><span data-ttu-id="e0762-172">Растягиваемые фигуры</span><span class="sxs-lookup"><span data-stu-id="e0762-172">Stretchable Shapes</span></span>  
 <span data-ttu-id="e0762-173"><xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Polygon> Все классы,,, <xref:System.Windows.Shapes.Polyline> и <xref:System.Windows.Shapes.Rectangle> имеют <xref:System.Windows.Shapes.Shape.Stretch%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e0762-173">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="e0762-174">Это свойство определяет, как <xref:System.Windows.Shapes.Shape> содержимое объекта (рисуемая фигура) растягивается для заполнения <xref:System.Windows.Shapes.Shape> пространства макета объекта.</span><span class="sxs-lookup"><span data-stu-id="e0762-174">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="e0762-175"><xref:System.Windows.Shapes.Shape>Пространство макета объекта — это объем пространства, <xref:System.Windows.Shapes.Shape> выделенного системой макета, из-за явной <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> настройки, или из-за <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> параметров и.</span><span class="sxs-lookup"><span data-stu-id="e0762-175">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="e0762-176">Дополнительные сведения о макете в Windows Presentation Foundation см. в разделе Общие сведения о [макете](../advanced/layout.md) .</span><span class="sxs-lookup"><span data-stu-id="e0762-176">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="e0762-177">Свойство Stretch принимает одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="e0762-177">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="e0762-178"><xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> Содержимое объекта не растягивается.</span><span class="sxs-lookup"><span data-stu-id="e0762-178"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="e0762-179"><xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается для заполнения пространства макета.</span><span class="sxs-lookup"><span data-stu-id="e0762-179"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="e0762-180">Пропорции не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="e0762-180">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="e0762-181"><xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается настолько, насколько возможно, для заполнения пространства макета с сохранением исходного пропорций.</span><span class="sxs-lookup"><span data-stu-id="e0762-181"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="e0762-182"><xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается для полного заполнения пространства макета с сохранением исходного пропорций.</span><span class="sxs-lookup"><span data-stu-id="e0762-182"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="e0762-183">Обратите внимание, что при <xref:System.Windows.Shapes.Shape> растяжении содержимого объекта <xref:System.Windows.Shapes.Shape> контур объекта закрашивается после растяжения.</span><span class="sxs-lookup"><span data-stu-id="e0762-183">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="e0762-184">В следующем примере <xref:System.Windows.Shapes.Polygon> используется для рисования очень маленького треугольника с (0, 0) до (1, 1).</span><span class="sxs-lookup"><span data-stu-id="e0762-184">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="e0762-185"><xref:System.Windows.Shapes.Polygon>Объект и имеет <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> значение 100, а свойство Stretch имеет значение Fill.</span><span class="sxs-lookup"><span data-stu-id="e0762-185">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="e0762-186">В результате <xref:System.Windows.Shapes.Polygon> содержимое объекта (треугольник) растягивается для заполнения большего пространства.</span><span class="sxs-lookup"><span data-stu-id="e0762-186">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
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
## <a name="transforming-shapes"></a><span data-ttu-id="e0762-187">Преобразование фигур</span><span class="sxs-lookup"><span data-stu-id="e0762-187">Transforming Shapes</span></span>  
 <span data-ttu-id="e0762-188"><xref:System.Windows.Media.Transform>Класс предоставляет средства для преобразования фигур в двумерной плоскости.</span><span class="sxs-lookup"><span data-stu-id="e0762-188">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="e0762-189">К различным типам преобразований относятся вращение ( <xref:System.Windows.Media.RotateTransform> ), Scale ( <xref:System.Windows.Media.ScaleTransform> ), асимметрия ( <xref:System.Windows.Media.SkewTransform> ) и Translation ( <xref:System.Windows.Media.TranslateTransform> ).</span><span class="sxs-lookup"><span data-stu-id="e0762-189">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="e0762-190">Распространенным преобразованием фигуры является поворот.</span><span class="sxs-lookup"><span data-stu-id="e0762-190">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="e0762-191">Чтобы повернуть фигуру, создайте <xref:System.Windows.Media.RotateTransform> и укажите ее <xref:System.Windows.Media.RotateTransform.Angle%2A> .</span><span class="sxs-lookup"><span data-stu-id="e0762-191">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="e0762-192">Значение, <xref:System.Windows.Media.RotateTransform.Angle%2A> равное 45, поворачивает элемент на 45 градусов по часовой стрелке; угол 90 поворачивает элемент на 90 градусов по часовой стрелке и т. д.</span><span class="sxs-lookup"><span data-stu-id="e0762-192">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="e0762-193">Задайте <xref:System.Windows.Media.RotateTransform.CenterX%2A> Свойства и, <xref:System.Windows.Media.RotateTransform.CenterY%2A> Если требуется управлять точкой, вокруг которой поворачивается элемент.</span><span class="sxs-lookup"><span data-stu-id="e0762-193">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="e0762-194">Эти значения свойств выражаются в системе координат преобразуемого элемента.</span><span class="sxs-lookup"><span data-stu-id="e0762-194">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="e0762-195"><xref:System.Windows.Media.RotateTransform.CenterX%2A>и <xref:System.Windows.Media.RotateTransform.CenterY%2A> имеют нулевые значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0762-195"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="e0762-196">Наконец, примените <xref:System.Windows.Media.RotateTransform> к элементу.</span><span class="sxs-lookup"><span data-stu-id="e0762-196">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="e0762-197">Если вы не хотите, чтобы преобразование влияло на макет, установите <xref:System.Windows.UIElement.RenderTransform%2A> свойство фигуры.</span><span class="sxs-lookup"><span data-stu-id="e0762-197">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="e0762-198">В следующем примере <xref:System.Windows.Media.RotateTransform> используется для поворота фигуры 45 градусов относительно левого верхнего угла фигуры (0, 0).</span><span class="sxs-lookup"><span data-stu-id="e0762-198">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="e0762-199">В следующем примере другая фигура поворачивается на 45 градусов, но на этот раз — вокруг точки (25, 50).</span><span class="sxs-lookup"><span data-stu-id="e0762-199">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="e0762-200">На следующем рисунке показаны результаты двух преобразований.</span><span class="sxs-lookup"><span data-stu-id="e0762-200">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="e0762-201">![Повороты на 45 градусов с разными центральными точками](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="e0762-201">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="e0762-202">В предыдущих примерах к каждому объекту фигуры применяется одно преобразование.</span><span class="sxs-lookup"><span data-stu-id="e0762-202">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="e0762-203">Чтобы применить несколько преобразований к фигуре (или любому другому элементу пользовательского интерфейса), используйте <xref:System.Windows.Media.TransformGroup> .</span><span class="sxs-lookup"><span data-stu-id="e0762-203">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0762-204">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e0762-204">See also</span></span>

- [<span data-ttu-id="e0762-205">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="e0762-205">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="e0762-206">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="e0762-206">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="e0762-207">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="e0762-207">Geometry Overview</span></span>](geometry-overview.md)
- <span data-ttu-id="e0762-208">[Пошаговое руководство: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md) (Пошаговое руководство. Создание классического приложения WPF)</span><span class="sxs-lookup"><span data-stu-id="e0762-208">[Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md)</span></span>
- [<span data-ttu-id="e0762-209">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="e0762-209">Animation Overview</span></span>](animation-overview.md)
