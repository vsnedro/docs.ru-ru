---
title: Создание шаблона в WPF — рабочий стол .NET
description: Узнайте, как создать шаблон элемента управления и ссылаться на него в Windows Presentation Foundation и .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c372659676b450cde789c96e45c7ec5de2aea194
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325723"
---
# <a name="create-a-template-for-a-control"></a>Создание шаблона элемента управления

В Windows Presentation Foundation (WPF) можно настраивать визуальную структуру и функциональные возможности существующего элемента управления с помощью своего собственного шаблона многократного использования. Шаблоны можно применять глобально ко всему приложению, отдельным окнам и страницам или непосредственно к элементам управления. Большинство сценариев, в которых требуется создать новый элемент управления, можно реализовать, создав вместо этого новый шаблон для существующего элемента управления.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

В этой статье будет показано, как создать новый шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button>.

## <a name="when-to-create-a-controltemplate"></a>Когда следует создавать ControlTemplate

Элементы управления имеют много свойств, таких, например, как <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontFamily%2A>. Эти свойства управляют различными аспектами внешнего вида элемента управления, но с помощью них можно внести не так много изменений. Например, для элемента управления <xref:System.Windows.Controls.CheckBox> можно задать синий цвет фона с помощью свойства <xref:System.Windows.Controls.Control.Foreground%2A> и курсив с помощью свойства <xref:System.Windows.Controls.Control.FontStyle%2A>. Если вы хотите внести такие изменения внешнего вида элемента управления, которые не предусмотрены его свойствами, можно создать шаблон <xref:System.Windows.Controls.ControlTemplate>.

В большинстве пользовательских интерфейсов кнопка обычно выглядит как прямоугольник с текстом. Если вы хотите создать круглую кнопку, можно создать новый элемент управления, который наследует от кнопки или воссоздает функциональность кнопки. И вдобавок этот новый пользовательский элемент управления будет иметь круглую форму.

Вы можете не создавать новые элементы управления, а просто настроить визуальный макет существующего элемента управления. Например, для круглой кнопки можно создать шаблон <xref:System.Windows.Controls.ControlTemplate> с желаемым визуальным макетом.

С другой стороны, если вам нужен элемент управления с новыми функциями, другими свойствами и новыми параметрами, лучше создать новый <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Предварительные требования

Создайте новое приложение WPF и в окне *MainWindow.xaml* (или другом окне по вашему выбору) установите следующие свойства элемента **\<Window>** :

|     |     |
| --- | --- |
| **Title**         | `Template Intro Sample` |
| **SizeToContent** | `WidthAndHeight` |
| **MinWidth**      | `250` |

В качестве содержимого элемента **\<Window>** задайте следующий код XAML:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

В итоге файл *MainWindow.xaml* должен выглядеть следующим образом.

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Если запустить приложение, оно будет выглядеть так.

![Окно WPF с двумя кнопками без стиля](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Создание шаблона ControlTemplate

Чаще всего <xref:System.Windows.Controls.ControlTemplate> объявляется как ресурс в разделе `Resources` файла XAML. Так как шаблоны являются ресурсами, для них действуют те же правила определения области, что и для всех других ресурсов. Проще говоря, то, где вы объявляете шаблон, влияет на то, где этот шаблон может быть применен. Например, если вы объявите шаблон в корневом элементе XAML-файла определения приложения, этот шаблон можно будет использовать в любом месте вашего приложения. Если вы определяете шаблон в окне, его смогут использовать только элементы управления из этого окна.

Для начала добавьте элемент `Window.Resources` в свой файл *MainWindow.xaml*:

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Создайте новый **\<ControlTemplate>** со следующими свойствами:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Этот шаблон элемента управления будет простым:

- корневой элемент этого элемента управления, <xref:System.Windows.Controls.Grid>;
- <xref:System.Windows.Shapes.Ellipse>, чтобы кнопка отображалась круглой;
- <xref:System.Windows.Controls.ContentPresenter> для вывода указанного пользователем содержимого кнопки.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

Создавая новый шаблон <xref:System.Windows.Controls.ControlTemplate>, вы можете захотеть использовать общие свойства для изменения внешнего вида элемента управления. Расширение разметки [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) привязывает свойство элемента из шаблона <xref:System.Windows.Controls.ControlTemplate> к общему свойству, которое задается элементом управления. При использовании расширения [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) свойства элемента управления могут действовать в качестве параметров шаблона. Это означает, что при задании свойства элемента управления соответствующее значение передается в элемент, который содержит [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).

### <a name="ellipse"></a>Ellipse

Обратите внимание, что свойства **:::no-loc text="Fill":::** и **:::no-loc text="Stroke":::** элемента **\<Ellipse>** связаны со свойствами <xref:System.Windows.Controls.Control.Foreground> и <xref:System.Windows.Controls.Control.Background>.

### <a name="contentpresenter"></a>ContentPresenter

Элемент [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) также добавляется в шаблон. Так как этот шаблон предназначен для кнопки, необходимо учитывать, что эта кнопка наследует от <xref:System.Windows.Controls.ContentControl>. Кнопка представляет содержимое элемента. Можно задать что-либо внутри кнопки, например обычный текст или даже другой элемент управления. Оба следующих варианта — правильные кнопки:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

В обоих приведенных выше примерах текст и флажок задаются как свойство [Button.Content](xref:System.Windows.Controls.ContentControl.Content). Данные, указываемые в качестве содержимого, могут быть представлены с помощью **\<ContentPresenter>**  — именно эту задачу выполняет шаблон.

Если <xref:System.Windows.Controls.ControlTemplate> применяется к типу <xref:System.Windows.Controls.ContentControl>, такому как `Button`, выполняется поиск <xref:System.Windows.Controls.ContentPresenter> в дереве элементов. Если `ContentPresenter` обнаруживается, шаблон автоматически привязывает свойство <xref:System.Windows.Controls.ContentControl.Content> элемента управления к элементу `ContentPresenter`.

## <a name="use-the-template"></a>Использовать шаблон

Найдите кнопки, которые были объявлены в начале этой статьи.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Задайте в свойстве <xref:System.Windows.Controls.Control.Template> второй кнопки ресурс `roundbutton`:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Если теперь вы запустите проект и посмотрите на результат, то фон кнопки будет иметь овальную форму.

![Окно WPF с одной овальной кнопкой](media/create-apply-template/styled-button.png)

Вы, конечно, заметили, что кнопка не круглая, а вытянутая. Именно так работает элемент **\<Ellipse>**  — он всегда растягивается, чтобы заполнить доступное пространство. Сделайте кнопку круглой, задав в свойствах **:::no-loc text="width":::** и **:::no-loc text="height":::** одно и то же значение:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Окно WPF с одной круглой кнопкой](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Добавление триггера

Хотя кнопка с примененным шаблоном выглядит иначе, она ведет себя так же, как и любая другая кнопка. При нажатии кнопки срабатывает событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. Однако, как вы могли заметить, при наведении указателя мыши на кнопку визуально ничего не меняется. Все визуальные взаимодействия определяются шаблоном.

В системах динамических событий и свойств, предоставляемых WPF, можно отслеживать значение конкретного свойства, а затем при необходимости изменять стиль шаблона. В данном примере вы будете отслеживать свойство <xref:System.Windows.UIElement.IsMouseOver> кнопки. Задайте новый цвет для элемента **\<Ellipse>** , который должен отображаться, когда указатель мыши наводится на элемент управления. Триггер такого типа называется *PropertyTrigger*.

Чтобы этот триггер сработал, необходимо добавить в **\<Ellipse>** имя, на которое можно ссылаться. Задайте имя **backgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

Затем добавьте новый <xref:System.Windows.Trigger> в коллекцию [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers). Этот триггер будет отслеживать, когда событие `IsMouseOver` принимает значение `true`.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

Затем добавьте в **\<Setter>** метод **\<Trigger>** , который изменяет цвет в свойстве **Fill** элемента **\<Ellipse>** на новый цвет.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Запустите проект. Обратите внимание, что при наведении мыши на кнопку цвет **\<Ellipse>** изменяется.

![При наведении мыши на кнопку WPF цвет заливки изменяется](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Использование VisualState

Визуальные состояния определяются и активируются элементом управления. Например, при наведении указателя мыши на элемент управления активируется состояние `CommonStates.MouseOver`. Изменения свойств можно анимировать на основе текущего состояния элемента управления. В предыдущем разделе с помощью **\<PropertyTrigger>** фон кнопки изменялся на `AliceBlue`, когда свойство `IsMouseOver` получало значение `true`. Теперь вместо этого создайте визуальное состояние, которое анимирует изменение этого цвета, обеспечивая плавный переход. Дополнительные сведения об элементе *VisualStates* см. в разделе [Стили и шаблоны в WPF](../fundamentals/styles-templates-overview.md#visual-states).

Чтобы преобразовать **\<PropertyTrigger>** в анимированное визуальное состояние, сначала удалите элемент **\<ControlTemplate.Triggers>** из вашего шаблона.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

Затем необходимо добавить в корень шаблона элемента управления **\<Grid>** элемент **\<VisualStateManager.VisualStateGroups>** со значением **\<VisualStateGroup>** для `CommonStates`. Определите два состояния — `Normal` и `MouseOver`.

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Все анимации, определенные в **\<VisualState>** , применяются при активации соответствующего состояния. Создайте анимации для каждого состояния. Анимации помещаются в элемент **\<Storyboard>** . Дополнительные сведения о раскадровках см. в статье [Общие сведения о Storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

- Норм.

  Это состояние анимирует заливку эллипса, восстанавливающую цвет `Background` элемента управления.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Это состояние анимирует изменение цвета `Background` эллипса на новый цвет: `Yellow`.

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

**\<ControlTemplate>** будет иметь следующий вид.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Запустите проект. Обратите внимание, что при наведении мыши на кнопку цвет **\<Ellipse>** анимируется.

![При наведении мыши на кнопку WPF цвет заливки изменяется](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Следующие шаги

- [Создание стиля элемента управления в WPF](../fundamentals/styles-templates-create-apply-style.md)
- [Стили и шаблоны в WPF](../fundamentals/styles-templates-overview.md)
- [Обзор ресурсов XAML](../fundamentals/xaml-resources-define.md)
