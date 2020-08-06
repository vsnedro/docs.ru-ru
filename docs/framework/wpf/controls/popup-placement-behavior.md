---
title: Поведение при размещении контекстного меню
description: Сведения о том, как указать расположение всплывающего окна Windows Presentation Foundation относительно элемента управления, указателя мыши или экрана с помощью свойств.
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 8184805518bc56693ead4c7d1f0e9a1bff9bff8f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167743"
---
# <a name="popup-placement-behavior"></a>Поведение при размещении контекстного меню
Элемент управления <xref:System.Windows.Controls.Primitives.Popup> отображает содержимое в отдельном окне, расположенном поверх приложения. Вы можете указать расположение <xref:System.Windows.Controls.Primitives.Popup> относительно элемента управления, указателя мыши или экрана с помощью свойств <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  Вместе эти свойства позволяют гибко указывать положение <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Классы <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ContextMenu> также определяют эти пять свойств и ведут себя аналогичным образом.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Размещение всплывающего окна  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> может быть задано относительно <xref:System.Windows.UIElement> или всего экрана.  В следующем примере показано создание четырех элементов управления <xref:System.Windows.Controls.Primitives.Popup>, располагаемых относительно к элемента <xref:System.Windows.UIElement>, в данном случае это изображение. Все элементы управления <xref:System.Windows.Controls.Primitives.Popup> имеют свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> со значением `image1`, но у каждого <xref:System.Windows.Controls.Primitives.Popup> свойство размещения имеет иное значение.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 На следующем рисунке показаны элементы управления <xref:System.Windows.Controls.Primitives.Popup> и изображение:  
  
 ![Изображение с четырьмя элементами управления всплывающих окон](./media/popup-placement-behavior/popup-placement-intro.png "Изображение с четырьмя всплывающими окнами")
  
 В этом простом примере показано, как задать свойства <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, но с помощью свойств <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> можно еще лучше контролировать расположение <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Определения терминов: Анатомия всплывающего окна  
 Следующие термины полезны для понимания того, как свойства <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> связаны друг с другом и с <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Целевой объект  
  
- Целевая область  
  
- Исходная точка  
  
- Точка выравнивания всплывающего окна  
  
 Эти термины удобно использовать для ссылки на различные аспекты <xref:System.Windows.Controls.Primitives.Popup> и связанные с ним элементы управления.  
  
### <a name="target-object"></a>Целевой объект  
 *Целевой объект* является элементом, с которым связано <xref:System.Windows.Controls.Primitives.Popup>. Если свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> задано, оно указывает целевой объект.  Если параметр <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не задан, а <xref:System.Windows.Controls.Primitives.Popup> имеет родительский объект, то такой родительский объект является целевым объектом.  Если родительского объекта и значения <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> нет, то целевой объект отсутствует, а <xref:System.Windows.Controls.Primitives.Popup> располагается относительно экрана.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup>, являющийся дочерним объектом для <xref:System.Windows.Controls.Canvas>.  В этом примере не задается свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> в <xref:System.Windows.Controls.Primitives.Popup>. Значение по умолчанию для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> — <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, поэтому <xref:System.Windows.Controls.Primitives.Popup> отображается под <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> располагается относительно <xref:System.Windows.Controls.Canvas>.  
  
 ![Элемент управления всплывающим окном без PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Всплывающее окно без PlacementTarget.")  

 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup>, являющийся дочерним объектом для <xref:System.Windows.Controls.Canvas>, но на этот раз для <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> задано значение `ellipse1`, поэтому всплывающее окно отображается под <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 На следующем рисунке показано, что <xref:System.Windows.Controls.Primitives.Popup> располагается относительно <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Размещение всплывающего окна относительно эллипса](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Всплывающее окно с PlacementTarget")
  
> [!NOTE]
> Для <xref:System.Windows.Controls.ToolTip> значением по умолчанию для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> является <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Для <xref:System.Windows.Controls.ContextMenu> значением по умолчанию для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> является <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Эти значения описаны дальше, в разделе "Совместная работа свойств".  
  
### <a name="target-area"></a>Целевая область  
 *Целевая область* — это область на экране, относительно которой располагается <xref:System.Windows.Controls.Primitives.Popup>. В предыдущих примерах <xref:System.Windows.Controls.Primitives.Popup> выравнивается по границам целевого объекта, но в некоторых случаях <xref:System.Windows.Controls.Primitives.Popup> выравнивается по другим границам, даже если у <xref:System.Windows.Controls.Primitives.Popup> есть целевой объект.  Если указано значение свойства <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, целевая область отличается от границ целевого объекта.  
  
 В следующем примере создаются два объекта <xref:System.Windows.Controls.Canvas>, каждый из которых содержит <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Controls.Primitives.Popup>.  В обоих случаях целевым объектом для <xref:System.Windows.Controls.Primitives.Popup> является <xref:System.Windows.Controls.Canvas>. Для <xref:System.Windows.Controls.Primitives.Popup> в первом <xref:System.Windows.Controls.Canvas> задано свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, а для свойств <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A> и <xref:System.Windows.Rect.Height%2A> заданы значения 50, 50, 50 и 100 соответственно. Для <xref:System.Windows.Controls.Primitives.Popup> во втором <xref:System.Windows.Controls.Canvas> свойство <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не задано.  В результате первый <xref:System.Windows.Controls.Primitives.Popup> располагается под <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, а второй <xref:System.Windows.Controls.Primitives.Popup> — под <xref:System.Windows.Controls.Canvas>. Каждый <xref:System.Windows.Controls.Canvas> также содержит <xref:System.Windows.Shapes.Rectangle> с теми же границами, что и у <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> для первого <xref:System.Windows.Controls.Primitives.Popup>.  Обратите внимание, что <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не создает видимый элемент в приложении; в примере <xref:System.Windows.Shapes.Rectangle> создается для представления <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Всплывающее меню с PlacementRectangle и без него](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Всплывающее окно с PlacementRectangle и без него.")  

### <a name="target-origin-and-popup-alignment-point"></a>Исходная точка и точка выравнивания всплывающего окна  
 *Исходная точка* и *точка выравнивания всплывающего окна* являются опорными точками на целевой области и всплывающем окне соответственно, которые используются для позиционирования. Вы можете использовать свойства <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> для смещения всплывающего окна от целевой области.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> располагаются относительно исходной точки и точки выравнивания всплывающего окна. Значение свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> определяет местоположение исходной точки и точки выравнивания всплывающего окна.  
  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.Popup>, а для свойств <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> задается значение 20.  Свойству <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> присвоено значение <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (по умолчанию), поэтому исходной точкой является левый нижний угол целевой области, а точкой выравнивания всплывающего окна — левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 На следующем рисунке показан результат примера, приведенного выше.  
  
 ![Размещение всплывающего окна с точкой выравнивания в исходной точке](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Всплывающее окно с HorizontalOffset и VerticalOffset.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Совместная работа свойств  
 Значения <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> и <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> нужно рассматривать вместе для определения правильной целевой области, исходной точки и точки выравнивания всплывающего окна.  Например, если значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> равно <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, целевой объект отсутствует, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> игнорируется, а целевой областью являются границы указателя мыши. С другой стороны, если значение <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> равно <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект определяет целевой объект, а <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> определяет целевую область.  
  
 В следующей таблице описаны целевой объект, целевая область, исходная точка и точка выравнивания всплывающего окна, а также указано, используются ли <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> и <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> для каждого значения перечисления <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Целевой объект|Целевая область|Исходная точка|Точка выравнивания всплывающего окна|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не учитывается.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно экрана.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не учитывается.|Экран или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно экрана.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Левый нижний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Центр целевой области.|Центр <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Определяется <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Левый верхний угол целевой области.|Правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не учитывается.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не учитывается.|Левый нижний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Не применяется <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> не учитывается.|Границы указателя мыши. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> не учитывается.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Левый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Правый верхний угол целевой области.|Левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> или родительский объект.|Целевой объект или <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, если он задан.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> задается относительно целевого объекта.|Левый верхний угол целевой области.|Левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 На следующих рисунках показаны <xref:System.Windows.Controls.Primitives.Popup>, целевая область, исходная точка и точка выравнивания всплывающего окна для каждого значения <xref:System.Windows.Controls.Primitives.PlacementMode>. На каждом рисунке целевая область закрашена желтым, а <xref:System.Windows.Controls.Primitives.Popup> — голубым цветом.  
  
 ![Всплывающее окно с абсолютным размещением или размещением с помощью AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "Абсолютное размещение или размещение с помощью AbsolutePoint.")
  
 ![Всплывающее окно с размещением внизу](./media/popup-placement-behavior/popup-placement-bottom.png "Расположение снизу.")
  
 ![Всплывающее окно с размещением по центру](./media/popup-placement-behavior/popup-placement-center.png "Размещение в центре.")
  
 ![Всплывающее окно с размещением слева](./media/popup-placement-behavior/popup-placement-left.png "Размещение слева.")
  
 ![Всплывающее окно с размещением относительно мыши](./media/popup-placement-behavior/popup-placement-mouse.png "Размещение относительно мыши.")  
  
 ![Всплывающее окно с размещением с помощью MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "Размещение относительно MousePoint.")  
  
 ![Всплывающее окно с относительным размещением или размещением с помощью RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "Относительное размещение или размещение с помощью RelativePoint.")
  
 ![Всплывающее окно с размещением справа](./media/popup-placement-behavior/popup-placement-right.png "Размещение справа.")
  
 ![Всплывающее окно с размещением сверху](./media/popup-placement-behavior/popup-placement-top.png "Размещение сверху.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Когда всплывающее окно достигает края экрана  
 По соображениям безопасности <xref:System.Windows.Controls.Primitives.Popup> не может быть скрыто за краем экрана. При достижении <xref:System.Windows.Controls.Primitives.Popup> края экрана происходит одно из следующих трех событий:  
  
- Всплывающее окно располагается вдоль края экрана, который мог бы скрыть <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Всплывающее окно использует другую точку выравнивания.  
  
- Всплывающее окно использует другую исходную точку и точку выравнивания.  
  
 Эти параметры будут описаны далее в данном разделе.  
  
 Поведение <xref:System.Windows.Controls.Primitives.Popup> при достижении края экрана зависит от значения свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> и от того, с каким краем экрана сталкивается всплывающее окно. Следующая таблица содержит сводные сведения о поведении, имеющем место, когда <xref:System.Windows.Controls.Primitives.Popup> достигает границы экрана, для каждого значения <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Верхний край|Нижний край|Левый край|Правый край|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна переходит в нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Выравнивание по верхнему краю.|Исходная точка переходит в левый верхний угол целевой области, а точка выравнивания всплывающего окна переходит в левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Исходная точка переходит в правый верхний угол целевой области, а точка выравнивания всплывающего окна переходит в левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Выравнивание по верхнему краю.|Исходная точка переходит в левый верхний угол целевой области (границы указателя мыши), а точка выравнивания всплывающего окна переходит в левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна переходит в нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Выравнивание по верхнему краю.|Точка выравнивания всплывающего окна переходит в нижний левый угол <xref:System.Windows.Controls.Primitives.Popup>.|Выравнивание по левому краю.|Точка выравнивания всплывающего окна переходит в верхний правый угол всплывающего окна.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Выравнивание по верхнему краю.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Исходная точка переходит в левый верхний угол целевой области, а точка выравнивания всплывающего окна переходит в правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Исходная точка переходит в левый нижний угол целевой области, а точка выравнивания всплывающего окна переходит в левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>. Фактически, это аналогично ситуации, когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Выравнивание по нижнему краю.|Выравнивание по левому краю.|Выравнивание по правому краю.|  
  
### <a name="aligning-to-the-screen-edge"></a>Выравнивание по краю экрана  
 Объект <xref:System.Windows.Controls.Primitives.Popup> может выровняться по краю экрана путем изменения расположения, таким образом все всплывающее окно <xref:System.Windows.Controls.Primitives.Popup> будет отображаться на экране.  В этом случае расстояние между исходной точкой и точкой выравнивания всплывающего окна может отличаться от значений <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> или <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> выравнивается по всем границам экрана.  Например, предположим, что у <xref:System.Windows.Controls.Primitives.Popup> для <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> задано значение <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, а для <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> — значение 100.  Если нижний край экрана полностью или частично скрывает <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> располагается вдоль нижнего края экрана, а расстояние по вертикали между исходной точкой и точкой выравнивания всплывающего окна составляет меньше 100. Эта ситуация представлена на рисунке ниже.  
  
 ![Всплывающее окно, выравниваемое по краю экрана](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Всплывающее окно выравнивается по краю экрана.")
  
### <a name="changing-the-popup-alignment-point"></a>Изменение точки выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> или <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, точка выравнивания всплывающего окна изменяется, когда всплывающее окно достигает нижнего или правого края экрана.  
  
 На следующем рисунке показано, что, если нижний край экрана полностью или частично скрывает <xref:System.Windows.Controls.Primitives.Popup>, точка выравнивания всплывающего окна находится в левом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Всплывающее окно достигает нижнего края экрана и меняет положение точки выравнивания.")  

 На следующем рисунке показано, что, если правый край экрана скрывает <xref:System.Windows.Controls.Primitives.Popup>, точка выравнивания всплывающего окна находится в правом верхнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания всплывающего окна относительно края экрана](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Всплывающее окно достигает правого края экрана и меняет положение точки выравнивания.")
  
 Если <xref:System.Windows.Controls.Primitives.Popup> достигает нижнего и правого краев экрана, точка выравнивания всплывающего окна находится в правом нижнем углу <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Изменение положения исходной точки и точки выравнивания всплывающего окна  
 Если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> или <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, исходная точка и точка выравнивания всплывающего окна изменяются при достижении определенного края экрана.  Край экрана, который вызывает изменение положения, зависит от значения <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> и <xref:System.Windows.Controls.Primitives.Popup> достигает нижнего края экрана, то исходной точкой является левый верхний угол целевой области, а точкой выравнивания всплывающего окна — левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно нижнего края экрана](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Размещение по нижнему краю, и всплывающее окно достигает нижнего края экрана.")
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Left> и <xref:System.Windows.Controls.Primitives.Popup> достигает левого края экрана, то исходной точкой является правый верхний угол целевой области, а точкой выравнивания всплывающего окна — левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно левого края экрана](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Размещение по левому краю, и всплывающее окно достигает левого края экрана.")  
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Right> и <xref:System.Windows.Controls.Primitives.Popup> достигает правого края экрана, то исходной точкой является левый верхний угол целевой области, а точкой выравнивания всплывающего окна — правый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно правого края экрана](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Размещение по правому краю, и всплывающее окно достигает правого края экрана.")  

 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Top> и <xref:System.Windows.Controls.Primitives.Popup> достигает верхнего края экрана, то исходной точкой является левый нижний угол целевой области, а точкой выравнивания всплывающего окна — левый верхний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Новая точка выравнивания относительно верхнего края экрана](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Размещение по верхнему краю, и всплывающее окно достигает верхнего края экрана.")  
  
 На следующем рисунке показано, что если <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> имеет значение <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> и <xref:System.Windows.Controls.Primitives.Popup> достигает нижнего края экрана, то исходной точкой является левый верхний угол целевой области (границы указателя мыши), а точкой выравнивания всплывающего окна — левый нижний угол <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![новая точка выравнивания относительно положения мыши возле края экрана](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Размещение относительно мыши, и всплывающее окно достигает нижнего края экрана.")
  
### <a name="customizing-popup-placement"></a>Настройка размещения контекстного меню  
 Вы можете настроить исходную точку и точку выравнивания всплывающего окна, задав для свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> значение <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Затем определите делегат <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>, который возвращает набор возможных точек размещения и основные оси (в порядке предпочтения) для <xref:System.Windows.Controls.Primitives.Popup>. Выбирается точка, в которой отображается наибольшая часть <xref:System.Windows.Controls.Primitives.Popup>.  Расположение <xref:System.Windows.Controls.Primitives.Popup> автоматически корректируется, если граница экрана скрывает <xref:System.Windows.Controls.Primitives.Popup>. См. пример в разделе [Указание пользовательского расположения контекстного меню](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>См. также

- [Пример размещения всплывающего окна](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
