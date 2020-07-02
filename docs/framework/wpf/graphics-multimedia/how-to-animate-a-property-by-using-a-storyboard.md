---
title: Практическое руководство. Анимирование свойства с помощью раскадровки (класс Storyboard)
description: Енливен пользовательский интерфейс с помощью анимации и раскадровки для свойств в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: f21b606751b845905a7bde6d3a7658b214369cc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853742"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Практическое руководство. Анимирование свойства с помощью раскадровки (класс Storyboard)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Storyboard> для анимации свойств. Чтобы анимировать свойство с помощью <xref:System.Windows.Media.Animation.Storyboard> , создайте анимацию для каждого свойства, которое необходимо анимировать, а также создайте объект <xref:System.Windows.Media.Animation.Storyboard> для хранения анимации.  
  
 Тип свойства определяет тип используемой анимации. Например, чтобы анимировать свойство, принимающее <xref:System.Double> значения, используйте <xref:System.Windows.Media.Animation.DoubleAnimation> . <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> Вложенные свойства и задают объект и свойство, к которому применяется анимация.  
  
 Чтобы запустить раскадровку в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , используйте <xref:System.Windows.Media.Animation.BeginStoryboard> действие и <xref:System.Windows.EventTrigger> . <xref:System.Windows.EventTrigger>Запускает действие, <xref:System.Windows.Media.Animation.BeginStoryboard> когда происходит событие, заданное его <xref:System.Windows.EventTrigger.RoutedEvent%2A> свойством. <xref:System.Windows.Media.Animation.BeginStoryboard>Действие запускает <xref:System.Windows.Media.Animation.Storyboard> .  
  
 В следующем примере <xref:System.Windows.Media.Animation.Storyboard> объекты используются для анимации двух <xref:System.Windows.Controls.Button> элементов управления. Чтобы изменить размер первой кнопки, <xref:System.Windows.FrameworkElement.Width%2A> она будет анимирована. Чтобы изменить цвет второй кнопки, <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойство объекта <xref:System.Windows.Media.SolidColorBrush> используется для задания <xref:System.Windows.Controls.Control.Background%2A> анимированной кнопки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Хотя анимация может ориентироваться и на <xref:System.Windows.FrameworkElement> объект, например <xref:System.Windows.Controls.Control> или <xref:System.Windows.Controls.Panel> , и на <xref:System.Windows.Freezable> объект, например <xref:System.Windows.Media.Brush> или <xref:System.Windows.Media.Transform> , только элементы платформы имеют <xref:System.Windows.FrameworkElement.Name%2A> свойство. Для назначения имени объекту freezable, чтобы его можно было использовать в анимации, следует использовать [директиву x:Name](../../../desktop-wpf/xaml-services/xname-directive.md), как показано в предыдущем примере.  
  
 При использовании кода необходимо создать <xref:System.Windows.NameScope> для <xref:System.Windows.FrameworkElement> и зарегистрировать имена объектов для анимации <xref:System.Windows.FrameworkElement> . Чтобы начать анимацию в коде, используйте <xref:System.Windows.Media.Animation.BeginStoryboard> действие с <xref:System.Windows.EventTrigger> . При необходимости можно использовать обработчик событий и <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод <xref:System.Windows.Media.Animation.Storyboard> . В следующем примере показано, как использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Дополнительные сведения об анимации и раскадровках см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
 При использовании кода вы не ограничены использованием <xref:System.Windows.Media.Animation.Storyboard> объектов для анимации свойств. Дополнительные сведения и примеры см. в разделах [Анимация свойств без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md) и [Анимация свойств с помощью AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
