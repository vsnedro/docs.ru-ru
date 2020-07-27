---
title: Поддержка автоматизации пользовательского интерфейса для типа элемента управления SplitButton
description: Получение сведений о поддержке модели автоматизации пользовательского интерфейса для типа элемента управления SplitButton. Сведения о требуемой древовидной структуре, свойствах, шаблонах элементов управления и событиях.
ms.date: 03/30/2017
helpviewer_keywords:
- Split Button control type
- control types, Split Button
- UI Automation, Split Button control type
ms.assetid: 14b05ccf-bcd8-4045-9bae-f7679cd98711
ms.openlocfilehash: e32d10f71eaab491f691e4be0529087af9102f93
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163825"
---
# <a name="ui-automation-support-for-the-splitbutton-control-type"></a>Поддержка автоматизации пользовательского интерфейса для типа элемента управления SplitButton
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления SplitButton. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 Элемент управления "Разворачивающаяся кнопка" позволяет выполнять действие в элементе управления и разворачивать этот элемент управления для просмотра списка других возможных действий, которые могут быть выполнены.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления SplitButton. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]Требования применяются ко всем элементам управления "разворачивающаяся кнопка", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 или Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которое относится к элементам управления "Разворачивающаяся кнопка" и описывает, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|------------------|------------------|  
|SplitButton<br /><br /> <ul><li>Image (0 или 1)</li><li>Text (0 или 1)</li><li>Button (1 или 2)<br /><br /> <ul><li>Menu (0 или 1; отображается как дочерний элемент кнопки, которая поддерживает шаблон ExpandCollapse)</li><li>MenuItem (1 или более)</li></ul></li></ul>|SplitButton<br /><br /> -MenuItem (от 1 до many)|  
  
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Разворачивающаяся кнопка". Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|Значение|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Поддерживается при наличии ограничивающего прямоугольника. Если не все точки внутри ограничивающего прямоугольника являются интерактивными и выполняется специализированная проверка на наличие данных, выполните переопределение и предоставьте интерактивную точку.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|"Назад"|Имя элемента управления "Разворачивающаяся кнопка" отображается на кнопке.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|NULL|Элементы управления "Разворачивающаяся кнопка" не имеют меток со статическим текстом.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|SplitButton|Это значение одинаково для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"разворачивающаяся кнопка"|Локализованная строка, соответствующая типу элемента управления SplitButton.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|См. примечания.|Текст справки может указывать результат активации разворачивающейся кнопки и обычно предоставляет тот же тип сведений, что и подсказка.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Элемент управления "Разворачивающаяся кнопка" содержит сведения для конечного пользователя.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элемент управления "Разворачивающаяся кнопка" является видимым для конечного пользователя.|  
  
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Разворачивающаяся кнопка". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Требуется|Разворачивающиеся кнопки всегда имеют действие по умолчанию, связанное с Invoke.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Требуется|Разворачивающиеся кнопки всегда имеют возможность развернуть список вариантов.|  
  
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Разворачивающаяся кнопка". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Требуется|None|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Требуется|None|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Требуется|None|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Требуется|None|  
|Событие изменения свойства<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty>|Требуется|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Требуется|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Требуется|None|  
  
## <a name="splitbutton-control-example"></a>Пример элемента управления "Разворачивающаяся кнопка"  
 На следующем рисунке показан тип элемента управления SplitButton в элементе управления "Сетка данных".  
  
 ![Разворачивающаяся кнопка](./media/uiauto-splitbutton-detailed.gif "uiauto_splitbutton_detailed")  
  
 Представление элемента управления и представление содержимого дерева модели автоматизации пользовательского интерфейса, относящиеся к элементам управления "Сетка данных" и "Разворачивающаяся кнопка", показаны ниже. Шаблоны элементов управления для каждого элемента автоматизации отображаются в круглых скобках.  
  
|Дерево[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление элемента управления|Дерево[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление содержимого|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|<ul><li>SplitButton "Name" (Invoke, ExpandCollapse)</li><li>Button "More options" (Invoke)<br /><br /> <ul><li>Меню</li><li>MenuItem</li><li>…</li></ul></li></ul>|<ul><li>SplitButton "Name" (Invoke, ExpandCollapse)</li><li>Button "More options" (Invoke)<br /><br /> <ul><li>Меню</li><li>MenuItem</li><li>…</li></ul></li></ul>|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Automation.ControlType.SplitButton>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
