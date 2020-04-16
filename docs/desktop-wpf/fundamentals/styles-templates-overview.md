---
title: Стили и шаблоны
description: Узнайте о ресурсах XAML в Фонде презентаций Windows (WPF) для .NET Core. Понять типы ресурсов XAML, связанные со стилями и темами.
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433100"
---
# <a name="styles-and-templates-in-wpf"></a>Стили и шаблоны в WPF

Windows Презентация Фонда (WPF) стиль и шаблоны относятся к набору функций, которые позволяют разработчикам и дизайнерам создавать визуально убедительные эффекты и последовательный внешний вид для своего продукта. При настройке внешнего вида приложения требуется сильная модель укладки и шаблонов, которая позволяет выполнять и делиться внешним видом внутри приложений и между приложениями. WPF предоставляет эту модель.

Еще одной особенностью модели укладки WPF является разделение презентации и логики. Дизайнеры могут работать над появлением приложения, используя только XAML в то же время, что разработчики работают над логикой программирования с помощью C или Visual Basic.

В этом обзоре основное внимание уделяется аспектам укладки и шаблонов приложения и не обсуждается какие-либо концепции, связанные с имеющими обязательную силу. Подробнее о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).

Важно понимать ресурсы, которые позволяют использовать стили и шаблоны повторно. Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](xaml-resources-define.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Пример

Пример кода, приведенный в этом обзоре, основан на [простом приложении для просмотра фотографий,](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) показанном на следующей иллюстрации.

![Стилизированный ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

В этом простом примере фото стилизация и шаблоны применяются для создания привлекательного интерфейса. Образец состоит <xref:System.Windows.Controls.TextBlock> из <xref:System.Windows.Controls.ListBox> двух элементов и элемента управления, который связан со списком изображений.

Полный пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Стили

Можно думать <xref:System.Windows.Style> как удобный способ применить набор значений свойств к нескольким элементам. Вы можете использовать стиль на любом <xref:System.Windows.FrameworkElement> элементе, который <xref:System.Windows.Controls.Button>вытекает из или, <xref:System.Windows.FrameworkContentElement> например, <xref:System.Windows.Window> или .

Наиболее распространенным способом объявления стиля является `Resources` ресурс в разделе в файле XAML. Поскольку стили являются ресурсами, они подчиняются тем же правилам отслеживания, которые применяются ко всем ресурсам. Проще говоря, если вы объявите стиль влияет, где стиль может быть применен. Например, если вы объявляете стиль в корневом элементе файла XAML определения приложения, стиль можно использовать в любом месте вашего приложения.

Например, следующий код XAML объявляет `TextBlock`два стиля для `TextBlock` , один автоматически применяется ко всем элементам, а другой, который должен быть явно ссылки.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Вот пример стилей, объявленных выше используется.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![Стилизованные текстовые блоки](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Для получения дополнительной информации [см.](styles-templates-create-apply-style.md)

## <a name="controltemplates"></a>шаблоны элементов управления

В WPF <xref:System.Windows.Controls.ControlTemplate> контроль определяет внешний вид контроля. Вы можете изменить структуру и внешний <xref:System.Windows.Controls.ControlTemplate> вид элемента управления, определив новый и назначив его элементуправления. Во многих случаях шаблоны дают вам достаточную гибкость, так что вам не придется писать свои собственные пользовательские элементы управления.

Каждый элемент управления имеет шаблон по умолчанию, назначенный свойству [Control.Template.](xref:System.Windows.Controls.Control.Template) Шаблон соединяет визуальное представление элемента управления с возможностями управления. Поскольку шаблон определяется в XAML, вы можете изменить внешний вид элемента управления, не написав никакого кода. Каждый шаблон предназначен для определенного <xref:System.Windows.Controls.Button>элемента управления, например.

Обычно вы объявляете шаблон в `Resources` качестве ресурса в разделе файла XAML. Как и во всех ресурсах, применяются правила снава.

Шаблоны управления гораздо более вовлечены, чем стиль. Это происходит потому, что шаблон управления переписывает внешний вид всего элемента управления, в то время как стиль просто применяет изменения свойства к существующему элементу управления. Однако, поскольку шаблон управления применяется путем установки свойства [Control.Template,](xref:System.Windows.Controls.Control.Template) можно использовать стиль для определения или установки шаблона.

Дизайнеры обычно позволяют создать копию существующего шаблона и изменить его. Например, в Visual Studio WPF `CheckBox` дизайнер, выберите элемент управления, а затем правой кнопкой мыши и выберите **шаблон** > edit**Создать копию**. Эта команда генерирует *стиль, определяющий шаблон.*

```xaml
<Style x:Key="CheckBoxStyle1" TargetType="{x:Type CheckBox}">
    <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual1}"/>
    <Setter Property="Background" Value="{StaticResource OptionMark.Static.Background1}"/>
    <Setter Property="BorderBrush" Value="{StaticResource OptionMark.Static.Border1}"/>
    <Setter Property="Foreground" Value="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type CheckBox}">
                <Grid x:Name="templateRoot" Background="Transparent" SnapsToDevicePixels="True">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Border x:Name="checkBoxBorder" Background="{TemplateBinding Background}" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="1" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
                        <Grid x:Name="markGrid">
                            <Path x:Name="optionMark" Data="F1 M 9.97498,1.22334L 4.6983,9.09834L 4.52164,9.09834L 0,5.19331L 1.27664,3.52165L 4.255,6.08833L 8.33331,1.52588e-005L 9.97498,1.22334 Z " Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="1" Opacity="0" Stretch="None"/>
                            <Rectangle x:Name="indeterminateMark" Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="2" Opacity="0"/>
                        </Grid>
                    </Border>
                    <ContentPresenter x:Name="contentPresenter" Grid.Column="1" Focusable="False" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="HasContent" Value="true">
                        <Setter Property="FocusVisualStyle" Value="{StaticResource OptionMarkFocusVisual1}"/>
                        <Setter Property="Padding" Value="4,-1,0,0"/>

... content removed to save space ...
```

Редактирование копии шаблона — это отличный способ узнать, как работают шаблоны. Вместо создания нового пустого шаблона проще отсеивать копию и изменять некоторые аспекты визуальной презентации.

Например, [см. Создать шаблон для управления.](../themes/how-to-create-apply-template.md)

### <a name="templatebinding"></a>TemplateBinding

Возможно, вы заметили, что ресурс шаблона, определенный в предыдущем разделе, использует [расширение шаблонной разметки.](../../framework/wpf/advanced/templatebinding-markup-extension.md) A `TemplateBinding` — это оптимизированная форма привязки для шаблонных сценариев, аналогичная привязке, построенной с `{Binding RelativeSource={RelativeSource TemplatedParent}}`помощью . `TemplateBinding`полезен для привязки частей шаблона к свойствам элемента управления. Например, каждый <xref:System.Windows.Controls.Control.BorderThickness> элемент управления имеет свойство. Используйте `TemplateBinding` элемент для управления, какой элемент в шаблоне зависит от этой настройки элемента управления.

### <a name="contentcontrol-and-itemscontrol"></a>КонтентКонтроль и элементыКонтроль

Если <xref:System.Windows.Controls.ContentPresenter> a объявлен <xref:System.Windows.Controls.ControlTemplate> в <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ContentPresenter> то автоматически привязывается к свойствам <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A> свойствам. Аналогичным образом, <xref:System.Windows.Controls.ItemsPresenter> то, <xref:System.Windows.Controls.ControlTemplate> что <xref:System.Windows.Controls.ItemsControl> находится в воле <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ItemsControl.Items%2A> автоматически привязывается к свойствам и свойствам.

## <a name="datatemplates"></a>ДанныеШаблоны

В этом примере <xref:System.Windows.Controls.ListBox> приложения есть элемент управления, который связан со списком фотографий.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

Это <xref:System.Windows.Controls.ListBox> в настоящее время выглядит следующим образом.

![ListBox до применения шаблона](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

Большинство элементов управления имеют некое содержимое, и это содержимое часто поступает из данных, к которым осуществляется привязка. В этом примере такими данными является список фотографий. В WPF используется <xref:System.Windows.DataTemplate> для определения визуального представления данных. В основном, то, <xref:System.Windows.DataTemplate> что вы вкладываете в определяет, как выглядят данные в отрисованной приложении.

В нашем примере `Photo` приложения каждый пользовательский объект имеет свойство `Source` строки типа, которая определяет траекторию файла изображения. Сейчас объекты фотографий отображаются как пути к файлам.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Для того, чтобы фотографии отображались в виде изображений, вы создаете <xref:System.Windows.DataTemplate> ресурс.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Обратите внимание, что свойство <xref:System.Windows.DataTemplate.DataType%2A> аналогично собственности <xref:System.Windows.Style.TargetType%2A> . <xref:System.Windows.Style> Если <xref:System.Windows.DataTemplate> вы находится в разделе ресурсов, <xref:System.Windows.DataTemplate.DataType%2A> когда вы указываете `x:Key`свойство <xref:System.Windows.DataTemplate> к типу и опускают, применяется всякий раз, когда этот тип появляется. У вас всегда есть возможность <xref:System.Windows.DataTemplate> назначить `x:Key` с, а `StaticResource` затем установить его в качестве свойств, которые принимают <xref:System.Windows.DataTemplate> типы, такие как <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство или <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойство.

По <xref:System.Windows.DataTemplate> существу, в приведенном выше примере `Photo` определяется, что всякий раз, когда есть объект, он должен отображаться <xref:System.Windows.Controls.Image> как в <xref:System.Windows.Controls.Border>пределах . При <xref:System.Windows.DataTemplate>этом, наше приложение теперь выглядит следующим образом.

![Фото](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

Модель использования шаблонов данных предоставляет и другие возможности. Например, если вы отображаете данные о <xref:System.Windows.Controls.HeaderedItemsControl> сборе, <xref:System.Windows.Controls.Menu> содержащие другие коллекции, с помощью типа, например a или a, <xref:System.Windows.Controls.TreeView>есть . <xref:System.Windows.HierarchicalDataTemplate> Другой функцией шаблонирования <xref:System.Windows.Controls.DataTemplateSelector>данных является, который <xref:System.Windows.DataTemplate> позволяет выбрать для использования на основе пользовательской логики. Дополнительные сведения см. в разделе [Общие сведения о шаблонах данных](../../framework/wpf/data/data-templating-overview.md), в котором более подробно рассматриваются различные возможности использования шаблонов данных.

## <a name="triggers"></a>Триггеры

Триггер задает значения свойств или активирует различные действия (например, анимацию) при изменении значения свойства или при возникновении какого-либо события. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate> и `Triggers` все они имеют свойство, которое может содержать набор триггеров. Существует несколько типов триггеров.

### <a name="propertytriggers"></a>НедвижимостьТриггеры

А, <xref:System.Windows.Trigger> который устанавливает значения свойств или запускает действия, основанные на значении свойства, называется триггером свойства.

Чтобы продемонстрировать, как использовать триггеры <xref:System.Windows.Controls.ListBoxItem> свойств, можно сделать каждый частично прозрачным, если он не выбран. Следующий стиль <xref:System.Windows.UIElement.Opacity%2A> устанавливает значение <xref:System.Windows.Controls.ListBoxItem> `0.5`до . Когда <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> `true`свойство, однако, <xref:System.Windows.UIElement.Opacity%2A> установлен `1.0`на .

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

В этом <xref:System.Windows.Trigger> примере используется значение для установки значения свойств, но обратите внимание, что <xref:System.Windows.Trigger> в классе также есть <xref:System.Windows.TriggerBase.EnterActions%2A> свойства и <xref:System.Windows.TriggerBase.ExitActions%2A> свойства, позволяющие триггеру выполнять действия.

Обратите внимание, что <xref:System.Windows.Controls.ListBoxItem> свойство `75` <xref:System.Windows.FrameworkElement.MaxHeight%2A> установлен о . В следующей иллюстрации третьим элементом является выбранный элемент.

![Стилизированный ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>Объекты EventTrigger и раскадровки

Другой тип триггера <xref:System.Windows.EventTrigger>, который запускает набор действий, основанных на возникновении события. <xref:System.Windows.EventTrigger> Например, следующие объекты указывают, что при <xref:System.Windows.Controls.ListBoxItem>входе указателя мыши в свойство <xref:System.Windows.FrameworkElement.MaxHeight%2A> оживляет значение `90` более второго `0.2` периода. Когда указатель мыши перемещается за пределы этого элемента, свойство возвращается к исходному значению в течение `1` сек. Обратите внимание, что нет <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> необходимости <xref:System.Windows.ContentElement.MouseLeave> указывать значение для анимации. Анимация сама может отслеживать исходное значение.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Для получения дополнительной информации смотрите [обзор раскадровок](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

На следующей иллюстрации мышь указывает на третий элемент.

![Укладка образца скриншот](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>Объекты MultiTrigger, DataTrigger и MultiDataTrigger

В дополнение <xref:System.Windows.Trigger> <xref:System.Windows.EventTrigger>к и , Есть другие типы триггеров. <xref:System.Windows.MultiTrigger>позволяет устанавливать значения свойств на основе нескольких условий. Вы <xref:System.Windows.DataTrigger> используете и <xref:System.Windows.MultiDataTrigger> когда свойство вашего состояния связано с данными.

## <a name="visual-states"></a>Визуальные состояния

Элементы управления всегда находятся в определенном **состоянии.** Например, когда мышь перемещается по поверхности элемента управления, элемент управления `MouseOver`считается в общем состоянии. Контроль без определенного состояния считается в `Normal` общем состоянии. Государства разбиты на группы, а ранее упомянутые `CommonStates`государства входят в состав государственной группы. Большинство элементов управления `CommonStates` имеют `FocusStates`две группы штатов: и . Из каждой группы штатов, применяемой к элементу `CommonStates.MouseOver` управления, контроль всегда находится в одном состоянии каждой группы, например и `FocusStates.Unfocused`. Тем не менее, элемент управления не может находиться в `CommonStates.Normal` `CommonStates.Disabled`двух разных состояниях в рамках одной и той же группы, таких как и . Вот таблица состояний, которые большинство элементов управления распознают и используют.

| Имя VisualState | Имя VisualStateGroup | Описание |
| ---------------- | --------------------- | ----------- |
| Нормальный           | CommonStates          | Состояние по умолчанию. |
| MouseOver        | CommonStates          | Указатель мыши расположен над элементом управления. |
| Нажато          | CommonStates          | Элемент управления нажат. |
| Выключено         | CommonStates          | Элемент управления отключен. |
| Focused          | FocusStates           | Элемент управления имеет фокус. |
| Без фокуса ввода        | FocusStates           | Элемент управления не имеет фокуса. |

Определив корневой <xref:System.Windows.VisualStateManager?displayProperty=fullName> элемент шаблона управления, можно вызвать анимацию при входе элемента управления в определенное состояние. Декларирует, `VisualStateManager` какие <xref:System.Windows.VisualStateGroup> комбинации и <xref:System.Windows.VisualState> смотреть. При входе элемента управления в наблюдаемое состояние запускается анимация, определяемая `VisaulStateManager` the.

Например, следующий код XAML наблюдает за `CommonStates.MouseOver` состоянием для анимации цвета заполнения названного `backgroundElement`элемента. Когда элемент управления `CommonStates.Normal` возвращается в состояние, цвет `backgroundElement` заполнения названного элемента восстанавливается.

```xaml
<ControlTemplate x:Key="roundbutton" TargetType="Button">
    <Grid>
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="{TemplateBinding Background}"
                                    Duration="0:0:0.3"/>
                </VisualState>
                <VisualState Name="MouseOver">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="Yellow"
                                    Duration="0:0:0.3"/>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>

        ...
```

Для получения дополнительной информации о раскадровки, см [Storyboards Обзор](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

## <a name="shared-resources-and-themes"></a>Общие ресурсы и темы

Типичное приложение WPF может иметь несколько ресурсов uI, которые применяются по всему приложению. В совокупности этот набор ресурсов можно считать темой приложения. WPF обеспечивает поддержку упаковки ресурсов UI в качестве темы, используя <xref:System.Windows.ResourceDictionary> словарь ресурсов, который инкапсулируется как класс.

Темы WPF определяются с помощью механизма укладки и шаблонирования, который WPF предоставляет для настройки визуальных элементов любого элемента.

Тематические ресурсы WPF хранятся во встроенных словарях ресурсов. Эти словари ресурсов должны быть внедрены в подписанную сборку и могут быть внедрены либо в ту же сборку, что и сам код, либо в параллельную сборку. Для PresentationFramework.dll, сборки, содержащей элементы управления WPF, тематические ресурсы находятся в серии бок о бок сборки.

Тема становится последним местом поиска стиля элемента. Как правило, поиск начинается с прогулки по дереву элементов в поисках соответствующего ресурса, затем заглядывать в коллекцию ресурсов приложения и, наконец, запросить систему. Это дает разработчикам приложений возможность пересмотреть стиль для любого объекта на уровне дерева или приложения, прежде чем достичь темы.

Словари ресурсов можно определить как отдельные файлы, которые позволяют повторно использовать тему в нескольких приложениях. Также можно создать изменяемые темы, определив несколько словарей ресурсов, которые обеспечивают одни и те же типы ресурсов, но с разными значениями. Переосмысление этих стилей или других ресурсов на уровне приложения является рекомендуемым подходом для скиннинга приложения.

Чтобы поделиться набором ресурсов, включая стили и шаблоны, в приложениях <xref:System.Windows.ResourceDictionary> можно создать `shared.xaml` файл XAML и определить файл, включающий ссылку на файл.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

Это совместное `shared.xaml`использование , который <xref:System.Windows.ResourceDictionary> сам определяет, который содержит набор стилей и кисти ресурсов, что позволяет управления в приложении, чтобы иметь последовательный вид.

Для получения дополнительной [информации см.](../../framework/wpf/advanced/merged-resource-dictionaries.md)

Если вы создаете тему для пользовательского управления, **см. Определяющие ресурсы в** разделе темного уровня [авторского обзора Управления.](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level)

## <a name="see-also"></a>См. также

- [URI типа "pack" в WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [Практическое руководство. Поиск элемента, созданного шаблоном ControlTemplate](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Поиск элементов, генерируемых DataTemplate](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
