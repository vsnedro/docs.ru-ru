---
title: Общие сведения о контекстном меню
description: Сведения о элементе управления Popup Windows Presentation Foundation, который позволяет отображать содержимое в окне, расположенном поверх текущего приложения.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 84eaddc53366df6d1da1a0a005d3618268f8cce2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167536"
---
# <a name="popup-overview"></a>Общие сведения о контекстном меню
<xref:System.Windows.Controls.Primitives.Popup>Элемент управления предоставляет способ отображения содержимого в отдельном окне, расположенном поверх текущего окна приложения относительно назначенного элемента или экранной координаты. В этом разделе описывается <xref:System.Windows.Controls.Primitives.Popup> элемент управления и предоставляются сведения об его использовании.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>Что такое контекстное меню?  
 <xref:System.Windows.Controls.Primitives.Popup>Элемент управления отображает содержимое в отдельном окне относительно элемента или точки на экране. Если отображается <xref:System.Windows.Controls.Primitives.Popup> , <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> свойство имеет значение `true` .  
  
> [!NOTE]
> Объект не <xref:System.Windows.Controls.Primitives.Popup> открывается автоматически при наведении указателя мыши на родительский объект. Если нужно <xref:System.Windows.Controls.Primitives.Popup> , чтобы автоматически открывался, используйте <xref:System.Windows.Controls.ToolTip> класс или <xref:System.Windows.Controls.ToolTipService> . Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Создание всплывающего окна  
 В следующем примере показано, как определить <xref:System.Windows.Controls.Primitives.Popup> элемент управления, который является дочерним элементом <xref:System.Windows.Controls.Button> элемента управления. Так как у элемента <xref:System.Windows.Controls.Button> может быть только один дочерний элемент, в этом примере текст для <xref:System.Windows.Controls.Button> элементов управления и заносится <xref:System.Windows.Controls.Primitives.Popup> в <xref:System.Windows.Controls.StackPanel> . Содержимое элемента <xref:System.Windows.Controls.Primitives.Popup> отображается в <xref:System.Windows.Controls.TextBlock> элементе управления, который отображает его текст в отдельном окне, расположенном над окном приложения рядом с соответствующим <xref:System.Windows.Controls.Button> элементом управления.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Элементы управления, реализующие контекстное меню  
 <xref:System.Windows.Controls.Primitives.Popup>Элементы управления можно создавать в других элементах управления. Следующие элементы управления реализуют <xref:System.Windows.Controls.Primitives.Popup> элемент управления для конкретных применений.  
  
- <xref:System.Windows.Controls.ToolTip>. Если необходимо создать подсказку для элемента, используйте <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> классы и. Дополнительные сведения см. в разделе [Общие сведения о всплывающих подсказках](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Если необходимо создать контекстное меню для элемента, используйте <xref:System.Windows.Controls.ContextMenu> элемент управления. Дополнительные сведения см. в разделе [Общие сведения об элементе управления ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Если необходимо создать элемент управления выбора с раскрывающимся списком, который можно отобразить или скрыть, используйте <xref:System.Windows.Controls.ComboBox> элемент управления.  
  
- <xref:System.Windows.Controls.Expander>. Если необходимо создать элемент управления, отображающий заголовок с сворачиваемой областью отображения содержимого, используйте <xref:System.Windows.Controls.Expander> элемент управления. Дополнительные сведения см. в разделе [Общие сведения об элементе управления Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Внешний вид и поведение контекстного меню  
 <xref:System.Windows.Controls.Primitives.Popup>Элемент управления предоставляет функциональные возможности, позволяющие настраивать его поведение и внешний вид. Например, можно задать поведение открытия и закрытия, анимацию, эффекты непрозрачности и растровых эффектов, а также <xref:System.Windows.Controls.Primitives.Popup> размер и расположение.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Поведение открытия и закрытия  
 <xref:System.Windows.Controls.Primitives.Popup>Элемент управления отображает его содержимое, если <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> свойство имеет значение `true` . По умолчанию <xref:System.Windows.Controls.Primitives.Popup> остается открытым до тех пор, пока <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> свойство не будет установлено в значение `false` . Однако поведение по умолчанию можно изменить, задав <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> для свойства значение `false` . Если задать для этого свойства значение `false` , <xref:System.Windows.Controls.Primitives.Popup> окно содержимого будет иметь захват мыши. <xref:System.Windows.Controls.Primitives.Popup>Теряется захват мыши, и окно закрывается при возникновении события мыши вне <xref:System.Windows.Controls.Primitives.Popup> окна.  
  
 <xref:System.Windows.Controls.Primitives.Popup.Opened>События и <xref:System.Windows.Controls.Primitives.Popup.Closed> вызываются, когда <xref:System.Windows.Controls.Primitives.Popup> окно содержимого открыто или закрыто.  
  
<a name="Animation"></a>
### <a name="animation"></a>Анимация  
 Этот <xref:System.Windows.Controls.Primitives.Popup> элемент управления имеет встроенную поддержку анимаций, которые обычно связаны с такими поведениями, как выцветание и скольжение. Эти анимации можно включить, задав <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> для свойства <xref:System.Windows.Controls.Primitives.PopupAnimation> значение перечисления. Для <xref:System.Windows.Controls.Primitives.Popup> правильной работы анимации необходимо задать <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> для свойства значение `true` .  
  
 Можно также применить анимацию, например <xref:System.Windows.Media.Animation.Storyboard> , к <xref:System.Windows.Controls.Primitives.Popup> элементу управления.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Прозрачность и эффекты для точечных рисунков  
 <xref:System.Windows.UIElement.Opacity%2A>Свойство <xref:System.Windows.Controls.Primitives.Popup> элемента управления не влияет на его содержимое. По умолчанию <xref:System.Windows.Controls.Primitives.Popup> окно содержимого является непрозрачным. Чтобы создать прозрачный объект <xref:System.Windows.Controls.Primitives.Popup> , присвойте <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> свойству значение `true` .  
  
 Содержимое объекта не <xref:System.Windows.Controls.Primitives.Popup> наследует эффекты точечного рисунка, такие как <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> , которые непосредственно задаются для <xref:System.Windows.Controls.Primitives.Popup> элемента управления или любого другого элемента в родительском окне. Чтобы эффекты точечных рисунков отображались на содержимом <xref:System.Windows.Controls.Primitives.Popup> , необходимо задать эффект точечного рисунка непосредственно для его содержимого. Например, если дочерний элемент a <xref:System.Windows.Controls.Primitives.Popup> является <xref:System.Windows.Controls.StackPanel> , установите эффекты точечного рисунка на <xref:System.Windows.Controls.StackPanel> .  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Размер контекстного меню  
 По умолчанию <xref:System.Windows.Controls.Primitives.Popup> размер автоматически изменяется в соответствии с содержимым. При возникновении автоматического изменения размера некоторые эффекты растрового изображения могут быть скрыты, так как размер области экрана по умолчанию, определенный для <xref:System.Windows.Controls.Primitives.Popup> содержимого, не предоставляет достаточно места для отображения эффектов растрового изображения.  
  
 <xref:System.Windows.Controls.Primitives.Popup>содержимое также может быть скрыто при задании <xref:System.Windows.UIElement.RenderTransform%2A> для содержимого. В этом случае часть содержимого может быть скрыта, если содержимое преобразованного элемента выходит <xref:System.Windows.Controls.Primitives.Popup> за пределы области исходного <xref:System.Windows.Controls.Primitives.Popup> . Если для растрового изображения или преобразования требуется больше пространства, можно определить поле вокруг содержимого, <xref:System.Windows.Controls.Primitives.Popup> чтобы предоставить больше областей для элемента управления.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Определение положения контекстного меню  
 Всплывающее окно можно разместить, задав <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> свойства,,, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> и <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> . Дополнительные сведения см. в разделе [Поведение при размещении контекстного меню](popup-placement-behavior.md). Когда <xref:System.Windows.Controls.Primitives.Popup> отображается на экране, он не перемещает себя при перемещении его родительского элемента.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Настройка размещения всплывающего окна  
 Размещение <xref:System.Windows.Controls.Primitives.Popup> элемента управления можно настроить, указав набор координат, относительный относительно того, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> где должен отображаться элемент <xref:System.Windows.Controls.Primitives.Popup> .  
  
 Чтобы настроить размещение, присвойте <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойству значение <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> . Затем определите <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат, возвращающий набор возможных точек размещения и основных осей (в порядке предпочтения) для <xref:System.Windows.Controls.Primitives.Popup> . Точка, на которой показана самая крупная часть элемента, <xref:System.Windows.Controls.Primitives.Popup> выбирается автоматически. См. пример в разделе [Указание пользовательского расположения всплывающего окна](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Контекстное меню и визуальное дерево  
 <xref:System.Windows.Controls.Primitives.Popup>Элемент управления не имеет собственного визуального дерева; вместо этого он возвращает размер 0 (нуль) при <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> <xref:System.Windows.Controls.Primitives.Popup> вызове метода для. Однако если для свойства задано значение <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> <xref:System.Windows.Controls.Primitives.Popup> , то `true` создается новое окно со своим собственным визуальным деревом. Новое окно содержит <xref:System.Windows.Controls.Primitives.Popup.Child%2A> содержимое <xref:System.Windows.Controls.Primitives.Popup> . Ширина и высота нового окна не могут превышать 75 процентов от ширины или высоты экрана.  
  
 <xref:System.Windows.Controls.Primitives.Popup>Элемент управления хранит ссылку на его <xref:System.Windows.Controls.Primitives.Popup.Child%2A> содержимое как логический дочерний объект. При создании нового окна содержимое <xref:System.Windows.Controls.Primitives.Popup> становится визуальным дочерним элементом окна и остается логическим дочерним элементом <xref:System.Windows.Controls.Primitives.Popup> . И наоборот, <xref:System.Windows.Controls.Primitives.Popup> остается логическим родителем своего <xref:System.Windows.Controls.Primitives.Popup.Child%2A> содержимого.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Практические руководства](popup-how-to-topics.md)
- [Практические руководства](tooltip-how-to-topics.md)
