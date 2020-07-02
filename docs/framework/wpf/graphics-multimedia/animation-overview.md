---
title: Общие сведения об эффектах анимации
description: Сделайте привлекательный пользовательский интерфейс еще более впечатляющая с помощью значительных переходов на экран или ярких визуальных подсказок в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: d761be0c95fb8aa7eb39cb26b57979185226b8fb
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853857"
---
# <a name="animation-overview"></a>Общие сведения об эффектах анимации

В <a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] представлен полный набор функций для работы с графикой и макетом, позволяющих создавать привлекательные пользовательские интерфейсы и документы. Применение анимации позволяет сделать пользовательский интерфейс еще более наглядным и удобным в использовании. Просто анимировать цвет фона или применить анимацию <xref:System.Windows.Media.Transform> , вы можете создавать значительные переходы экрана или предоставлять полезные визуальные подсказки.

В этом обзоре содержатся общие сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации и системе управления временем. Он посвящен анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектов с помощью раскадровок.

<a name="introducinganimations"></a>

## <a name="introducing-animations"></a>Введение в анимацию

Анимация — это имитация изменений, которая обеспечивается быстрым показом серии слегка отличающихся друг от друга изображений. Мозг человека воспринимает набор изображений как одну непрерывно изменяющуюся картинку. В фильме эта имитация создается за счет применения камер, записывающих множество фотографий (кадров) в секунду. При воспроизведении кадров проектором зрители видят движущееся изображение.

Анимация на компьютере выполняется по аналогичному принципу. Например, программа, в которой реализуется исчезновение прямоугольника, может работать следующим образом.

- В программе создается таймер.

- Через заданные временные интервалы проверяется значение таймера для определения истекшего времени.

- При каждой проверке значения таймера вычисляется текущее значение непрозрачности для прямоугольника в зависимости от прошедшего времени.

- Затем программа обновляет прямоугольник с использованием нового значения и перерисовывает его.

Перед тем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , как разработчикам Microsoft Windows пришлось создавать собственные системы управления временем и управлять ими, а также использовать специальные пользовательские библиотеки. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]включает эффективную систему управления временем, доступную через управляемый код и [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] которая тесно интегрирована в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] платформу. Анимация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] упрощает анимацию элементов управления и других графических объектов.

В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эффективно осуществляются все внутренние процессы управления системой времени и перерисовки экрана. Предоставляются классы контроля времени, позволяющие сосредоточиться на создаваемых эффектах, а не на механике их реализации. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также упрощает создание собственной анимации, предоставляя доступ к базовым классам анимации, из которых пользовательские классы могут наследовать средства создания пользовательской анимации. По сравнению со стандартными пользовательские классы анимации обеспечивают большое преимущество в производительности.

<a name="thewpftimingsystem"></a>

## <a name="wpf-property-animation-system"></a>Система анимации свойств WPF

Если вы понимаете несколько важных концепций системы управления временем, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимация может быть проще в использовании. Самое важное состоит в том, что в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно анимировать объекты, применяя анимацию к отдельным свойствам. Например, чтобы увеличить элемент платформы, необходимо анимировать его <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> Свойства и. Чтобы сделать объект эффектным от представления, необходимо анимировать его <xref:System.Windows.UIElement.Opacity%2A> свойство.

Свойство, поддерживающее анимацию, должно удовлетворять следующим трем требованиям.

- Свойство является свойством зависимостей.

- Он должен принадлежать классу, который наследует от <xref:System.Windows.DependencyObject> и реализует <xref:System.Windows.Media.Animation.IAnimatable> интерфейс.

- Доступен совместимый тип анимации. (Если не [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет его, можно создать собственный. См. раздел [Общие сведения о пользовательской анимации](custom-animations-overview.md).)

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]содержит множество объектов, имеющих <xref:System.Windows.Media.Animation.IAnimatable> Свойства. Элементы управления, такие как <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.TabControl> , а также и <xref:System.Windows.Controls.Panel> объекты, <xref:System.Windows.Shapes.Shape> наследуются от <xref:System.Windows.DependencyObject> . Большинство их свойств являются свойствами зависимостей.

Анимацию можно использовать практически везде, где используются стили и шаблоны элементов управления. Анимация не обязательно должна быть визуальной; можно анимировать и объекты, не являющиеся частью пользовательского интерфейса, если они соответствуют описанным в этом разделе условиям.

<a name="storyboardwalkthrough"></a>

## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Пример. Реализация исчезновения и появления элемента

В этом примере показано, как использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимацию для анимации значения свойства зависимостей. В нем используется объект <xref:System.Windows.Media.Animation.DoubleAnimation> , который представляет собой тип анимации, создающей <xref:System.Double> значения, для анимации <xref:System.Windows.UIElement.Opacity%2A> свойства объекта <xref:System.Windows.Shapes.Rectangle> . В результате <xref:System.Windows.Shapes.Rectangle> исчезает и выходит из представления.

В первой части примера создается <xref:System.Windows.Shapes.Rectangle> элемент. В следующих шагах показано, как создать анимацию и применить ее к <xref:System.Windows.UIElement.Opacity%2A> свойству прямоугольника.

Ниже показано, как создать <xref:System.Windows.Shapes.Rectangle> элемент в <xref:System.Windows.Controls.StackPanel> в XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]

Ниже показано, как создать <xref:System.Windows.Shapes.Rectangle> элемент в <xref:System.Windows.Controls.StackPanel> коде.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]

<a name="opacity_animation_step1"></a>

### <a name="part-1-create-a-doubleanimation"></a>Часть 1. Создание объекта DoubleAnimation

Один из способов сделать элемент недоступным для просмотра — анимировать его <xref:System.Windows.UIElement.Opacity%2A> свойство. Поскольку <xref:System.Windows.UIElement.Opacity%2A> свойство имеет тип, требуется <xref:System.Double> анимация, создающая значения типа Double. Это <xref:System.Windows.Media.Animation.DoubleAnimation> одна из таких анимаций. <xref:System.Windows.Media.Animation.DoubleAnimation>Создает переход между двумя значениями типа Double. Чтобы указать его начальное значение, необходимо задать его <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство. Чтобы указать конечное значение, необходимо задать его <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство.

1. Значение Opacity объекта `1.0` делает объект полностью непрозрачным, а значение непрозрачности `0.0` делает его полностью невидимым. Чтобы сделать переход анимации с `1.0` на, `0.0` Задайте для свойства значение <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> `1.0` , а для <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойства `0.0` — значение. Ниже показано, как создать <xref:System.Windows.Media.Animation.DoubleAnimation> в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]

    Ниже показано, как создать <xref:System.Windows.Media.Animation.DoubleAnimation> в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]

2. Далее необходимо указать <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . Объект <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимации указывает, как долго уходит от его начального значения к целевому значению. Ниже показано, как установить значение <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 секунд в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]

    Ниже показано, как установить значение <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 секунд в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]

3. Предыдущий код показал анимацию, которая переводится с `1.0` на `0.0` , что приводит к тому, что целевой элемент постепенно переводится из абсолютного непрозрачного в невидимый. Чтобы вернуть элемент в представление после исчезновения, установите <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> для свойства анимации значение `true` . Чтобы сделать анимацию неопределенной, задайте <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> для свойства значение <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . Ниже показано, как задать <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Свойства и в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]

    Ниже показано, как задать <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Свойства и в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]

<a name="opacity_animation_step2"></a>

### <a name="part-2-create-a-storyboard"></a>Часть 2. Создание раскадровки

Чтобы применить анимацию к объекту, создайте <xref:System.Windows.Media.Animation.Storyboard> и используйте <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> вложенные свойства и, чтобы указать объект и свойство для анимации.

1. Создайте <xref:System.Windows.Media.Animation.Storyboard> и добавьте анимацию в качестве дочернего элемента. Ниже показано, как создать <xref:System.Windows.Media.Animation.Storyboard> в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]

    Чтобы создать <xref:System.Windows.Media.Animation.Storyboard> в коде, объявите <xref:System.Windows.Media.Animation.Storyboard> переменную на уровне класса.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]

    Затем инициализируйте <xref:System.Windows.Media.Animation.Storyboard> и добавьте анимацию в качестве дочернего элемента.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]

2. Объект <xref:System.Windows.Media.Animation.Storyboard> должен быть в курсе, где применяется анимация. Используйте <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> присоединенное свойство, чтобы указать объект для анимации. Ниже показано, как задать целевое имя <xref:System.Windows.Media.Animation.DoubleAnimation> для в `MyRectangle` XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]

    Ниже показано, как задать целевое имя объекта в <xref:System.Windows.Media.Animation.DoubleAnimation> `MyRectangle` в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]

3. Используйте <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> присоединенное свойство, чтобы указать свойство для анимации. Ниже показано, как настроить анимацию для <xref:System.Windows.UIElement.Opacity%2A> свойства объекта <xref:System.Windows.Shapes.Rectangle> в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]

    Ниже показано, как настроить анимацию для <xref:System.Windows.UIElement.Opacity%2A> свойства <xref:System.Windows.Shapes.Rectangle> в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]

Дополнительные сведения о <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> синтаксисе и дополнительные примеры см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).

<a name="opacity_animation_step3"></a>

### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Часть 3 (XAML). Связывание раскадровки с триггером

Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] — использовать триггер события. В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с триггером в XAML.

1. Создайте <xref:System.Windows.Media.Animation.BeginStoryboard> объект и свяжите с ним раскадровку. <xref:System.Windows.Media.Animation.BeginStoryboard>— Это тип <xref:System.Windows.TriggerAction> , который применяет и запускает <xref:System.Windows.Media.Animation.Storyboard> .

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]

2. Создайте объект <xref:System.Windows.EventTrigger> и добавьте в <xref:System.Windows.Media.Animation.BeginStoryboard> его <xref:System.Windows.EventTrigger.Actions%2A> коллекцию. Задайте <xref:System.Windows.EventTrigger.RoutedEvent%2A> для свойства объекта <xref:System.Windows.EventTrigger> перенаправленное событие, которое необходимо запустить <xref:System.Windows.Media.Animation.Storyboard> . (Дополнительные сведения о перенаправленных событиях см. в разделе [Общие сведения о перенаправленных событиях](../advanced/routed-events-overview.md).)

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]

3. Добавьте в <xref:System.Windows.EventTrigger> <xref:System.Windows.FrameworkElement.Triggers%2A> коллекцию прямоугольника.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]

<a name="opacity_animation_step3code"></a>

### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Часть 3 (код). Связывание раскадровки с обработчиком событий

Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> в коде — использовать обработчик событий. В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с обработчиком событий в коде.

1. Зарегистрируйте <xref:System.Windows.FrameworkElement.Loaded> событие прямоугольника.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]

2. Объявите обработчик событий. В обработчике событий используйте метод, <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> чтобы применить раскадровку.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]

### <a name="complete-example"></a>Пример целиком

Ниже показано, как создать прямоугольник, который исчезает и выходит из представления в XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]

Далее показано, как создать прямоугольник, который исчезает и появляется, в коде.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]

<a name="animationtypes"></a>

## <a name="animation-types"></a>Типы анимации

Поскольку анимация создает значения свойств, для различных типов свойств существуют различные типы анимации. Чтобы анимировать свойство, которое принимает <xref:System.Double> , например <xref:System.Windows.FrameworkElement.Width%2A> свойство элемента, используйте анимацию, создающую <xref:System.Double> значения. Чтобы анимировать свойство, которое принимает <xref:System.Windows.Point> , используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д. Из-за количества различных типов свойств в пространстве имен существует несколько классов анимации <xref:System.Windows.Media.Animation> . Имена классов следуют строгому соглашению, благодаря чему их легко различать.

- \<*Type*>Анимация

  Такая анимация называется "базовой" (или From/To/By) и производится либо от начального до конечного значения, либо посредством добавления значения смещения к начальному значению.

  - Чтобы установить начальное значение, присвойте значение свойству From анимации.

  - Чтобы установить конечное значение, присвойте значение свойству To анимации.

  - Чтобы установить значение смещения, присвойте значение свойству By анимации.

  В примерах этого раздела используются анимации этого класса, поскольку они являются наиболее простыми в использовании. Сведения об анимации From/To/By подробно описаны в обзоре анимации From/To/By.

- \<*Type*>AnimationUsingKeyFrames

  Анимация с использованием ключевых кадров является более эффективным средством, чем анимация класса From/To/By, поскольку при ее использовании можно задать любое число конечных значений, а также управлять методами их интерполяции. Некоторые типы могут быть анимированы только с помощью анимации с ключевыми кадрами. Анимация по ключевым кадрам подробно описана в разделе [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).

- \<*Type*>аниматионусингпас

  Анимация с использованием пути позволяет использовать геометрический путь для создания анимации значений.

- \<*Type*>AnimationBase

  Абстрактный класс, который при реализации реализует анимацию \<*Type*> значения. Этот класс выступает в качестве базового класса для \<*Type*> классов Animation и \<*Type*> AnimationUsingKeyFrames. Эти классы используются непосредственно только для создания пользовательской анимации. В противном случае используйте анимацию анимации \<*Type*> или опорный кадр \<*Type*> .

В большинстве случаев потребуется использовать \<*Type*> классы анимации, такие как <xref:System.Windows.Media.Animation.DoubleAnimation> и <xref:System.Windows.Media.Animation.ColorAnimation> .

В следующей таблице приведены несколько общих типов анимации, а также некоторые свойства, с которыми они используются.

|Тип свойства|Соответствующая базовая (From/To/By) анимация|Соответствующая анимация с ключевыми кадрами|Соответствующая анимация с использованием пути|Пример использования|
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|None|Анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> объекта <xref:System.Windows.Media.SolidColorBrush> или <xref:System.Windows.Media.GradientStop> .|
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Анимация <xref:System.Windows.FrameworkElement.Width%2A> объекта или объекта <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.Button> .|
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Анимация <xref:System.Windows.Media.EllipseGeometry.Center%2A> расположения объекта <xref:System.Windows.Media.EllipseGeometry> .|
|<xref:System.String>|None|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|None|Анимация <xref:System.Windows.Controls.TextBlock.Text%2A> объекта или объекта <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Button> .|

<a name="animationsaretimelines"></a>

### <a name="animations-are-timelines"></a>Анимации представляет собой шкалу времени

Все типы анимации наследуют от <xref:System.Windows.Media.Animation.Timeline> класса, поэтому все анимации являются специализированными типами временных шкал. A <xref:System.Windows.Media.Animation.Timeline> определяет сегмент времени. Можно указать *временные характеристики* временной шкалы: ее количество <xref:System.Windows.Media.Animation.Timeline.Duration%2A> повторений, а также время, в течение которого она выполняется.

Так как анимация представляет собой <xref:System.Windows.Media.Animation.Timeline> , она также представляет сегмент времени. Анимация также вычисляет выходные значения по мере продвижения по заданному сегменту времени (или <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ). По мере выполнения (воспроизведения) анимации обновляется свойство, с которым она связана.

Три часто используемых свойства времени: <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> .

#### <a name="the-duration-property"></a>Свойство Duration

Как упоминалось ранее, временная шкала представляет собой сегмент времени. Длина этого сегмента определяется по <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкале, которая обычно указывается с помощью <xref:System.Windows.Duration.TimeSpan%2A> значения. По достижении конца временной шкалы времени ее выполнение завершается.

<xref:System.Windows.Media.Animation.Timeline.Duration%2A>Для определения текущего значения анимации используется ее свойство. Если для анимации не задано <xref:System.Windows.Media.Animation.Timeline.Duration%2A> значение, используется по умолчанию 1 секунда.

Следующий синтаксис демонстрирует упрощенную версию [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] синтаксиса атрибута для <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Свойства.

*количество часов* `:` *минут* `:` *с*

В следующей таблице показано несколько <xref:System.Windows.Duration> параметров и их результирующие значения.

|Параметр|Возвращаемое значение|
|-------------|---------------------|
|0:0:5.5|5,5 секунды.|
|0:30:5.5|30 минут и 5,5 секунды.|
|1:30:5.5|1 час, 30 минут и 5,5 секунды.|

Одним из способов указания <xref:System.Windows.Duration> в коде является использование <xref:System.TimeSpan.FromSeconds%2A> метода для создания <xref:System.TimeSpan> , а затем объявление новой <xref:System.Windows.Duration> структуры с помощью <xref:System.TimeSpan> .

Дополнительные сведения о <xref:System.Windows.Duration> значениях и полный [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Синтаксис см. в разделе <xref:System.Windows.Duration> структура.

#### <a name="autoreverse"></a>Свойство AutoReverse

<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>Свойство указывает, будет ли временная шкала воспроизводиться назад после достижения конца <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . Если задать для этого свойства анимации значение, анимация будет отменяться `true` после достижения конца <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , начиная с конечного значения и заканчивая начальным значением. По умолчанию это свойство имеет значение `false` .

#### <a name="repeatbehavior"></a>RepeatBehavior

<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>Свойство указывает, сколько раз будет воспроизводиться временная шкала. По умолчанию временные шкалы имеют число итераций `1.0` , что означает, что они воспроизводятся один раз и не повторяются.

Дополнительные сведения об этих свойствах и других см. в разделе [Общие сведения о поведении времени](timing-behaviors-overview.md).

<a name="applyanimationstoproperty"></a>

## <a name="applying-an-animation-to-a-property"></a>Применение анимации к свойству

В предыдущих разделах описаны различные типы анимации и их свойства времени. В этом подразделе показано, как применить анимацию к свойству. <xref:System.Windows.Media.Animation.Storyboard>объекты предоставляют один из способов применения анимации к свойствам. <xref:System.Windows.Media.Animation.Storyboard>— Это *временная шкала контейнера* , которая предоставляет сведения о целевой информации для содержащихся в ней анимаций.

### <a name="targeting-objects-and-properties"></a>Целевые объекты и свойства

<xref:System.Windows.Media.Animation.Storyboard>Класс предоставляет <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> вложенные свойства и. Эти свойства определяют анимируемые объекты. Чтобы использовать объект в качестве целевого объекта анимации, обычно следует присвоить ему имя.

Присваивание имени <xref:System.Windows.FrameworkElement> объекту отличается от присвоения ему имени <xref:System.Windows.Freezable> . Большинство элементов управления и панелей являются элементами среды. Однако большинство чисто графических объектов, в том числе кисти, преобразования и геометрические объекты, являются фиксируемыми объектами. Если вы не уверены, является ли тип типом <xref:System.Windows.FrameworkElement> или <xref:System.Windows.Freezable> , обратитесь к разделу **Иерархия наследования** в справочной документации.

- Чтобы создать <xref:System.Windows.FrameworkElement> цель анимации, присвойте ей имя, задав его <xref:System.Windows.FrameworkElement.Name%2A> свойство. В коде также необходимо использовать <xref:System.Windows.FrameworkElement.RegisterName%2A> метод для регистрации имени элемента со страницей, к которой он принадлежит.

- Чтобы сделать <xref:System.Windows.Freezable> объект целевым объектом анимации в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , используйте [директиву x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) , чтобы присвоить ей имя. В коде вы просто используете метод, <xref:System.Windows.FrameworkElement.RegisterName%2A> чтобы зарегистрировать объект со страницей, к которой он принадлежит.

В следующих разделах приводится пример именования элемента в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] коде и. Более подробные сведения об именовании и нацеливании см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).

### <a name="applying-and-starting-storyboards"></a>Применение и запуск раскадровки

Чтобы запустить раскадровку в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , свяжите ее с <xref:System.Windows.EventTrigger> . <xref:System.Windows.EventTrigger>Объект является объектом, который описывает действия, выполняемые при наступлении указанного события. Одно из этих действий может быть <xref:System.Windows.Media.Animation.BeginStoryboard> действием, которое используется для запуска раскадровки. Триггеры событий по концепции аналогичны обработчикам событий, так как они позволяют задать реакцию приложения на конкретное событие. В отличие от обработчиков событий, триггеры событий могут быть полностью описаны в разделе [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ; никакой другой код не требуется.

Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> в коде, можно использовать <xref:System.Windows.EventTrigger> или <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод <xref:System.Windows.Media.Animation.Storyboard> класса.

<a name="controllingstoryboards"></a>

## <a name="interactively-control-a-storyboard"></a>Интерактивное управление раскадровкой

В предыдущем примере показано, как запустить <xref:System.Windows.Media.Animation.Storyboard> событие при возникновении события. Можно также интерактивно управлять <xref:System.Windows.Media.Animation.Storyboard> после запуска: вы можете приостановить, возобновить, остановить, перейти к его периоду заполнения, найти и удалить <xref:System.Windows.Media.Animation.Storyboard> . Дополнительные сведения и пример, демонстрирующий интерактивное управление <xref:System.Windows.Media.Animation.Storyboard> , см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).

<a name="fillbehaviorsection"></a>

## <a name="what-happens-after-an-animation-ends"></a>Что происходит по завершении анимации?

<xref:System.Windows.Media.Animation.FillBehavior>Свойство определяет, как ведет себя временная шкала при ее завершении. По умолчанию временная шкала начинается по <xref:System.Windows.Media.Animation.ClockState.Filling> завершении. Анимация, которая <xref:System.Windows.Media.Animation.ClockState.Filling> содержит конечное выходное значение.

<xref:System.Windows.Media.Animation.DoubleAnimation>В предыдущем примере не заканчивается, так как его <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойство имеет значение <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . В следующем примере прямоугольник анимируется с помощью аналогичной анимации. В отличие от предыдущего примера, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Свойства и <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> этой анимации остаются в значениях по умолчанию. Таким образом, анимация выполняется от 1 до 0 в течение пяти секунд, а затем останавливается.

[!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]

[!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
[!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]

Так как <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> значение по умолчанию не изменилось, то есть <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> анимация сохраняет свое окончательное значение 0 при завершении. Таким образом, <xref:System.Windows.UIElement.Opacity%2A> прямоугольник остается в 0 после окончания анимации. Если задать <xref:System.Windows.UIElement.Opacity%2A> для прямоугольника другое значение, код не будет оказывать никакого влияния, так как анимация по-прежнему влияет на <xref:System.Windows.UIElement.Opacity%2A> свойство.

Одним из способов восстановить управление анимированным свойством в коде является использование <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода и указание значения NULL для <xref:System.Windows.Media.Animation.AnimationTimeline> параметра. Дополнительные сведения и пример см. в разделе [Задание свойства после его анимации с помощью раскадровки](how-to-set-a-property-after-animating-it-with-a-storyboard.md).

Обратите внимание, что, хотя установка значения свойства, имеющего <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> анимацию или, не оказывает никакого влияния, значение свойства изменяется. Дополнительные сведения см. в разделе [Обзор анимации и системы управления временем](animation-and-timing-system-overview.md).

<a name="databindingAndAnimatingAnimationsSection"></a>

## <a name="data-binding-and-animating-animations"></a>Привязка данных и анимирование анимации

Большинство свойств анимации могут быть привязанными к данным или анимированными. Например, можно анимировать <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство объекта <xref:System.Windows.Media.Animation.DoubleAnimation> . Однако в связи с особенностями работы системы времени поведение привязки данных или анимированных анимаций отличается от других случаев привязки данных и анимирования объектов. Чтобы понять их поведение, следует понять значение применения анимации к свойству.

См. пример в предыдущем разделе, в котором показано, как анимировать <xref:System.Windows.UIElement.Opacity%2A> прямоугольник. При загрузке прямоугольника в предыдущем примере его триггер события применяет <xref:System.Windows.Media.Animation.Storyboard> . Система времени создает копию <xref:System.Windows.Media.Animation.Storyboard> и ее анимацию. Эти копии заморожены (доступны только для чтения), а <xref:System.Windows.Media.Animation.Clock> объекты создаются из них. Эти объекты используются для выполнения фактических действий по анимации целевых свойств.

Система управления временем создает часы для <xref:System.Windows.Media.Animation.DoubleAnimation> и применяет ее к объекту и свойству, заданному <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> <xref:System.Windows.Media.Animation.DoubleAnimation> . В этом случае система времени применяет часы к <xref:System.Windows.UIElement.Opacity%2A> свойству объекта с именем «миректангле».

Несмотря на то, что для используется также время <xref:System.Windows.Media.Animation.Storyboard> , часы не применяются к свойствам. Его целью является управление дочерними часами, а также часов, создаваемых для <xref:System.Windows.Media.Animation.DoubleAnimation> .

Для отражения анимацией привязки данных или изменений анимации следует обновить ее часы. Автоматическое обновление часов не поддерживается. Чтобы анимация отражала изменения, повторно примените ее раскадровку с помощью <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метода или. При использовании любого из этих методов анимация запускается повторно. В коде можно использовать <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метод, чтобы переместить раскадровку обратно в предыдущую точку.

Пример анимации с привязкой к данным см. в разделе [Пример анимации по ключевым сплайнам](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations). Дополнительные сведения о работе анимации и системы управления временем см. в разделе [Общие сведения об анимации и системе](animation-and-timing-system-overview.md)управления временем.

<a name="otherWaysToAnimateSection"></a>

## <a name="other-ways-to-animate"></a>Другие способы анимации

В примерах этого раздела демонстрируется анимация с помощью раскадровок. При использовании кода можно выполнять анимацию различными способами. Дополнительные сведения см. в статье [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md).

<a name="animation_samples"></a>

## <a name="animation-samples"></a>Примеры анимации

В следующих примерах описывается порядок добавления анимации в приложения.

- [Пример целевых значений анимации From, To и By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)

  Описание различных параметров анимации From/To/By.

- [Пример поведения анимации с учетом времени](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)

  Описание способов управления поведением анимации во времени. В этом примере также описывается порядок привязки данных для конечного значения анимации.

<a name="related_topics"></a>

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md)|Описывает, как система управления временем использует <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> классы и, которые позволяют создавать анимации.|
|[Советы и рекомендации по анимации](animation-tips-and-tricks.md)|Список полезных советов по устранению проблем с анимацией, например проблем производительности.|
|[Общие сведения о пользовательской анимации](custom-animations-overview.md)|Описание способов расширения системы анимации полными кадрами, классами анимации и покадровым обратным вызовом.|
|[Общие сведения об анимациях From/To/By](from-to-by-animations-overview.md)|Описание способов создания анимации, которая переходит между двумя значениями.|
|[Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)|Описание способов создания анимации с несколькими целевыми значениями, включая возможность управления методом интерполяции.|
|[Функции плавности](easing-functions.md)|Описание способов применения математических формул к анимациям для получения реалистичного поведения, такого как подскок.|
|[Общие сведения об анимация с использованием пути](path-animations-overview.md)|Описание способов перемещения или поворота объекта по сложному пути.|
|[Общие сведения о методах анимации свойств](property-animation-techniques-overview.md)|Описание анимации свойств с помощью раскадровок, локальных анимаций, часов и покадровой анимации.|
|[Общие сведения о Storyboard](storyboards-overview.md)|Описание способов использования раскадровок с несколькими временными шкалами для создания сложных анимаций.|
|[Общие сведения о характере поведения во времени](timing-behaviors-overview.md)|Описывает <xref:System.Windows.Media.Animation.Timeline> типы и свойства, используемые в анимации.|
|[Общие сведения о временных событиях](timing-events-overview.md)|Описание событий, доступных для <xref:System.Windows.Media.Animation.Timeline> объектов и <xref:System.Windows.Media.Animation.Clock> для выполнения кода в точках временной шкалы, таких как begin, пауза, возобновление, пропуск или остановка.|
|[Практические руководства](animation-and-timing-how-to-topics.md)|Примеры кода для использования анимаций и временных шкал в приложении.|
|[Разделы руководства, посвященные часам](clocks-how-to-topics.md)|Содержит примеры кода для использования <xref:System.Windows.Media.Animation.Clock> объекта в приложении.|
|[Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)|Примеры кода для использования покадровой анимации в приложении.|
|[Практические руководства, посвященные анимации пути](path-animation-how-to-topics.md)|Примеры кода для применения анимации с использованием пути в приложении.|

<a name="reference"></a>

## <a name="reference"></a>Ссылка

- <xref:System.Windows.Media.Animation.Timeline>

- <xref:System.Windows.Media.Animation.Storyboard>

- <xref:System.Windows.Media.Animation.BeginStoryboard>

- <xref:System.Windows.Media.Animation.Clock>
