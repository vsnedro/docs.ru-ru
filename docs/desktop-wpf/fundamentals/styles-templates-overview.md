---
title: Стили и шаблоны
description: Сведения о ресурсах XAML в Windows Presentation Foundation (WPF) для .NET Core. Ознакомьтесь с общими сведениями о типах ресурсов XAML, связанных со стилями и темами.
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433100"
---
# <a name="styles-and-templates-in-wpf"></a>Стили и шаблоны в WPF

Стилизация и использование шаблонов Windows Presentation Foundation (WPF) относятся к набору возможностей, которые позволяют разработчикам и дизайнерам создавать визуально привлекательные эффекты и согласованный внешний вид своих продуктов. При настройке внешнего вида приложения необходима строгая модель стилизации и шаблонов, обеспечивающая обслуживание и совместное использование внешнего вида в приложениях и между ними. WPF предоставляет такую модель.

Еще одной возможностью модели стилизации WPF является разделение представления и логики. Дизайнеры могут создавать внешний вид приложения только с помощью XAML в то же самое время, когда разработчики работают над логикой программы, используя языки C# или Visual Basic.

В этом обзоре основное внимание уделяется аспектам стилизации и использования шаблонов приложения и не рассматриваются концепции привязки данных. Подробнее о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).

Важно иметь представление о ресурсах, которые позволяют повторно использовать стили и шаблоны. Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](xaml-resources-define.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Пример

В примере кода, приведенного в этом обзоре, используется [простое приложение для просмотра фотографий](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating), показанное ниже.

![Стилизированный ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

В этом простом примере фото стилизация и шаблоны применяются для создания привлекательного интерфейса. Пример содержит два элемента <xref:System.Windows.Controls.TextBlock> и элемент управления <xref:System.Windows.Controls.ListBox>, привязанный к списку изображений.

Полный пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Стили

Элемент <xref:System.Windows.Style> можно рассматривать как удобный способ применения набора значений свойств к нескольким элементам. Стиль можно использовать для любого элемента, производного от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, например <xref:System.Windows.Window> или <xref:System.Windows.Controls.Button>.

Чаще всего стиль объявляется как ресурс в разделе `Resources` файла XAML. Так как стили являются ресурсами, для них действуют те же правила определения области, что и для всех других ресурсов. Проще говоря, то, где вы объявляете стиль, влияет на то, где этот стиль может быть применен. Например, если объявить стиль в корневом элементе файла XAML определения приложения, стиль может использоваться в любом месте приложения.

Например, в следующем коде XAML объявляются два стиля для `TextBlock`, один из которых автоматически применяется ко всем элементам `TextBlock`, а для другого необходимы явные ссылки.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Ниже приведен пример стилей, объявленных выше.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![TextBlock со стилизацией](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Дополнительные сведения см. в статье [Создание стиля элемента управления в WPF](styles-templates-create-apply-style.md).

## <a name="controltemplates"></a>ControlTemplates

В WPF <xref:System.Windows.Controls.ControlTemplate> элемента управления определяет внешний вид этого элемента управления. Структуру и внешний вид элемента управления можно изменить, определив и назначив для него новый объект <xref:System.Windows.Controls.ControlTemplate>. Во многих случаях шаблоны являются достаточно гибким средством, и вам не придется писать собственные пользовательские элементы управления.

Каждый элемент управления имеет шаблон по умолчанию, назначенный свойству [Control.Template](xref:System.Windows.Controls.Control.Template). Шаблон соединяет визуальное представление элемента управления с его возможностями. Путем определения шаблона в XAML можно изменить внешний вид элемента управления без написания какого-либо кода. Каждый шаблон предназначен для конкретного элемента управления, например <xref:System.Windows.Controls.Button>.

Обычно шаблон объявляется как ресурс в разделе `Resources` файла XAML. Как и для всех ресурсов применяются правила области.

Шаблоны элементов управления более сложные, чем стиль. Это связано с тем, что шаблон элемента управления перезаписывает весь его внешний вид, в то время как стиль просто применяет изменения свойств к существующему элементу управления. Однако, так как шаблон элемента управления применяется путем установки свойства [Control.Template](xref:System.Windows.Controls.Control.Template), можно использовать стиль для определения или установки шаблона.

Обычно разработчики позволяют создать копию существующего шаблона и изменить ее. Например, в конструкторе WPF в Visual Studio выберите элемент управления `CheckBox`, а затем щелкните правой кнопкой мыши и последовательно выберите **Изменить шаблон** > **Создать копию**. Эта команда создает *стиль, который определяет шаблон*.

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

Редактирование копии шаблона — отличный способ научиться работать с шаблонами. Вместо создания пустого шаблона проще редактировать копию и изменять некоторые аспекты визуального представления.

Пример см. в статье [Создание шаблона элемента управления](../themes/how-to-create-apply-template.md).

### <a name="templatebinding"></a>TemplateBinding

Возможно, вы заметили, что ресурс шаблона, определенный в предыдущем разделе, использует [расширение разметки TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md). `TemplateBinding` является оптимизированной формой привязки для сценариев шаблонов, аналогичных привязке, созданной с помощью `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` может использоваться для привязки частей шаблона к свойствам элемента управления. Например, каждый элемент управления имеет свойство <xref:System.Windows.Controls.Control.BorderThickness>. Используйте `TemplateBinding`, чтобы управлять элементом шаблона, затрагиваемым параметром элемента управления.

### <a name="contentcontrol-and-itemscontrol"></a>ContentControl и ItemsControl

Если в элементе <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ContentControl> объявляется <xref:System.Windows.Controls.ContentPresenter>, элемент <xref:System.Windows.Controls.ContentPresenter> будет автоматически привязан к свойствам <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A>. Аналогичным образом элемент <xref:System.Windows.Controls.ItemsPresenter>, который находится в <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ItemsControl>, автоматически привязывается к свойствам <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> и <xref:System.Windows.Controls.ItemsControl.Items%2A>.

## <a name="datatemplates"></a>DataTemplates

В этом примере приложения имеется элемент управления <xref:System.Windows.Controls.ListBox>, связанный со списком фотографий.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

Теперь <xref:System.Windows.Controls.ListBox> выглядит так.

![ListBox до применения шаблона](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

Большинство элементов управления имеют некое содержимое, и это содержимое часто поступает из данных, к которым осуществляется привязка. В этом примере такими данными является список фотографий. В WPF для определения визуального представления данных можно использовать <xref:System.Windows.DataTemplate>. По сути, то, что вы поместите в <xref:System.Windows.DataTemplate>, определяет визуальное представление данных в отображаемом приложении.

В нашем примере приложения каждый пользовательский объект `Photo` имеет свойство `Source` строкового типа, которое задает путь к файлу изображения. Сейчас объекты фотографий отображаются как пути к файлам.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Чтобы фотографии отображались как изображения, необходимо создать <xref:System.Windows.DataTemplate> в качестве ресурса.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Обратите внимание, что свойство <xref:System.Windows.DataTemplate.DataType%2A> подобно свойству <xref:System.Windows.Style.TargetType%2A> <xref:System.Windows.Style>. Если <xref:System.Windows.DataTemplate> находится в разделе ресурсов, когда вы указываете свойство <xref:System.Windows.DataTemplate.DataType%2A> для типа и не назначаете ему атрибут `x:Key`, <xref:System.Windows.DataTemplate> будет применяться каждый раз при появлении этого типа. Вы всегда можете назначить <xref:System.Windows.DataTemplate> атрибут `x:Key`, а затем задать его в качестве `StaticResource` для свойств, которые принимают типы <xref:System.Windows.DataTemplate> (например, свойство <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> или <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>).

По существу <xref:System.Windows.DataTemplate> в приведенном выше примере определяет, что при наличии объекта `Photo` он должен отображаться в качестве элемента <xref:System.Windows.Controls.Image> в рамках <xref:System.Windows.Controls.Border>. С этим шаблоном <xref:System.Windows.DataTemplate> приложение теперь выглядит так.

![Фото](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

Модель использования шаблонов данных предоставляет и другие возможности. Например, для отображения данных коллекции, содержащей другие коллекции, с помощью типа <xref:System.Windows.Controls.HeaderedItemsControl>, например <xref:System.Windows.Controls.Menu> или <xref:System.Windows.Controls.TreeView>, имеется шаблон <xref:System.Windows.HierarchicalDataTemplate>. Другой возможностью использования шаблонов данных является элемент<xref:System.Windows.Controls.DataTemplateSelector>, который позволяет выбрать <xref:System.Windows.DataTemplate> для использования на основе пользовательской логики. Дополнительные сведения см. в разделе [Общие сведения о шаблонах данных](../../framework/wpf/data/data-templating-overview.md), в котором более подробно рассматриваются различные возможности использования шаблонов данных.

## <a name="triggers"></a>Триггеры

Триггер задает значения свойств или активирует различные действия (например, анимацию) при изменении значения свойства или при возникновении какого-либо события. В <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>и <xref:System.Windows.DataTemplate> есть свойство `Triggers`, которое может содержать набор триггеров. Существует несколько типов триггеров.

### <a name="propertytriggers"></a>PropertyTriggers

Объект <xref:System.Windows.Trigger>, который задает значения свойств или активирует действия на основе значения свойства, называется триггером свойств.

Чтобы продемонстрировать использование триггеров свойств, можно сделать каждый элемент <xref:System.Windows.Controls.ListBoxItem> частично прозрачным, если он не выбран. В следующем стиле для свойства <xref:System.Windows.UIElement.Opacity%2A> типа <xref:System.Windows.Controls.ListBoxItem> задается значение `0.5`. Если свойство <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> имеет значение`true`, то, несмотря на это, для <xref:System.Windows.UIElement.Opacity%2A> присваивается значение `1.0`.

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

В этом примере объект <xref:System.Windows.Trigger> используется для установки значения свойства, но обратите внимание, что у класса <xref:System.Windows.Trigger> также есть свойства <xref:System.Windows.TriggerBase.EnterActions%2A> и <xref:System.Windows.TriggerBase.ExitActions%2A>, которые позволяют триггеру выполнять действия.

Обратите внимание, что свойство <xref:System.Windows.FrameworkElement.MaxHeight%2A> типа <xref:System.Windows.Controls.ListBoxItem> имеет значение `75`. На следующем рисунке третий элемент является выбранным.

![Стилизированный ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>Объекты EventTrigger и раскадровки

Еще один тип триггера — это объект <xref:System.Windows.EventTrigger>, который активирует набор действий по возникновению события. Например, следующие объекты <xref:System.Windows.EventTrigger> определяют, что при наведении указателя мыши на элемент <xref:System.Windows.Controls.ListBoxItem> выполняется анимированный переход свойства <xref:System.Windows.FrameworkElement.MaxHeight%2A> к значению `90` в течение `0.2` сек. Когда указатель мыши перемещается за пределы этого элемента, свойство возвращается к исходному значению в течение `1` сек. Обратите внимание, что нет необходимости указывать значение <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> для анимации <xref:System.Windows.ContentElement.MouseLeave>. Анимация сама может отслеживать исходное значение.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Подробнее см. в статье [Общие сведения о Storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

На следующем рисунке указатель мыши наведен на третий элемент.

![Снимок экрана: пример стилизации](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>Объекты MultiTrigger, DataTrigger и MultiDataTrigger

Помимо триггеров <xref:System.Windows.Trigger> и <xref:System.Windows.EventTrigger>, существуют и другие типы триггеров. Триггер <xref:System.Windows.MultiTrigger> позволяет задавать значения свойств на основании нескольких условий. Используйте триггеры <xref:System.Windows.DataTrigger> и <xref:System.Windows.MultiDataTrigger>, когда свойство условия имеет привязку к данным.

## <a name="visual-states"></a>Визуальные состояния

Элементы управления всегда находятся в определенном **состоянии**. Например, когда указатель мышь перемещается над элементом управления, то считается, что элемент управления находится в обычном состоянии `MouseOver`. Элемент управления без определенного состояния рассматривается как элемент управления с обычным состоянием `Normal`. Состояния разбиваются на группы, а упомянутые выше состояния являются частью группы состояний `CommonStates`. Большинство элементов управления имеют две группы состояний: `CommonStates` и `FocusStates`. Для каждой группы состояний, применяемой к элементу управления, элемент управления всегда находится в одном из состояний каждой группы, например `CommonStates.MouseOver` и `FocusStates.Unfocused`. Элемент управления не может находиться в двух разных состояниях в рамках одной группы, например `CommonStates.Normal` и `CommonStates.Disabled`. Ниже приведена таблица состояний, которые большинство элементов управления распознают и используют.

| Имя VisualState | Имя VisualStateGroup | Описание |
| ---------------- | --------------------- | ----------- |
| Норм.           | CommonStates          | Состояние по умолчанию. |
| MouseOver        | CommonStates          | Указатель мыши расположен в элементе управления. |
| Нажато          | CommonStates          | Элемент управления нажат. |
| Отключено         | CommonStates          | Элемент управления отключен. |
| Focused          | FocusStates           | Элемент управления имеет фокус. |
| Без фокуса ввода        | FocusStates           | Элемент управления не имеет фокуса. |

Определив <xref:System.Windows.VisualStateManager?displayProperty=fullName> в корневом элементе шаблона элемента управления, вы можете активировать анимации при переходе элемента управления в определенное состояние. `VisualStateManager` объявляет, какие сочетания <xref:System.Windows.VisualStateGroup> и <xref:System.Windows.VisualState> отслеживать. Когда элемент управления переходит в состояние отслеживания, запускается анимация, определенная `VisaulStateManager`.

Например, следующий код XAML отслеживает состояние `CommonStates.MouseOver`, чтобы анимировать цвет заливки элемента `backgroundElement`. Когда элемент управления возвращается в состояние `CommonStates.Normal`, восстанавливается цвет заливки элемента `backgroundElement`.

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

Дополнительные сведения о раскадровках см. в статье [Общие сведения о Storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

## <a name="shared-resources-and-themes"></a>Общие ресурсы и темы

Типичное приложение WPF может иметь несколько ресурсов пользовательского интерфейса, которые применяются в рамках всего приложения. В совокупности этот набор ресурсов можно рассматривать как тему приложения. WPF поддерживает упаковку ресурсов пользовательского интерфейса в виде темы, используя словарь ресурсов, который инкапсулируется как класс <xref:System.Windows.ResourceDictionary>.

Темы WPF задаются с помощью механизмов стилизации и использования шаблонов, которые WPF предоставляет для настройки отображения любого элемента.

Ресурсы темы WPF хранятся в словарях внедренных ресурсов. Эти словари ресурсов должны быть внедрены в подписанную сборку и могут быть внедрены либо в ту же сборку, что и сам код, либо в параллельную сборку. Для библиотеки PresentationFramework.dll (сборки, содержащей элементы управления WPF) ресурсы тем находятся в ряде параллельных сборок.

Тема становится последним местом поиска стиля элемента. Как правило, процесс поиска начинается с прохода вверх по дереву элементов в поисках соответствующего ресурса, затем выполняется поиск в коллекции ресурсов приложения и, наконец, в последнюю очередь осуществляется запрос к системе. Это дает разработчикам приложений возможность переопределить стиль для любого объекта на уровне дерева или приложения до достижения темы.

Словари ресурсов, оформленные в виде отдельных файлов, позволяют повторно использовать тему в нескольких приложениях. Также можно создать изменяемые темы, определив несколько словарей ресурсов, которые обеспечивают одни и те же типы ресурсов, но с разными значениями. Переопределение этих стилей или других ресурсов на уровне приложения является рекомендуемым способом смены тем приложения.

Для совместного использования набора ресурсов (в том числе стилей и шаблонов) в приложениях можно создать файл XAML и определить объект <xref:System.Windows.ResourceDictionary>, который содержит ссылку на файл `shared.xaml`.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

Это совместное использование файла `shared.xaml`, который определяет объект <xref:System.Windows.ResourceDictionary>, содержащий набор стилей и ресурсов кисти, что позволяет придать согласованный вид элементам управления приложения.

Подробнее см. в статье [Объединенные словари ресурсов](../../framework/wpf/advanced/merged-resource-dictionaries.md).

Если вы создаете тему для пользовательского элемента управления, ознакомьтесь с разделом **Определение ресурсов на уровне темы** в статье [Общие сведения о разработке элементов управления](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level).

## <a name="see-also"></a>См. также

- [URI типа "pack" в WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [Практическое руководство. Поиск элемента, созданного шаблоном ControlTemplate](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Поиск элементов, созданных с использованием шаблона DataTemplate](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
