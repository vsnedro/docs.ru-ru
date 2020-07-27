---
title: Стили и шаблоны элемента Menu
description: Сведения о стилях и шаблонах для Windows Presentation Foundation элементе управления Menu. Измените ControlTemplate, чтобы присвоить элементу управления уникальный внешний вид.
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 5187e4a479609686e39e043808931141ca52078c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164543"
---
# <a name="menu-styles-and-templates"></a>Стили и шаблоны элемента Menu
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Menu> элемента управления. Можно изменить значение по умолчанию, <xref:System.Windows.Controls.ControlTemplate> чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="menu-parts"></a>Части меню  
 <xref:System.Windows.Controls.Menu>Элемент управления не имеет именованных частей.  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для в <xref:System.Windows.Controls.Menu> шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.Menu> ; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).  Если объект не <xref:System.Windows.Controls.ItemsPresenter> является прямым дочерним элементом объекта <xref:System.Windows.Controls.ScrollViewer> , необходимо присвоить ему <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter` .  
  
## <a name="menu-states"></a>Состояния меню  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Menu> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Допустимо|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет `true` фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство `true` имеет элемент управления, не имеющий фокуса.|  
  
## <a name="menuitem-parts"></a>Части MenuItem  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Menu> элемента управления.  
  
|Часть|Тип|Описание|  
|-|-|-|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Область для подменю.|  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для в <xref:System.Windows.Controls.MenuItem> шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.MenuItem> ; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).  Если объект не <xref:System.Windows.Controls.ItemsPresenter> является прямым дочерним элементом объекта <xref:System.Windows.Controls.ScrollViewer> , необходимо присвоить ему <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter` .  
  
## <a name="menuitem-states"></a>Состояния MenuItem  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.MenuItem> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Допустимо|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет `true` фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство `true` имеет элемент управления, не имеющий фокуса.|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a>Пример меню и ControlTemplate для MenuItem  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Menu> элемента управления.  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.MenuItem> элемента управления.  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 В следующем примере определяется объект `MenuScrollViewer` , который используется в предыдущем примере.  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 В <xref:System.Windows.Controls.ControlTemplate> примерах используется один или несколько следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента Control](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Создание шаблона элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
