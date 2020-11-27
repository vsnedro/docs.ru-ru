---
title: Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Window
description: Получение сведений о поддержке модели автоматизации пользовательского интерфейса для типа элемента управления Window. Сведения о требуемой древовидной структуре, свойствах, шаблонах элементов управления и событиях.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Window control type
- Window control type
- control types, Window
ms.assetid: 53be78a6-cdcc-4af3-a464-5927d19c54e8
ms.openlocfilehash: 675f9cfdf1fb2be8519a671e2fd798520412296d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281275"
---
# <a name="ui-automation-support-for-the-window-control-type"></a>Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Window

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления Window. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Эти условия включают определенные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 Элемент управления "Окно" состоит из рамки окна, содержащей дочерние объекты, такие как заголовок окна, клиент и другие объекты.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]Требования, приведенные в следующих разделах, применяются ко всем элементам управления, которые реализуют тип элемента управления Window, будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 или Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  

 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления "Окно", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|------------------|------------------|  
|Окно|Окно|  
  
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  

 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Окно". Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|Значение|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Элемент управления "Окно" должен иметь активную точку, при нажатии на которую окно становится выбранным или невыбранным.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Окно|Это значение одинаково для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Элемент управления "Окно" всегда должен быть содержимым.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элемент управления "Окно" всегда должен быть элементом управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`null`|Элементы управления "Окно" не имеют статических меток.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"окно"|Локализованная строка, соответствующая типу элемента управления Window.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Элемент управления "Окно" всегда содержит основной элемент Window, имеющий отношение к тому, что пользователь будет воспринимать как семантический идентификатор для этого элемента.|  
  
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  

 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться элементами управления "Окно". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider>|Условная логика|Должен поддерживаться, если окно может быть закреплено.|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|Обязательно|Разрешает перемещать окно, изменять его размер и поворачивать его на экране.|  
|<xref:System.Windows.Automation.Provider.IWindowProvider>|Обязательно|Включает специальные операции для окна.|  
  
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  

 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Окно". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent>|Обязательно|Нет|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательно|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Обязательно|Нет|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>|Зависит|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty>|Зависит|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty>|Зависит|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty>|Зависит|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty>|Зависит|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty>|Зависит|Нет|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent>|Обязательно|Нет|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent>|Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty>|Зависит|Нет|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType.Window>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
