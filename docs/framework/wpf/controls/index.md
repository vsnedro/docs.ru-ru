---
title: Элементы управления
description: Сведения о Windows Presentation Foundation общих компонентов пользовательского интерфейса, которые называются элементами управления, но которые могут не наследовать от класса Control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: c3d9d3a38cf5f84e21df195e113e264e5a4ac025
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165853"
---
# <a name="controls"></a>Элементы управления
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]поставляется с множеством общих компонентов пользовательского интерфейса, которые используются практически в любом приложении Windows, например,, <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBox> , <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.ListBox> . Исторически эти объекты называются элементами управления. Хотя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] пакет SDK по-видимому использует термин "элемент управления" для нестрогого обозначения любого класса, представляющего видимый объект в приложении, важно отметить, что классу не нужно наследовать от класса, <xref:System.Windows.Controls.Control> чтобы иметь видимое присутствие. Классы, наследуемые от класса <xref:System.Windows.Controls.Control>, содержат шаблон <xref:System.Windows.Controls.ControlTemplate>, который позволяет существенно изменить внешний вид элемента управления, не создавая новый подкласс.  В этом разделе описывается, как часто используются элементы управления (которые наследуются от <xref:System.Windows.Controls.Control> класса и те, которые не являются) в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>Создание экземпляра элемента управления  
 Элемент управления можно добавить в приложение с помощью либо кода, либо [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .  В следующем примере показано, как создать простое приложение, которое запрашивает у пользователя имя и фамилию.  В этом примере создается шесть элементов управления: две метки, два текстовых поля и две кнопки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере создается такое же приложение в коде. Для краткости создание <xref:System.Windows.Controls.Grid> , `grid1` , было исключено из примера. `grid1`имеет одинаковые определения столбцов и строк, как показано в предыдущем [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>Изменение внешнего вида элемента управления  
 Обычно внешний вид элемента управления изменяется в соответствии с внешним видом приложения. Можно изменить внешний вид элемента управления, выполнив одно из следующих действий (в зависимости от того, чего нужно достичь):  
  
- Измените значение свойства элемента управления.  
  
- Создайте <xref:System.Windows.Style> для элемента управления.  
  
- Создайте новый <xref:System.Windows.Controls.ControlTemplate> элемент управления.  
  
### <a name="changing-a-controls-property-value"></a>Изменение значения свойства элемента управления  
 Многие элементы управления имеют свойства, позволяющие изменять способ отображения элемента управления, например, <xref:System.Windows.Controls.Control.Background%2A> объекта <xref:System.Windows.Controls.Button> . Свойства значения можно задать в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и в коде. В следующем примере задаются <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Control.FontSize%2A> свойства, и в <xref:System.Windows.Controls.Control.FontWeight%2A> <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Следующий пример устанавливает те же самые свойства в коде.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Создание стиля для элемента управления  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]дает возможность задавать внешний вид элементов управления, а не задавать свойства для каждого экземпляра в приложении, создавая <xref:System.Windows.Style> . В следующем примере создается объект <xref:System.Windows.Style> , который применяется к каждому <xref:System.Windows.Controls.Button> в приложении. <xref:System.Windows.Style>определения обычно определяются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в <xref:System.Windows.ResourceDictionary> , например <xref:System.Windows.FrameworkElement.Resources%2A> свойство объекта <xref:System.Windows.FrameworkElement> .  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Можно также применить стиль только к определенным элементам управления определенного типа, назначив ключ стилю и указав этот ключ в `Style` свойстве элемента управления.  Дополнительные сведения о стилях см. в статье [Стили и шаблоны в WPF](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
### <a name="creating-a-controltemplate"></a>Создание шаблона ControlTemplate  
 <xref:System.Windows.Style>Позволяет задавать свойства для нескольких элементов управления за раз, но иногда может потребоваться настроить внешний вид, чем <xref:System.Windows.Controls.Control> вы можете сделать, создав <xref:System.Windows.Style> . Классы, наследующие от <xref:System.Windows.Controls.Control> класса, имеют класс <xref:System.Windows.Controls.ControlTemplate> , который определяет структуру и внешний вид <xref:System.Windows.Controls.Control> . <xref:System.Windows.Controls.Control.Template%2A>Свойство объекта <xref:System.Windows.Controls.Control> является открытым, поэтому можно присвоить <xref:System.Windows.Controls.Control> значение, отличное <xref:System.Windows.Controls.ControlTemplate> от значения по умолчанию. Часто можно указать новое значение <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Control> вместо наследования от элемента управления для настройки внешнего вида <xref:System.Windows.Controls.Control> .  
  
 Рассмотрим очень распространенный элемент управления, <xref:System.Windows.Controls.Button> .  Основное поведение <xref:System.Windows.Controls.Button> приложения — позволить приложению предпринимать какие-либо действия, когда пользователь щелкнет его.  По умолчанию <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается как порожденный прямоугольник.  При разработке приложения может потребоваться использовать преимущества поведения, т. е. <xref:System.Windows.Controls.Button> обрабатывая событие нажатия кнопки, но вы можете изменить внешний вид кнопки, выполнив изменения свойств кнопки.  В этом случае можно создать новый объект <xref:System.Windows.Controls.ControlTemplate> .  
  
 В следующем примере создается <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> .  <xref:System.Windows.Controls.ControlTemplate>Создает объект <xref:System.Windows.Controls.Button> с закругленными углами и градиентным фоном.  Объект <xref:System.Windows.Controls.ControlTemplate> содержит объект, который <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Border.Background%2A> является <xref:System.Windows.Media.LinearGradientBrush> с двумя <xref:System.Windows.Media.GradientStop> объектами.  В первом <xref:System.Windows.Media.GradientStop> используется привязка данных для привязки <xref:System.Windows.Media.GradientStop.Color%2A> свойства объекта <xref:System.Windows.Media.GradientStop> к цвету фона кнопки.  При задании <xref:System.Windows.Controls.Control.Background%2A> свойства <xref:System.Windows.Controls.Button> , цвет этого значения будет использоваться в качестве первого <xref:System.Windows.Media.GradientStop> . Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md). В примере также создается объект <xref:System.Windows.Trigger> , который изменяет внешний вид, <xref:System.Windows.Controls.Button> когда <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> имеет значение `true` .  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Чтобы <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> пример работал правильно, свойство объекта должно иметь значение <xref:System.Windows.Media.SolidColorBrush> .  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>Подписка на события  
 Вы можете подписываться на события элемента управления с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода, но вы можете только обрабатывали событие в коде.  В следующем примере показано, как подписываться на `Click` событие объекта <xref:System.Windows.Controls.Button> .  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 В следующем примере обрабатывается `Click` событие объекта <xref:System.Windows.Controls.Button> .  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>Форматированное содержимое в элементах управления  
 Большинство классов, наследующих от <xref:System.Windows.Controls.Control> класса, имеют емкость для хранения форматированного содержимого. Например, <xref:System.Windows.Controls.Label> может содержать любой объект, например строку, <xref:System.Windows.Controls.Image> или <xref:System.Windows.Controls.Panel> .  Следующие классы обеспечивают поддержку расширенного содержимого и служат базовыми классами для большинства элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  
  
- <xref:System.Windows.Controls.ContentControl>--Некоторые примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.Label> , <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.ToolTip> .  
  
- <xref:System.Windows.Controls.ItemsControl>--Некоторые примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.ListBox> , <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.Primitives.StatusBar> .  
  
- <xref:System.Windows.Controls.HeaderedContentControl>--Некоторые примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.TabItem> , <xref:System.Windows.Controls.GroupBox> и <xref:System.Windows.Controls.Expander> .  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Некоторые примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.MenuItem> , <xref:System.Windows.Controls.TreeViewItem> и <xref:System.Windows.Controls.ToolBar> .  

 Дополнительные сведения об этих базовых классах см. в разделе [модель содержимого WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>См. также раздел

- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Категории элементов управления](controls-by-category.md)
- [Библиотека элементов управления](control-library.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Ввод](../advanced/input-wpf.md)
- [Включение команды](../advanced/how-to-enable-a-command.md)
- [Пошаговые руководства. Создание пользовательской анимированной кнопки](walkthroughs-create-a-custom-animated-button.md)
- [Настройка элементов управления](control-customization.md)
