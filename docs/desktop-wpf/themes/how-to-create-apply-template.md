---
title: Создание шаблона в WPF - .NET Desktop
description: Узнайте, как создать и ссылку на шаблон управления в Windows Presentation Foundation и .NET Core.
author: thraka
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
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432542"
---
# <a name="create-a-template-for-a-control"></a>Создание шаблона для управления

С помощью Фонда презентации Windows (WPF) вы можете настроить визуальную структуру и поведение существующего элемента управления с помощью собственного многоразового шаблона. Шаблоны могут быть применены по всему миру к вашему приложению, окнам и страницам или непосредственно к элементам управления. Большинство сценариев, требующих создания нового элемента управления, могут быть охвачены вместо этого созданием нового шаблона для существующего элемента управления.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

В этой статье вы исследуете создание нового <xref:System.Windows.Controls.ControlTemplate> элемента <xref:System.Windows.Controls.Button> управления.

## <a name="when-to-create-a-controltemplate"></a>Когда создавать ControlTemplate

Элементы управления имеют <xref:System.Windows.Controls.Border.Background%2A>множество <xref:System.Windows.Controls.Control.Foreground%2A>свойств, таких как , и <xref:System.Windows.Controls.Control.FontFamily%2A>. Эти свойства управляют различными аспектами внешнего вида элемента управления, но изменения, которые можно внести, установив эти свойства, ограничены. Например, можно установить <xref:System.Windows.Controls.Control.Foreground%2A> свойство <xref:System.Windows.Controls.Control.FontStyle%2A> на синий <xref:System.Windows.Controls.CheckBox>и курсивна на . Если вы хотите настроить внешний вид элемента управления сверх того, что может <xref:System.Windows.Controls.ControlTemplate>сделать установка других свойств на элементе управления, создается.

В большинстве пользовательских интерфейсов кнопка имеет тот же общий внешний вид: прямоугольник с некоторым текстом. Если вы хотите создать закруглена кнопка, вы можете создать новый элемент управления, который наследует от кнопки или воссоздает функциональность кнопки. Кроме того, новый пользовательский контроль обеспечит круговой визуальный эффект.

Вы можете избежать создания новых элементов управления, настроив визуальную компоновку существующего элемента управления. С закругленной кнопкой, вы создаете <xref:System.Windows.Controls.ControlTemplate> с желаемой визуальной компоновкой.

С другой стороны, если вам нужен элемент управления с новой функциональностью, различными свойствами и новыми настройками, вы создадите новый <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Предварительные требования

Создайте новое приложение WPF и в *MainWindow.xaml* (или другом окне по вашему выбору) установите следующие свойства на элементе ** \<window>:**

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

Установите содержимое ** \<** элемента Window>на следующее XAML:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

В конце концов, файл *MainWindow.xaml* должен выглядеть так же, как и следующее:

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Если вы запустите приложение, оно выглядит следующим образом:

![Окно WPF с двумя нестилейными кнопками](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Создание шаблона ControlTemplate

Наиболее распространенный <xref:System.Windows.Controls.ControlTemplate> способ декларировать `Resources` является ресурсом в разделе в файле XAML. Поскольку шаблоны являются ресурсами, они подчиняются тем же правилам отслеживания, которые применяются ко всем ресурсам. Проще говоря, если вы объявите шаблон влияет, где шаблон может быть применен. Например, если вы объявите шаблон в корневом элементе файла XAML- приложения, шаблон можно использовать в любом месте приложения. Если вы определяете шаблон в окне, только элементы управления в этом окне могут использовать шаблон.

Для начала добавьте `Window.Resources` элемент в файл *MainWindow.xaml:*

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Создайте новую ** \<>ControlTemplate** со следующим набором свойств:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Этот шаблон управления будет прост:

- корневой элемент для управления,<xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Shapes.Ellipse> чтобы нарисовать округлые внешний вид кнопки
- для <xref:System.Windows.Controls.ContentPresenter> отображения заданного пользователем кнопок

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

При создании нового, <xref:System.Windows.Controls.ControlTemplate>вы все еще можете использовать общедоступные свойства для изменения внешнего вида элемента управления. Расширение разметки [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) связывает свойство элемента, напавающего в <xref:System.Windows.Controls.ControlTemplate> государственную собственность, определяемую контролем. При использовании [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)вы позволяете свойствам элемента управления действовать в качестве параметров шаблона. Это означает, что при задании свойства элемента управления соответствующее значение передается в элемент, который содержит [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).

### <a name="ellipse"></a>Эллипс

Обратите **:::no-loc text="Fill":::** внимание, **:::no-loc text="Stroke":::** что свойства <xref:System.Windows.Controls.Control.Foreground> ** \<элемента Ellipse>** связаны <xref:System.Windows.Controls.Control.Background> с элементами управления и свойствами.

### <a name="contentpresenter"></a>ContentPresenter

В шаблон также добавляется элемент [ \<ContentPresenter>.](xref:System.Windows.Controls.ContentPresenter) Поскольку этот шаблон предназначен для кнопки, примите <xref:System.Windows.Controls.ContentControl>во внимание, что кнопка наследует от . Кнопка представляет содержимое элемента. Вы можете установить что-нибудь внутри кнопки, например, простой текст или даже другой элемент управления. Оба из них являются действительными кнопками:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

В обоих предыдущих примерах текст и флажок устанавливаются как свойство [Button.Content.](xref:System.Windows.Controls.ContentControl.Content) Все, что устанавливается как содержание может быть представленчерез через ** \<ContentPresenter>**, который является то, что шаблон делает.

Если <xref:System.Windows.Controls.ControlTemplate> применяется к <xref:System.Windows.Controls.ContentControl> типу, `Button`например, a, <xref:System.Windows.Controls.ContentPresenter> поиск в дереве элемента. При `ContentPresenter` обнаружении шаблон автоматически связывает свойство <xref:System.Windows.Controls.ContentControl.Content> элемента `ContentPresenter`управления с .

## <a name="use-the-template"></a>Использовать шаблон

Найдите кнопки, которые были объявлены в начале этой статьи.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Установите свойство <xref:System.Windows.Controls.Control.Template> второй кнопки на `roundbutton` ресурс:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Если вы запустите проект и посмотрите на результат, вы увидите, что кнопка имеет закругленный фон.

![Окно WPF с одной овальной кнопкой шаблона](media/create-apply-template/styled-button.png)

Возможно, вы заметили, что кнопка не круг, но перекос. Из-за того, как работает элемент ** \<Ellipse>,** он всегда расширяется, чтобы заполнить доступное пространство. Сделайте круг равномерным, **:::no-loc text="width":::** изменив кнопку и **:::no-loc text="height":::** свойства на одно и то же значение:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Окно WPF с одной круговой кнопкой шаблона](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Добавить триггер

Несмотря на то, что кнопка с прикладным шаблоном выглядит по-другому, она ведет себя так же, как и любая другая кнопка. Если вы нажмете на кнопку, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие срастанет. Тем не менее, вы могли заметить, что при перемещении мыши по кнопке визуальные эффекты кнопки не меняются. Все эти визуальные взаимодействия определяются шаблоном.

С помощью динамических систем событий и свойств, которые предоставляет WPF, вы можете посмотреть определенное свойство для значения, а затем рестайлинг шаблона, когда это необходимо. В этом примере вы будете наблюдать <xref:System.Windows.UIElement.IsMouseOver> за свойством кнопки. Когда мышь над управлением, стиль ** \<Ellipse>** с новым цветом. Этот тип триггера известен как *PropertyTrigger.*

Для того, чтобы это сработало, необходимо добавить имя в ** \<>,** на которую вы можете ссылаться. Дайте ему название **backgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

Затем добавьте <xref:System.Windows.Trigger> новую коллекцию [ControlTemplate.Triggers.](xref:System.Windows.Controls.ControlTemplate.Triggers) Триггер будет наблюдать `IsMouseOver` за событием для значения. `true`

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

Затем добавьте ** \<>сеттера** в ** \<>триггера,** которая изменяет свойство **заполнения** ** \<>На** новый цвет.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Запустите проект. Обратите внимание, что при перемещении мыши по кнопке цвет ** \<Ellipse>** изменяется.

![мышь перемещается по кнопке WPF, чтобы изменить цвет заполнения](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Использование VisualState

Визуальные состояния определяются и запускаются элементом управления. Например, когда мышь перемещается поверх элемента управления, `CommonStates.MouseOver` срабатывает состояние. Вы можете анимировать изменения свойств в зависимости от текущего состояния элемента управления. В предыдущем разделе ** \<>PropertyTrigger** использовался для изменения переднего `AliceBlue` плана `IsMouseOver` кнопки `true`на время, когда свойство было . Вместо этого создайте визуальное состояние, которое оживляет изменение этого цвета, обеспечивая плавный переход. Для получения дополнительной информации о *VisualStates*, [см.](../fundamentals/styles-templates-overview.md#visual-states)

Чтобы преобразовать ** \<>PropertyTrigger** в анимированное визуальное состояние, во-первых, удалите ** \<элемент ControlTemplate.Triggers>** элемент из шаблона.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

Далее, в ** \<сетке>** корень шаблона управления, добавить ** \<VisualStateManager.VisualStateGroups>** элемент с ** \<VisualStateGroup>** для `CommonStates`. Определите два `Normal` `MouseOver`состояния, и .

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Любые анимации, ** \<** определенные в>VisualState, применяются при срабатывании этого состояния. Создавайте анимации для каждого состояния. Анимации помещаются внутри ** \<раскадровки>** элементом. Для получения дополнительной информации о раскадровки, см [Storyboards Обзор](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

- Нормальный

  Это состояние оживляет заливку эллипса, восстанавливая его в `Background` цвете управления.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Это состояние оживляет `Background` цвет эллипса `Yellow`к новому цвету: .

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

** \<>ControlTemplate** теперь должен выглядеть следующим образом.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Запустите проект. Обратите внимание, что при перемещении мыши по кнопке цвет ** \<Эллипса>** оживляет.

![мышь перемещается по кнопке WPF, чтобы изменить цвет заполнения](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Следующие шаги

- [Создание стиля для управления в WPF](../fundamentals/styles-templates-create-apply-style.md)
- [Стили и шаблоны в WPF](../fundamentals/styles-templates-overview.md)
- [Обзор ресурсов XAML](../fundamentals/xaml-resources-define.md)
