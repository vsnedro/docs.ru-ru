---
title: Синтаксис разметки пути
description: Узнайте о мощном и сложном мини-языке, который можно использовать для указания компактных геометрических путей в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 6d2778522b622f0b0dcb59673e793a6d772a4b4f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853649"
---
# <a name="path-markup-syntax"></a>Синтаксис разметки пути
Пути обсуждаются в [фигурах и базовом изображении в обзоре WPF](shapes-and-basic-drawing-in-wpf-overview.md) и в [общих сведениях об геометрии](geometry-overview.md). Однако в этом разделе подробно описывается мощный и сложный компактный язык, который можно использовать для указания геометрических путей с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять этот раздел, необходимо ознакомиться с основными возможностями <xref:System.Windows.Media.Geometry> объектов. Дополнительные сведения см. в разделе [Общие сведения о геометрии](geometry-overview.md).  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>Мини-языки StreamGeometry и PathFigureCollection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет два класса, которые предоставляют мини-языки для описания геометрических путей: <xref:System.Windows.Media.StreamGeometry> и <xref:System.Windows.Media.PathFigureCollection> .  
  
- Используйте <xref:System.Windows.Media.StreamGeometry> мини-язык при задании свойства типа <xref:System.Windows.Media.Geometry> , например <xref:System.Windows.UIElement.Clip%2A> свойства <xref:System.Windows.UIElement> или <xref:System.Windows.Shapes.Path.Data%2A> свойства <xref:System.Windows.Shapes.Path> элемента. В следующем примере используется синтаксис атрибутов для создания <xref:System.Windows.Media.StreamGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <xref:System.Windows.Media.PathFigureCollection>При задании свойства объекта используется мини-язык <xref:System.Windows.Media.PathGeometry.Figures%2A> <xref:System.Windows.Media.PathGeometry> . В следующем примере используется синтаксис атрибута для создания <xref:System.Windows.Media.PathFigureCollection> для <xref:System.Windows.Media.PathGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Как видно из предыдущих примеров мини-языки очень похожи. Всегда можно использовать <xref:System.Windows.Media.PathGeometry> в любой ситуации, где можно использовать, <xref:System.Windows.Media.StreamGeometry> и какой из них следует использовать? Используйте, если <xref:System.Windows.Media.StreamGeometry> не нужно изменять путь после его создания; используйте, <xref:System.Windows.Media.PathGeometry> Если необходимо изменить путь.  
  
 Дополнительные сведения о различиях между <xref:System.Windows.Media.PathGeometry> объектами и <xref:System.Windows.Media.StreamGeometry> см. в разделе [Общие сведения о геометрии](geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Примечание о пробелах  
 В следующих разделах для краткости в примерах синтаксиса показан один пробел, но допускается использовать по нескольку пробелов везде, где указан один пробел.  
  
 В действительности два числа не должны разделяться запятыми или пробелами, но это можно сделать только в том случае, если результирующая строка является однозначной. Например, `2..3` фактически является двумя числами: 2. и 3. Аналогичным образом `2-3` — "2" и "-3". Пробелы до и после команд ставить необязательно.  
  
### <a name="syntax"></a>Синтаксис  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Синтаксис использования атрибута для элемента <xref:System.Windows.Media.StreamGeometry> состоит из необязательного <xref:System.Windows.Media.FillRule> значения и одного или нескольких описаний цифр.  
  
|Использование атрибута XAML на StreamGeometry|  
|-----------------------------------------|  
|`<`*object* *свойство* объекта `="` [ `fillRule` ] `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Синтаксис использования атрибута для элемента <xref:System.Windows.Media.PathFigureCollection> состоит из одного или нескольких описаний цифр.  
  
|Использование атрибута XAML на PathFigureCollection|  
|-----------------------------------------------|  
|`<`*object* *свойство* объекта `="` `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
|Термин|Описание|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Указывает, <xref:System.Windows.Media.StreamGeometry> использует ли объект <xref:System.Windows.Media.FillRule.EvenOdd> или <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A> .<br /><br /> -   `F0`Указывает <xref:System.Windows.Media.FillRule.EvenOdd> правило заполнения.<br />-   `F1`Указывает <xref:System.Windows.Media.FillRule.Nonzero> правило заполнения.<br /><br /> Если эта команда не задана, вложенный путь использует поведение по умолчанию, то есть <xref:System.Windows.Media.FillRule.EvenOdd> . Если эта команда используется, ее необходимо размещать вначале.|  
|*figureDescription*|Фигура, состоящая из команды перемещения, команд рисования и необязательной команды закрытия.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Команда перемещения, которая указывает начальную точку фигуры. См. раздел [команда Move](#themovecommand) .|  
|*drawCommands*|Одна или несколько команд рисования, описывающих содержимое фигуры. См. раздел [команды Draw](#drawcommands) .|  
|*closeCommand*|Необязательная команда, которая закрывает фигуру. См. раздел [команда Close](#closecommand) .|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Команда перемещения  
 Задает начальную точку новой фигуры.  
  
|Синтаксис|  
|------------|  
|`M`*StartPoint*<br /><br /> -или-<br /><br /> `m`*StartPoint*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Начальная точка новой фигуры.|  
  
 Прописная буква указывает на то `M` , что `startPoint` является абсолютным значением; строчная буква `m` указывает, что `startPoint` является смещением к предыдущей точке, или (0, 0), если ни одно из них не существует. Если после команды перемещения указано несколько точек, будет нарисована линия к этим точкам, как в случае указания команды рисования линии.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Команды рисования  
 Команда рисования может состоять из нескольких команд формы. Имеются следующие команды формы: линия, горизонтальная линия, вертикальная линия, кривая Безье третьего порядка, кривая Безье второго порядка, гладкая кривая Безье третьего порядка, гладкая кривая Безье второго порядка и эллиптическая дуга.  
  
 Все команды можно вводить как прописными, так и строчными буквами. Прописными буквами определяются абсолютные значения, а строчными —относительные. Контрольная точка для этого сегмента указывается относительно конечной точки в предыдущем примере. При последовательном вводе нескольких команд одного типа можно опустить дублирующую запись команды. Например, `L 100,200 300,400` эквивалентно `L 100,200 L 300,400` . В следующей таблице описаны команды **Move** и **Draw** .  
  
### <a name="line-command"></a>Команда рисования линии  
 Создает прямую линию между текущей и заданной конечной точками. `l 20 30`и `L 20,30` являются примерами допустимых команд **line** .  
  
|Синтаксис|  
|------------|  
|`L`*Конечная точка*<br /><br /> -или-<br /><br /> `l`*Конечная точка*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*Конечной*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Конечная точка строки.|  

Прописная буква указывает на то `L` , что `endPoint` является абсолютным значением; строчная буква `l` указывает, что `endPoint` является смещением к предыдущей точке, или (0, 0), если ни одно из них не существует.

### <a name="horizontal-line-command"></a>Команда рисования горизонтальной линии  
 Создает горизонтальную линию между текущей точкой и заданной координатой X. `H 90` — пример допустимой команды рисования горизонтальной линии.

|Синтаксис|  
|------------|  
|`H`  *x*<br /><br /> -или-<br /><br /> `h`  *x*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата X конечной точки линии.|  
  
Прописная буква указывает на то `H` , что `x` является абсолютным значением; строчная буква `h` указывает, что `x` является смещением к предыдущей точке, или (0, 0), если ни одно из них не существует.
  
### <a name="vertical-line-command"></a>Команда рисования вертикальной линии  
 Создает вертикальную линию между текущей точкой и заданной координатой Y. `v 90` — пример допустимой команды рисования вертикальной линии.

|Синтаксис|  
|------------|  
|`V`  *&*<br /><br /> -или-<br /><br /> `v`  *&*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*&*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата Y конечной точки линии.|  

Прописная буква указывает на то `V` , что `y` является абсолютным значением; строчная буква `v` указывает, что `y` является смещением к предыдущей точке, или (0, 0), если ни одно из них не существует.  

### <a name="cubic-bezier-curve-command"></a>Команда рисования кривой Безье третьего порядка  
 Создает кривую Безье третьего порядка между текущей точкой и заданной конечной точкой с помощью двух указанных контрольных точек ( `controlPoint` 1 и `controlPoint` 2). `C 100,200 200,400 300,200` — пример допустимой команды рисования кривой линии.  
  
|Синтаксис|  
|------------|  
|`C``controlPoint`1 `controlPoint` 2`endPoint`<br /><br /> -или-<br /><br /> `c``controlPoint`1 `controlPoint` 2`endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Первая контрольная точка кривой, которая определяет начальную касательную к кривой.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Вторая контрольная точка кривой, которая определяет конечную касательную к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="quadratic-bezier-curve-command"></a>Команда рисования кривой Безье второго порядка  
 Создает кривую Безье второго квадратичного интервала между текущей точкой и заданной конечной точкой с помощью заданной контрольной точки ( `controlPoint` ). `q 100,200 300,200` — пример допустимой команды рисования кривой Безье второго порядка.  
  
|Синтаксис|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> -или-<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Контрольная точка кривой, которая определяет начальную и конечную касательные к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Команда рисования гладкой кривой Безье третьего порядка  
 Создает кривую Безье третьего порядка между текущей и заданной конечной точками. Предполагается, что первая контрольная точка является отражением второй контрольной точки предыдущей команды относительно текущей точки. Если нет предыдущей команды или если предыдущая команда не является командой рисования кривой Безье третьего порядка или командой рисования гладкой кривой Безье третьего порядка, считается, что первая контрольная точка совпадает с текущей точкой. Вторая контрольная точка, контрольная точка для конца кривой, задается `controlPoint` 2. Например, `S 100,200 200,300` — допустимая команда гладкой кривой Безье третьего порядка.  
  
|Синтаксис|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> -или-<br /><br /> `s``controlPoint`2`endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Контрольная точка кривой, которая определяет конечную касательную к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Команда рисования гладкой кривой Безье второго порядка  
 Создает кривую Безье второго порядка между текущей и заданной конечной точками. Предполагается, что контрольная точка является отражением контрольной точки предыдущей команды относительно текущей точки. Если нет предыдущей команды или если предыдущая команда не является командой рисования кривой Безье второго порядка или командой рисования гладкой кривой Безье второго порядка, считается, что контрольная точка совпадает с текущей точкой.  
  
|Синтаксис|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> -или-<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Контрольная точка кривой, которая определяет начальную касательную к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="elliptical-arc-command"></a>Команда рисования эллиптической дуги  
 Создает эллиптическую дугу между текущей и заданной конечной точками.  
  
|Синтаксис|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> -или-<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> Радиусы арки X и Y.|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Поворот эллипса в градусах.|  
|`isLargeArcFlag`|Значение 1, если угол дуги должен быть 180 градусов или больше, в противном случае — значение 0.|  
|`sweepDirectionFlag`|Значение 1, если дуга рисуется в направлении положительного угла, в противном случае — значение 0.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка, в которую рисуется дуга.|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a>Команда закрытия  
 Заканчивает текущую фигуру и создает линию, соединяющую текущую точку с начальной точкой фигуры. Эта команда создает соединительную линию (угол) между последним и первым сегментами фигуры.  
  
|Синтаксис|  
|------------|  
|`Z`<br /><br /> -или-<br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a>Синтаксис точки  
 Описывает координаты x и y точки, где (0, 0) — верхний левый угол.
  
|Синтаксис|  
|------------|  
|`x` `,` `y`<br /><br /> -или-<br /><br /> `x` `y`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата X точки.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата Y точки.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>Специальные значения  
 Вместо стандартных числовых значений можно использовать следующие специальные значения. В этих значениях учитывается регистр.  
  
 Бесконечность  
 Представляет <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> .  
  
 -бесконечность  
 Представляет <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> .  
  
 Не число  
 Представляет <xref:System.Double.NaN?displayProperty=nameWithType> .  
  
 Можно также использовать экспоненциальное представление чисел. Например, `+1.e17` — допустимое значение.  
  
## <a name="see-also"></a>Дополнительно

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Общие сведения о классе Geometry](geometry-overview.md)
- [Практические руководства](geometries-how-to-topics.md)
