---
title: Создание стиля элемента управления
description: Узнайте, как создать стиль элемента управления, а также ссылку на него в Windows Presentation Foundation и .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: de186cd6da83ffef8a5cd59df581e88b24bc474d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325792"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Создание стиля элемента управления в WPF

В Windows Presentation Foundation (WPF) можно настраивать внешний вид элемента управления, используя собственный перенастраиваемый стиль. Стили можно применять глобально ко всему приложению, отдельным окнам и страницам или непосредственно к элементам управления.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Создание стиля

<xref:System.Windows.Style> обеспечивает удобный способ применения набора значений свойств к одному или нескольким элементам. Стиль можно использовать для любого элемента, производного от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, например <xref:System.Windows.Window> или <xref:System.Windows.Controls.Button>.

Чаще всего стиль объявляется как ресурс в разделе `Resources` файла XAML. Так как стили являются ресурсами, для них действуют те же правила определения области, что и для всех других ресурсов. Проще говоря, то, где вы объявляете стиль, влияет на то, где этот стиль может быть применен. Например, если объявить стиль в корневом элементе файла XAML определения приложения, стиль может использоваться в любом месте приложения.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Стиль, объявленный в одном из файлов XAML приложения, можно использовать только в этом файле XAML. Подробнее о правилах видимости ресурсов см. в разделе [Ресурсы XAML](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Стиль состоит из дочерних элементов `<Setter>`, которые задают свойства для элементов, к которым применяется стиль. Обратите внимание, что в приведенном выше примере стиль настроен на применение к типам `TextBlock` с использованием атрибута `TargetType`. Стиль задаст `15` для <xref:System.Windows.Controls.Control.FontSize%2A> и `ExtraBold` для <xref:System.Windows.Controls.Control.FontWeight%2A>. Добавьте `<Setter>` для каждого свойства, которое изменяет стиль.

## <a name="apply-a-style-implicitly"></a>Неявное применение стиля

<xref:System.Windows.Style> обеспечивает удобный способ применения набора значений свойств к нескольким элементам. Рассмотрим, к примеру, следующие элементы <xref:System.Windows.Controls.TextBlock> и их внешний вид по умолчанию в окне.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Снимок экрана: пример стилизации](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

Внешний вид по умолчанию можно изменить, задав такие свойства, как <xref:System.Windows.Controls.Control.FontSize%2A> и <xref:System.Windows.Controls.Control.FontFamily%2A>, непосредственно в каждом элементе <xref:System.Windows.Controls.TextBlock>. Но если вы хотите, чтобы элементы <xref:System.Windows.Controls.TextBlock> могли совместно использовать некоторые свойства, можно создать <xref:System.Windows.Style> в разделе `Resources` файла XAML, как показано ниже.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

Если вы задаете стилю <xref:System.Windows.Style.TargetType%2A> для типа <xref:System.Windows.Controls.TextBlock> и опускаете атрибут `x:Key`, стиль применяется ко всем элементам <xref:System.Windows.Controls.TextBlock>, областью действия которых является стиль, представленный по сути файлом XAML.

Теперь элементы <xref:System.Windows.Controls.TextBlock> выглядят следующим образом.

![Снимок экрана: пример стилизации](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Явное применение стиля

Если вы добавляете в стиль атрибут `x:Key` со значением, стиль больше не будет неявно применяться ко всем элементам <xref:System.Windows.Style.TargetType%2A>. Стиль будет применяться только к тем элементам, которые явно ссылаются на него.

Ниже приведен стиль из предыдущего раздела, который объявлен с атрибутом `x:Key`.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Чтобы применить этот стиль, задайте для свойства элемента <xref:System.Windows.FrameworkElement.Style%2A> значение `x:Key`, используя расширение разметки [StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md), как показано ниже.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Обратите внимание, что стиль применен к первому элементу <xref:System.Windows.Controls.TextBlock>, а второй элемент TextBlock остается неизменным. Неявный стиль из предыдущего раздела был изменен на стиль, объявляющий атрибут `x:Key`. То есть единственный элемент, затронутый стилем, — это тот, который непосредственно ссылался на стиль.

![Снимок экрана: пример стилизации](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "create-a-style-explicit-textblock")

Явно или неявно примененный стиль становится запечатанным и не подлежит изменению. Чтобы динамически изменить стиль, который уже был применен, нужно создать новый стиль, который заменит существующий. Дополнительные сведения см. в описании свойства <xref:System.Windows.Style.IsSealed%2A>.

Можно создать объект, который выбирает стиль, который нужно применить, основываясь на собственной логике. Ознакомьтесь с примером для класса <xref:System.Windows.Controls.StyleSelector>.

## <a name="apply-a-style-programmatically"></a>Применение стиля программным способом

Чтобы назначить именованный стиль элементу программным способом, возьмите стиль из коллекции ресурсов и присвойте его свойству <xref:System.Windows.FrameworkElement.Style%2A> этого элемента. Обратите внимание, что элементы в коллекции ресурсов имеют тип <xref:System.Object>. Поэтому полученный стиль необходимо привести к <xref:System.Windows.Style?displayProperty=fullName>, прежде чем назначать его свойству `Style`. Например, следующий код задает стиль `TextBlock` с именем `textblock1` определенному стилю `TitleText`.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Расширение стиля

Возможно, вы хотите, чтобы два элемента <xref:System.Windows.Controls.TextBlock> совместно использовали некоторые значения свойств, такие как <xref:System.Windows.Controls.Control.FontFamily%2A> и <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> с выравниванием по центру. При этом текст **Мои рисунки** должен иметь некоторые дополнительные свойства. Это можно сделать, создав новый стиль на основе первого стиля, как показано ниже.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Теперь этот стиль `TextBlock` выравнивается по центру, а также использует шрифт `Comic Sans MS` с размером `26` и цвет переднего плана <xref:System.Windows.Media.LinearGradientBrush>, как показано в примере. Обратите внимание, что значение <xref:System.Windows.Controls.Control.FontSize%2A> базового стиля переопределено. Если несколько <xref:System.Windows.Setter> указывают на одно и то же свойство в <xref:System.Windows.Style>, приоритет имеет свойство `Setter`, объявленное последним.

Ниже показано, как будут выглядеть элементы <xref:System.Windows.Controls.TextBlock>.

![TextBlock со стилизацией](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Стиль `TitleText` расширяет стиль, который был создан для типа <xref:System.Windows.Controls.TextBlock>, на который ссылается `BasedOn="{StaticResource {x:Type TextBlock}}"`. Вы также можете расширить стиль с `x:Key`, используя `x:Key` стиля. Например, если существовал стиль с именем `Header1`, который вы хотите расширить, используйте `BasedOn="{StaticResource Header1}"`.

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Связь между свойством TargetType и атрибутом x:Key

Как было показано выше, присвоив свойству <xref:System.Windows.Style.TargetType%2A> значения `TextBlock` без назначения стиля `x:Key`, вы примените стиль ко всем элементам <xref:System.Windows.Controls.TextBlock>. В этом случае для `x:Key` неявно устанавливается значение `{x:Type TextBlock}`. Это означает, что при явном присвоении `x:Key` значения, отличающегося от `{x:Type TextBlock}`, <xref:System.Windows.Style> не применяется ко всем элементам `TextBlock` автоматически. Вместо этого необходимо явным образом применить стиль (используя значение `x:Key`) ко всем элементам `TextBlock`. Если стиль находится в разделе ресурсов и вы не задаете для стиля свойство `TargetType`, задайте атрибут `x:Key`.

Свойство `TargetType` не только предоставляет значение по умолчанию для `x:Key`, но и указывает тип, к которому применяются свойства метода задания. Если вы не указываете `TargetType`, необходимо определите свойства в объектах <xref:System.Windows.Setter>, используя имя класса и синтаксис `Property="ClassName.Property"`. Например, вместо установки `Property="FontSize"` необходимо задать для <xref:System.Windows.Setter.Property%2A> значение `"TextBlock.FontSize"` или `"Control.FontSize"`.

Также обратите внимание, что многие элементы управления WPF состоят из других элементов управления WPF. Если создать стиль, который применяется ко всем элементам управления типа, можно получить непредвиденные результаты. Например, если вы создаете стиль, предназначенный для типа <xref:System.Windows.Controls.TextBlock> в <xref:System.Windows.Window>, этот стиль будет применен ко всем элементам управления `TextBlock` в окне, даже если `TextBlock` является частью другого элемента управления, например <xref:System.Windows.Controls.ListBox>.

## <a name="see-also"></a>См. также

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Общие сведения о ресурсах XAML](xaml-resources-define.md)
- [Обзор XAML (WPF и .NET Core)](xaml.md)
