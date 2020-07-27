---
title: Общие сведения о типах элементов управления автоматизации пользовательского интерфейса
description: Ознакомьтесь с обзором типов элементов управления модели автоматизации пользовательского интерфейса, которые представляют собой хорошо известные идентификаторы, которые можно использовать для указания типа элемента управления, представляемого элементом.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: 204e950fca74c4f7bd2c13dc8a8891152954c071
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166139"
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="17e9a-103">Общие сведения о типах элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="17e9a-103">UI Automation Control Types Overview</span></span>
> [!NOTE]
> <span data-ttu-id="17e9a-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="17e9a-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="17e9a-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="17e9a-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="17e9a-106">Типы элементов управления[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] — это хорошо известные идентификаторы, которые можно использовать для указания вида элемента управления, например поля со списком или кнопки.</span><span class="sxs-lookup"><span data-stu-id="17e9a-106">[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="17e9a-107">Известный идентификатор упрощает для вспомогательных устройств определение типов элементов управления, доступных в [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , и способов взаимодействия с ними.</span><span class="sxs-lookup"><span data-stu-id="17e9a-107">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="17e9a-108">Необходимые компоненты элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="17e9a-108">UI Automation Control Type Requisites</span></span>  
 <span data-ttu-id="17e9a-109">Тип элемента управления[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] предоставляют набор условий, которым должны соответствовать поставщики.</span><span class="sxs-lookup"><span data-stu-id="17e9a-109">[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="17e9a-110">При выполнении этих условий элемент управления может использовать имя типа определенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="17e9a-110">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="17e9a-111">Каждый тип элемента управления использует следующие условия:</span><span class="sxs-lookup"><span data-stu-id="17e9a-111">Each control type has conditions for the following:</span></span>  
  
- <span data-ttu-id="17e9a-112">Шаблоны элементов управления[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — какие шаблоны элементов управления должны поддерживаться, какой шаблоны необязательные и какие шаблоны не должны поддерживаться элементом управления.</span><span class="sxs-lookup"><span data-stu-id="17e9a-112">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
- <span data-ttu-id="17e9a-113">Значения свойств[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — какие значения свойств поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="17e9a-113">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values—which property values are supported.</span></span>  
  
- <span data-ttu-id="17e9a-114">Структура дерева[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — обязательная древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="17e9a-114">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="17e9a-115">Если элемент управления удовлетворяет условиям определенного типа элемента управления, значение свойства <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> указывает этот тип.</span><span class="sxs-lookup"><span data-stu-id="17e9a-115">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="17e9a-116">Текущие типы элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="17e9a-116">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="17e9a-117">Следующий список содержит текущий набор типов элементов управления [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="17e9a-117">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
- [<span data-ttu-id="17e9a-118">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления кнопки</span><span class="sxs-lookup"><span data-stu-id="17e9a-118">UI Automation Support for the Button Control Type</span></span>](ui-automation-support-for-the-button-control-type.md)  
  
- [<span data-ttu-id="17e9a-119">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Calendar</span><span class="sxs-lookup"><span data-stu-id="17e9a-119">UI Automation Support for the Calendar Control Type</span></span>](ui-automation-support-for-the-calendar-control-type.md)  
  
- [<span data-ttu-id="17e9a-120">Поддержка модели автоматизированного пользовательского интерфейса для элемента управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="17e9a-120">UI Automation Support for the CheckBox Control Type</span></span>](ui-automation-support-for-the-checkbox-control-type.md)  
  
- [<span data-ttu-id="17e9a-121">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="17e9a-121">UI Automation Support for the ComboBox Control Type</span></span>](ui-automation-support-for-the-combobox-control-type.md)  
  
- [<span data-ttu-id="17e9a-122">Поддержка автоматизированного пользовательского интерфейса для типа элемента управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="17e9a-122">UI Automation Support for the DataGrid Control Type</span></span>](ui-automation-support-for-the-datagrid-control-type.md)  
  
- [<span data-ttu-id="17e9a-123">Поддержка автоматизации пользовательского интерфейса для элемента управления типа DataItem</span><span class="sxs-lookup"><span data-stu-id="17e9a-123">UI Automation Support for the DataItem Control Type</span></span>](ui-automation-support-for-the-dataitem-control-type.md)  
  
- [<span data-ttu-id="17e9a-124">Поддержка автоматизированного пользовательского интерфейса для типа элемента управления Document</span><span class="sxs-lookup"><span data-stu-id="17e9a-124">UI Automation Support for the Document Control Type</span></span>](ui-automation-support-for-the-document-control-type.md)  
  
- [<span data-ttu-id="17e9a-125">Поддержка автоматизации пользовательского интерфейса для типа элемента управления "Поле вода"</span><span class="sxs-lookup"><span data-stu-id="17e9a-125">UI Automation Support for the Edit Control Type</span></span>](ui-automation-support-for-the-edit-control-type.md)  
  
- [<span data-ttu-id="17e9a-126">Поддержка автоматизации пользовательского интерфейса для типа элемента управления Group</span><span class="sxs-lookup"><span data-stu-id="17e9a-126">UI Automation Support for the Group Control Type</span></span>](ui-automation-support-for-the-group-control-type.md)  
  
- [<span data-ttu-id="17e9a-127">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления "Заголовок"</span><span class="sxs-lookup"><span data-stu-id="17e9a-127">UI Automation Support for the Header Control Type</span></span>](ui-automation-support-for-the-header-control-type.md)  
  
- [<span data-ttu-id="17e9a-128">Поддержка модели автоматизации пользовательского интерфейса типа элемента управления HeaderItem</span><span class="sxs-lookup"><span data-stu-id="17e9a-128">UI Automation Support for the HeaderItem Control Type</span></span>](ui-automation-support-for-the-headeritem-control-type.md)  
  
- [<span data-ttu-id="17e9a-129">Поддержка автоматизированного пользовательского интерфейса для элемента управления типа Hyperlink</span><span class="sxs-lookup"><span data-stu-id="17e9a-129">UI Automation Support for the Hyperlink Control Type</span></span>](ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [<span data-ttu-id="17e9a-130">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления изображения</span><span class="sxs-lookup"><span data-stu-id="17e9a-130">UI Automation Support for the Image Control Type</span></span>](ui-automation-support-for-the-image-control-type.md)  
  
- [<span data-ttu-id="17e9a-131">Поддержка модели автоматизации пользовательского интерфейса для элемента управления "Список"</span><span class="sxs-lookup"><span data-stu-id="17e9a-131">UI Automation Support for the List Control Type</span></span>](ui-automation-support-for-the-list-control-type.md)  
  
- [<span data-ttu-id="17e9a-132">Поддержка автоматизированного пользовательского интерфейса для типа элемента управления ListItem</span><span class="sxs-lookup"><span data-stu-id="17e9a-132">UI Automation Support for the ListItem Control Type</span></span>](ui-automation-support-for-the-listitem-control-type.md)  
  
- [<span data-ttu-id="17e9a-133">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления меню</span><span class="sxs-lookup"><span data-stu-id="17e9a-133">UI Automation Support for the Menu Control Type</span></span>](ui-automation-support-for-the-menu-control-type.md)  
  
- [<span data-ttu-id="17e9a-134">Поддержка автоматизации пользовательского интерфейса для типа элемента управления MenuBar</span><span class="sxs-lookup"><span data-stu-id="17e9a-134">UI Automation Support for the MenuBar Control Type</span></span>](ui-automation-support-for-the-menubar-control-type.md)  
  
- [<span data-ttu-id="17e9a-135">Поддержка автоматизации пользовательского интерфейса для типа элемента управления MenuItem</span><span class="sxs-lookup"><span data-stu-id="17e9a-135">UI Automation Support for the MenuItem Control Type</span></span>](ui-automation-support-for-the-menuitem-control-type.md)  
  
- [<span data-ttu-id="17e9a-136">Поддержка автоматизации пользовательского интерфейса для элемента управления Pane</span><span class="sxs-lookup"><span data-stu-id="17e9a-136">UI Automation Support for the Pane Control Type</span></span>](ui-automation-support-for-the-pane-control-type.md)  
  
- [<span data-ttu-id="17e9a-137">Поддержка автоматизации пользовательского интерфейса для типа элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="17e9a-137">UI Automation Support for the ProgressBar Control Type</span></span>](ui-automation-support-for-the-progressbar-control-type.md)  
  
- [<span data-ttu-id="17e9a-138">Поддержка автоматизации пользовательского интерфейса для элемента управления типа RadioButton</span><span class="sxs-lookup"><span data-stu-id="17e9a-138">UI Automation Support for the RadioButton Control Type</span></span>](ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [<span data-ttu-id="17e9a-139">Поддержка автоматизации пользовательского интерфейса для типа элемента управления ScrollBar</span><span class="sxs-lookup"><span data-stu-id="17e9a-139">UI Automation Support for the ScrollBar Control Type</span></span>](ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [<span data-ttu-id="17e9a-140">Поддержка автоматизации пользовательского интерфейса для элемента управления Separator</span><span class="sxs-lookup"><span data-stu-id="17e9a-140">UI Automation Support for the Separator Control Type</span></span>](ui-automation-support-for-the-separator-control-type.md)  
  
- [<span data-ttu-id="17e9a-141">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ползунка</span><span class="sxs-lookup"><span data-stu-id="17e9a-141">UI Automation Support for the Slider Control Type</span></span>](ui-automation-support-for-the-slider-control-type.md)  
  
- [<span data-ttu-id="17e9a-142">Поддержка Автоматизации Пользовательского Интерфейса для типа элемента управления "Счетчик"</span><span class="sxs-lookup"><span data-stu-id="17e9a-142">UI Automation Support for the Spinner Control Type</span></span>](ui-automation-support-for-the-spinner-control-type.md)  
  
- [<span data-ttu-id="17e9a-143">Поддержка автоматизации пользовательского интерфейса для типа элемента управления SplitButton</span><span class="sxs-lookup"><span data-stu-id="17e9a-143">UI Automation Support for the SplitButton Control Type</span></span>](ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [<span data-ttu-id="17e9a-144">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="17e9a-144">UI Automation Support for the StatusBar Control Type</span></span>](ui-automation-support-for-the-statusbar-control-type.md)  
  
- [<span data-ttu-id="17e9a-145">Поддержка UI Automation для типа элемента управления Tab</span><span class="sxs-lookup"><span data-stu-id="17e9a-145">UI Automation Support for the Tab Control Type</span></span>](ui-automation-support-for-the-tab-control-type.md)  
  
- [<span data-ttu-id="17e9a-146">Поддержка автоматизации пользовательского интерфейса для типа элемента управления TabItem</span><span class="sxs-lookup"><span data-stu-id="17e9a-146">UI Automation Support for the TabItem Control Type</span></span>](ui-automation-support-for-the-tabitem-control-type.md)  
  
- [<span data-ttu-id="17e9a-147">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Table</span><span class="sxs-lookup"><span data-stu-id="17e9a-147">UI Automation Support for the Table Control Type</span></span>](ui-automation-support-for-the-table-control-type.md)  
  
- [<span data-ttu-id="17e9a-148">Поддержка автоматизированного пользовательского интерфейса для текстовых элементов управления</span><span class="sxs-lookup"><span data-stu-id="17e9a-148">UI Automation Support for the Text Control Type</span></span>](ui-automation-support-for-the-text-control-type.md)  
  
- [<span data-ttu-id="17e9a-149">Поддержка автоматизации пользовательского интерфейса для элемента управления типа Thumb</span><span class="sxs-lookup"><span data-stu-id="17e9a-149">UI Automation Support for the Thumb Control Type</span></span>](ui-automation-support-for-the-thumb-control-type.md)  
  
- [<span data-ttu-id="17e9a-150">Поддержка Автоматизации Пользовательского Интерфейса для Элементов Управления Типа "Заголовок Окна"</span><span class="sxs-lookup"><span data-stu-id="17e9a-150">UI Automation Support for the TitleBar Control Type</span></span>](ui-automation-support-for-the-titlebar-control-type.md)  
  
- [<span data-ttu-id="17e9a-151">Поддержка автоматизации пользовательского интерфейса для типа элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="17e9a-151">UI Automation Support for the ToolBar Control Type</span></span>](ui-automation-support-for-the-toolbar-control-type.md)  
  
- [<span data-ttu-id="17e9a-152">Поддержка автоматизации пользовательского интерфейса для типа элементов управления ToolTip</span><span class="sxs-lookup"><span data-stu-id="17e9a-152">UI Automation Support for the ToolTip Control Type</span></span>](ui-automation-support-for-the-tooltip-control-type.md)  
  
- [<span data-ttu-id="17e9a-153">Поддержка автоматизации пользовательского интерфейса для древовидного типа элемента управления</span><span class="sxs-lookup"><span data-stu-id="17e9a-153">UI Automation Support for the Tree Control Type</span></span>](ui-automation-support-for-the-tree-control-type.md)  
  
- [<span data-ttu-id="17e9a-154">Поддержка автоматизации пользовательского интерфейса для типа элемента управления TreeItem</span><span class="sxs-lookup"><span data-stu-id="17e9a-154">UI Automation Support for the TreeItem Control Type</span></span>](ui-automation-support-for-the-treeitem-control-type.md)  
  
- [<span data-ttu-id="17e9a-155">Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Window</span><span class="sxs-lookup"><span data-stu-id="17e9a-155">UI Automation Support for the Window Control Type</span></span>](ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="17e9a-156">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="17e9a-156">See also</span></span>

- <xref:System.Windows.Automation.ControlType>
