---
title: Общие сведения о декоративных элементах
description: Сведения о Windows Presentation Foundation декоративных элементах, Специальный тип FrameworkElement, который предоставляет пользователю подсказки, например функциональные дескрипторы для элементов.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 43d4af9f86c6ae72a61f86d1ca19405c2dcc6cc8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167730"
---
# <a name="adorners-overview"></a>Общие сведения о декоративных элементах

Декораторы — это особый тип <xref:System.Windows.FrameworkElement> , используемый для предоставления визуальных подсказок пользователю. Помимо прочего, декоративные элементы можно использовать для добавления функциональных дескрипторов к элементам или предоставления информации о состоянии элемента управления.

## <a name="about-adorners"></a>Сведения о декоративных элементах

<xref:System.Windows.Documents.Adorner>Является пользовательским <xref:System.Windows.FrameworkElement> , привязанным к <xref:System.Windows.UIElement> . Декораторы подготавливаются к просмотру в <xref:System.Windows.Documents.AdornerLayer> , который представляет собой область отрисовки, которая всегда находится над декоративным элементом или коллекцией декоративных элементов. Отрисовка декоративного элемента не зависит от отрисовки элемента <xref:System.Windows.UIElement> , к которому привязан декоративный элемент. Декоративный элемент обычно располагается относительно элемента, к которому он привязан, используя стандартную координату двухмерной координаты, расположенную в левом верхнем углу декоративного элемента.

Типичные сценарии использования декоративных элементов:

- Добавление функциональных дескрипторов в <xref:System.Windows.UIElement> , позволяющих пользователю манипулировать элементом каким-либо образом (изменение размера, вращение, перемещение и т. д.).
- Обеспечение визуальной обратной связи для указания различных состояний или в ответ на различные события.
- Наложение визуальных украшений на <xref:System.Windows.UIElement> .
- Визуальная маскировка или переопределение части или всех элементов <xref:System.Windows.UIElement> .

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет базовую среду для декоративных визуальных элементов. В следующей таблице перечислены основные типы, используемые при настройке объектов, и их назначение. Ниже приведено несколько примеров использования.

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Абстрактный базовый класс, из которого наследуются все конкретные реализации декоративного элемента.|
|<xref:System.Windows.Documents.AdornerLayer>|Класс, представляющий слой отрисовки декоративного элемента одного или нескольких настроенных элементов.|
|<xref:System.Windows.Documents.AdornerDecorator>|Класс, который позволяет ассоциировать слой декоративного элемента с коллекцией элементов.|

## <a name="implementing-a-custom-adorner"></a>Реализация пользовательского декоративного элемента

Среда декоративных элементов, предоставляемая [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], предназначена в первую очередь для поддержки создания пользовательских декоративных элементов. Пользовательский декоративный элемент создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.

> [!NOTE]
> Родителем объекта <xref:System.Windows.Documents.Adorner> является объект, <xref:System.Windows.Documents.AdornerLayer> который визуализирует, а <xref:System.Windows.Documents.Adorner> не элемент, декоративный.

В следующем примере показан класс, который реализует простой декоративный элемент. Пример декоративного элемента просто декоративно углы <xref:System.Windows.UIElement> с круговыми кругами.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
На следующем рисунке показан SimpleCircleAdorner, применяемый к <xref:System.Windows.Controls.TextBox> :

![Снимок экрана, на котором отображается декоративное текстовое поле.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Поведение отрисовки для декоративных элементов

Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор. Обычным способом реализации поведения при отрисовке является переопределение <xref:System.Windows.UIElement.OnRender%2A> метода и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для отрисовки визуальных элементов декоративного элемента по мере необходимости (как показано в примере выше).

> [!NOTE]
> Все, что помещено в слой декоративного элемента, отрисовывается поверх остальных установленных стилей. Другими словами, декоративные элементы всегда визуально находятся сверху и не могут быть переопределены с помощью упорядочения по z-координате.

## <a name="events-and-hit-testing"></a>События и проверка нажатия

Декораторы получают события ввода так же, как и любые другие <xref:System.Windows.FrameworkElement> .  Поскольку декоративный элемент всегда имеет более высокий z-порядок, чем элемент, на который он оформлен, декоративный элемент получает входные события (например, <xref:System.Windows.UIElement.Drop> или <xref:System.Windows.UIElement.MouseMove> ), которые могут быть предназначены для базового декоративного элемента.  Декоративный элемент может отслеживать определенные события ввода и передавать их в базовый декорированный элемент, повторно запуская событие.

Чтобы включить проверку попадания для элементов в декоративном элементе, задайте для свойства Проверка попадания <xref:System.Windows.UIElement.IsHitTestVisible%2A> **значение false** в декоративном элементе.  Дополнительные сведения о проверке попадания см. [в разделе Проверка попадания в визуальном слое](../graphics-multimedia/hit-testing-in-the-visual-layer.md).

## <a name="adorning-a-single-uielement"></a>Декорирование одного элемента пользовательского интерфейса

Чтобы привязать декоративный элемент к конкретному <xref:System.Windows.UIElement> , выполните следующие действия.

1. Вызовите статический метод, <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> чтобы получить <xref:System.Windows.Documents.AdornerLayer> объект для <xref:System.Windows.UIElement> элемента, который должен быть оформлен. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>переходит вверх по визуальному дереву, начиная с указанного <xref:System.Windows.UIElement> , и возвращает первый найденный слой декоративных элементов. (Если слои декоративных элементов не найдены, метод возвращает значение 0.)

2. Вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод, чтобы привязать декоративный элемент к целевому объекту <xref:System.Windows.UIElement> .

 В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше) к <xref:System.Windows.Controls.TextBox> именованной *митекстбокс*:

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.

## <a name="adorning-the-children-of-a-panel"></a>Декорирование дочерних объектов панели

Чтобы привязать декоративный элемент к дочерним элементам <xref:System.Windows.Controls.Panel> , выполните следующие действия.

1. Вызовите `static` метод, <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> чтобы найти слой декоративных элементов для элемента, чьи дочерние элементы должны быть декоративными.

2. Перечислите дочерние элементы родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента к каждому дочернему элементу.

В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше) к дочерним элементам <xref:System.Windows.Controls.StackPanel> именованного *мистаккпанел*:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Обзор фигур и базовых средств рисования в приложении WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Рисование с помощью объектов Image, Drawing и Visual](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Обзор объектов Drawing](../graphics-multimedia/drawing-objects-overview.md)
- [Практические руководства](adorners-how-to-topics.md)
