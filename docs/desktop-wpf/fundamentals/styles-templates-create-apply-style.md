---
title: Создание стиля для управления
description: Узнайте, как создать и привести стиль управления в Фонд епредставления Windows и .NET Core.
author: thraka
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2956dbf93a1d34feca31d3ab10536f5089010189
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "81432560"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Создание стиля для управления в WPF

С Windows Presentation Foundation (WPF) вы можете настроить внешний вид существующего элемента управления с помощью собственного многоразового стиля. Стили могут быть применены глобально к вашему приложению, окнам и страницам или непосредственно к элементам управления.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Создание стиля

Можно подумать <xref:System.Windows.Style> о удобном способе применить набор значений свойств к одному или несколько элементам. Вы можете использовать стиль на любом <xref:System.Windows.FrameworkElement> элементе, который <xref:System.Windows.Controls.Button>вытекает из или, <xref:System.Windows.FrameworkContentElement> например, <xref:System.Windows.Window> или .

Наиболее распространенным способом объявления стиля является `Resources` ресурс в разделе в файле XAML. Поскольку стили являются ресурсами, они подчиняются тем же правилам отслеживания, которые применяются ко всем ресурсам. Проще говоря, если вы объявите стиль влияет, где стиль может быть применен. Например, если вы объявляете стиль в корневом элементе файла XAML определения приложения, стиль можно использовать в любом месте вашего приложения.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Если вы объявите стиль в одном из файлов XAML приложения, стиль можно использовать только в этом файле XAML. Подробнее о правилах видимости ресурсов см. в разделе [Ресурсы XAML](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Стиль состоит из `<Setter>` элементов ребенка, которые устанавливают свойства на элементы, к которым применяется стиль. В приведенном выше примере обратите внимание, `TextBlock` что `TargetType` стиль настроен на типы через атрибут. Стиль установит к <xref:System.Windows.Controls.Control.FontSize%2A> `15` и <xref:System.Windows.Controls.Control.FontWeight%2A> к `ExtraBold`. Добавьте `<Setter>` для каждого свойства изменения стиля.

## <a name="apply-a-style-implicitly"></a>Применить стиль неявно

A <xref:System.Windows.Style> — это удобный способ применить набор значений свойств к более чем одному элементу. Например, рассмотрим <xref:System.Windows.Controls.TextBlock> следующие элементы и их появление по умолчанию в окне.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Укладка образца скриншот](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

Внешний вид по умолчанию можно <xref:System.Windows.Controls.Control.FontSize%2A> изменить, установив свойства, такие как и <xref:System.Windows.Controls.Control.FontFamily%2A>непосредственно на каждом <xref:System.Windows.Controls.TextBlock> элементе. Однако, если <xref:System.Windows.Controls.TextBlock> вы хотите, чтобы элементы <xref:System.Windows.Style> делились `Resources` некоторыми свойствами, можно создать раздел файла XAML, как показано здесь.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

При настройке <xref:System.Windows.Style.TargetType%2A> вашего стиля <xref:System.Windows.Controls.TextBlock> к типу `x:Key` и опускании <xref:System.Windows.Controls.TextBlock> атрибута стиль применяется ко всем элементам, применяемым к стилю, который, как правило, сам файл XAML.

Теперь <xref:System.Windows.Controls.TextBlock> элементы отображаются следующим образом.

![Укладка образца скриншот](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Применить стиль явно

Если добавить `x:Key` атрибут со значением к стилю, стиль больше не <xref:System.Windows.Style.TargetType%2A>будет неявно применяться ко всем элементам . Только элементы, которые явно ссылаются на стиль, будут иметь стиль, применяемый к ним.

Вот стиль из предыдущего раздела, `x:Key` но заявлен с атрибутом.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Чтобы применить стиль, <xref:System.Windows.FrameworkElement.Style%2A> установите свойство `x:Key` на элементе к значению, используя [расширение разметки StaticResource,](../../framework/wpf/advanced/staticresource-markup-extension.md)как показано здесь.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Обратите внимание, <xref:System.Windows.Controls.TextBlock> что первый элемент имеет стиль, применяемый к нему, в то время как второй элемент TextBlock остается неизменным. Неявный стиль из предыдущего раздела `x:Key` был изменен на стиль, который объявил атрибут, то есть, единственным элементом, на который повлиял стиль, является тот, который напрямую ссылается на стиль.

![Укладка образца скриншот](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "создать-стиль-явный-текстовый блок")

Как только стиль применяется, явно или неявно, он запечатывается и не может быть изменен. Если вы хотите изменить применяемый стиль, создайте новый стиль, который заменит существующий. Дополнительные сведения см. в описании свойства <xref:System.Windows.Style.IsSealed%2A>.

Можно создать объект, который выбирает стиль, который нужно применить, основываясь на собственной логике. Например, см. пример, <xref:System.Windows.Controls.StyleSelector> предоставленный для класса.

## <a name="apply-a-style-programmatically"></a>Применение стиля программно

Чтобы присвоить именный стиль элементу программно, получите стиль из коллекции ресурсов <xref:System.Windows.FrameworkElement.Style%2A> и присвоите его свойству элемента. Элементы в коллекции ресурсов <xref:System.Object>имеют тип. Таким образом, необходимо отбросить извлеченный стиль <xref:System.Windows.Style?displayProperty=fullName> на `Style` свойство, прежде чем присвоить его свойству. Например, следующий код определяет `TextBlock` стиль `textblock1` имени в `TitleText`определенном стиле.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Расширить стиль

Возможно, вы <xref:System.Windows.Controls.TextBlock> хотите, чтобы ваши два элемента <xref:System.Windows.Controls.Control.FontFamily%2A> разделяли <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>некоторые значения свойств, такие как и по центру . Но вы также хотите, чтобы текст **My Pictures** иметь некоторые дополнительные свойства. Вы можете сделать это, создав новый стиль, который основан на первом стиле, как показано здесь.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Этот `TextBlock` стиль теперь центрируется, использует `Comic Sans MS` `26`шрифт с размером, и <xref:System.Windows.Media.LinearGradientBrush> цвет переднего плана установлен на показанный в примере. Обратите внимание, что <xref:System.Windows.Controls.Control.FontSize%2A> он переопределяет значение базового стиля. Если есть более чем <xref:System.Windows.Setter> один указывая на <xref:System.Windows.Style>то `Setter` же свойство в , что объявлено последнего имеет приоритет.

Ниже показано, <xref:System.Windows.Controls.TextBlock> как теперь выглядят элементы:

![Стилизированный TextBlocks](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Этот `TitleText` стиль расширяет стиль, созданный <xref:System.Windows.Controls.TextBlock> для типа, `BasedOn="{StaticResource {x:Type TextBlock}}"`на который ссылаются. Вы также можете расширить стиль, который имеет `x:Key` с помощью `x:Key` стиля. Например, если есть стиль `Header1` с именем, и вы `BasedOn="{StaticResource Header1}"`хотите расширить этот стиль, вы будете использовать .

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Связь свойства TargetType и атрибута x:Key

Как показано ранее, <xref:System.Windows.Style.TargetType%2A> установка `TextBlock` свойства без присвоения стиля `x:Key` приводит к <xref:System.Windows.Controls.TextBlock> тому, что стиль применяется ко всем элементам. В этом случае для `x:Key` неявно устанавливается значение `{x:Type TextBlock}`. Это означает, что если `x:Key` вы явно установите значение для чего-либо, кроме, `{x:Type TextBlock}` <xref:System.Windows.Style> не применяется ко всем `TextBlock` элементам автоматически. Вместо этого необходимо применить стиль (используя `x:Key` значение) `TextBlock` к элементам явно. Если ваш стиль находится в разделе ресурсов, `TargetType` и вы не установите свойство на ваш стиль, то вы должны установить `x:Key` атрибут.

В дополнение к предоставлению `x:Key`значения `TargetType` по умолчанию для, свойство определяет тип, к которому применяются свойства сеттера. Если вы не указали, `TargetType`вы должны квалифицировать <xref:System.Windows.Setter> свойства в ваших объектах `Property="ClassName.Property"`с именем класса с помощью синтаксиса. Например, вместо `Property="FontSize"`установки необходимо <xref:System.Windows.Setter.Property%2A> `"TextBlock.FontSize"` установить или. `"Control.FontSize"`

Следует также отметить, что многие элементы контроля WPF состоят из комбинации других элементов контроля WPF. Если создать стиль, который применяется ко всем элементам управления типа, можно получить непредвиденные результаты. Например, если вы создаете <xref:System.Windows.Controls.TextBlock> стиль, <xref:System.Windows.Window>нацеленный на тип `TextBlock` в окне, то `TextBlock` стиль применяется ко всем <xref:System.Windows.Controls.ListBox>элементам управления в окне, даже если он является частью другого элемента управления, например.

## <a name="see-also"></a>См. также

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Обзор ресурсов XAML](xaml-resources-define.md)
- [Обзор XAML (WPF & .NET Core)](xaml.md)
