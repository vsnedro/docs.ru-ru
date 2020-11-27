---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
description: Получение сведений о поддержке модели автоматизации пользовательского интерфейса для стандартных элементов управления в приложениях, разработанных для Windows Presentation Foundation (WPF), Win32 и Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 0a5a0b61a6492d9efb62799fa610859b247cf26e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261076"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="9cb5c-103">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="9cb5c-103">UI Automation Support for Standard Controls</span></span>

> [!NOTE]
> <span data-ttu-id="9cb5c-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="9cb5c-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9cb5c-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="9cb5c-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="9cb5c-106">В этом разделе содержатся сведения о [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] поддержке стандартных элементов управления в приложениях, разработанных для [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] платформ, Win32 и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>

## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="9cb5c-107">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="9cb5c-107">Windows Presentation Foundation Controls</span></span>  

 <span data-ttu-id="9cb5c-108">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cb5c-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="9cb5c-109">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cb5c-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>

## <a name="win32-controls"></a><span data-ttu-id="9cb5c-110">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-110">Win32 Controls</span></span>  

 <span data-ttu-id="9cb5c-111">Большинство элементов управления Win32 предоставляются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="9cb5c-112">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="9cb5c-113">Полная поддержка предоставляется только для элементов управления из *ComCtrl32.dll* версии 6.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="9cb5c-114">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="9cb5c-115">Имя класса</span><span class="sxs-lookup"><span data-stu-id="9cb5c-115">Class name</span></span>|<span data-ttu-id="9cb5c-116">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="9cb5c-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="9cb5c-117">Button</span><span class="sxs-lookup"><span data-stu-id="9cb5c-117">Button</span></span>|<span data-ttu-id="9cb5c-118">Button</span><span class="sxs-lookup"><span data-stu-id="9cb5c-118">Button</span></span>|  
|<span data-ttu-id="9cb5c-119">Button</span><span class="sxs-lookup"><span data-stu-id="9cb5c-119">Button</span></span>|<span data-ttu-id="9cb5c-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="9cb5c-120">RadioButton</span></span>|  
|<span data-ttu-id="9cb5c-121">Кнопка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-121">Button</span></span>|<span data-ttu-id="9cb5c-122">Группа</span><span class="sxs-lookup"><span data-stu-id="9cb5c-122">Group</span></span>|  
|<span data-ttu-id="9cb5c-123">Кнопка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-123">Button</span></span>|<span data-ttu-id="9cb5c-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-124">CheckBox</span></span>|  
|<span data-ttu-id="9cb5c-125">Кнопка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-125">Button</span></span>|<span data-ttu-id="9cb5c-126">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-126">Hyperlink</span></span>|  
|<span data-ttu-id="9cb5c-127">Кнопка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-127">Button</span></span>|<span data-ttu-id="9cb5c-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="9cb5c-128">SplitButton</span></span>|  
|<span data-ttu-id="9cb5c-129">Кнопка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-129">Button</span></span>|<span data-ttu-id="9cb5c-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-130">CheckBox</span></span>|  
|<span data-ttu-id="9cb5c-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-131">ComboBoxEx32</span></span>|<span data-ttu-id="9cb5c-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-132">ComboBox</span></span>|  
|<span data-ttu-id="9cb5c-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-133">ComboBox</span></span>|<span data-ttu-id="9cb5c-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-134">ComboBox</span></span>|  
|<span data-ttu-id="9cb5c-135">Изменить</span><span class="sxs-lookup"><span data-stu-id="9cb5c-135">Edit</span></span>|<span data-ttu-id="9cb5c-136">Документ</span><span class="sxs-lookup"><span data-stu-id="9cb5c-136">Document</span></span>|  
|<span data-ttu-id="9cb5c-137">Изменить</span><span class="sxs-lookup"><span data-stu-id="9cb5c-137">Edit</span></span>|<span data-ttu-id="9cb5c-138">Изменить</span><span class="sxs-lookup"><span data-stu-id="9cb5c-138">Edit</span></span>|  
|<span data-ttu-id="9cb5c-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="9cb5c-139">SysLink</span></span>|<span data-ttu-id="9cb5c-140">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-140">Hyperlink</span></span>|  
|<span data-ttu-id="9cb5c-141">Статические</span><span class="sxs-lookup"><span data-stu-id="9cb5c-141">Static</span></span>|<span data-ttu-id="9cb5c-142">Текст</span><span class="sxs-lookup"><span data-stu-id="9cb5c-142">Text</span></span>|  
|<span data-ttu-id="9cb5c-143">Статические</span><span class="sxs-lookup"><span data-stu-id="9cb5c-143">Static</span></span>|<span data-ttu-id="9cb5c-144">Образ —</span><span class="sxs-lookup"><span data-stu-id="9cb5c-144">Image</span></span>|  
|<span data-ttu-id="9cb5c-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-145">SysIPAddress32</span></span>|<span data-ttu-id="9cb5c-146">Другой</span><span class="sxs-lookup"><span data-stu-id="9cb5c-146">Custom</span></span>|  
|<span data-ttu-id="9cb5c-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-147">SysHeader32</span></span>|<span data-ttu-id="9cb5c-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="9cb5c-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="9cb5c-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-149">SysListView32</span></span>|<span data-ttu-id="9cb5c-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="9cb5c-150">DataGrid</span></span>|  
|<span data-ttu-id="9cb5c-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-151">SysListView32</span></span>|<span data-ttu-id="9cb5c-152">Список</span><span class="sxs-lookup"><span data-stu-id="9cb5c-152">List</span></span>|  
|<span data-ttu-id="9cb5c-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-153">ListBox</span></span>|<span data-ttu-id="9cb5c-154">Список</span><span class="sxs-lookup"><span data-stu-id="9cb5c-154">List</span></span>|  
|<span data-ttu-id="9cb5c-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-155">ListBox</span></span>|<span data-ttu-id="9cb5c-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="9cb5c-156">ListItem</span></span>|  
|<span data-ttu-id="9cb5c-157">#32768</span><span class="sxs-lookup"><span data-stu-id="9cb5c-157">#32768</span></span>|<span data-ttu-id="9cb5c-158">Меню</span><span class="sxs-lookup"><span data-stu-id="9cb5c-158">Menu</span></span>|  
|<span data-ttu-id="9cb5c-159">#32768</span><span class="sxs-lookup"><span data-stu-id="9cb5c-159">#32768</span></span>|<span data-ttu-id="9cb5c-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="9cb5c-160">MenuItem</span></span>|  
|<span data-ttu-id="9cb5c-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-161">msctls_progress32</span></span>|<span data-ttu-id="9cb5c-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-162">ProgressBar</span></span>|  
|<span data-ttu-id="9cb5c-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="9cb5c-163">RichEdit</span></span>|<span data-ttu-id="9cb5c-164">Документ.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-164">Document.</span></span> <span data-ttu-id="9cb5c-165">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-165">See note.</span></span>|  
|<span data-ttu-id="9cb5c-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="9cb5c-166">RichEdit20A</span></span>|<span data-ttu-id="9cb5c-167">Документ</span><span class="sxs-lookup"><span data-stu-id="9cb5c-167">Document</span></span>|  
|<span data-ttu-id="9cb5c-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="9cb5c-168">RichEdit20W</span></span>|<span data-ttu-id="9cb5c-169">Документ</span><span class="sxs-lookup"><span data-stu-id="9cb5c-169">Document</span></span>|  
|<span data-ttu-id="9cb5c-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="9cb5c-170">RichEdit50W</span></span>|<span data-ttu-id="9cb5c-171">Документ</span><span class="sxs-lookup"><span data-stu-id="9cb5c-171">Document</span></span>|  
|<span data-ttu-id="9cb5c-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-172">ScrollBar</span></span>|<span data-ttu-id="9cb5c-173">Slider</span><span class="sxs-lookup"><span data-stu-id="9cb5c-173">Slider</span></span>|  
|<span data-ttu-id="9cb5c-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-174">msctls_trackbar32</span></span>|<span data-ttu-id="9cb5c-175">Slider</span><span class="sxs-lookup"><span data-stu-id="9cb5c-175">Slider</span></span>|  
|<span data-ttu-id="9cb5c-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-176">msctls_updown32</span></span>|<span data-ttu-id="9cb5c-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="9cb5c-177">Spinner</span></span>|  
|<span data-ttu-id="9cb5c-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-178">msctls_statusbar32</span></span>|<span data-ttu-id="9cb5c-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-179">StatusBar</span></span>|  
|<span data-ttu-id="9cb5c-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-180">SysTabControl32</span></span>|<span data-ttu-id="9cb5c-181">Вкладка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-181">Tab</span></span>|  
|<span data-ttu-id="9cb5c-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-182">SysTabControl32</span></span>|<span data-ttu-id="9cb5c-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="9cb5c-183">TabItem</span></span>|  
|<span data-ttu-id="9cb5c-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-184">ToolbarWindow32</span></span>|<span data-ttu-id="9cb5c-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-185">ToolBar</span></span>|  
|<span data-ttu-id="9cb5c-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-186">ToolbarWindow32</span></span>|<span data-ttu-id="9cb5c-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="9cb5c-187">MenuItem</span></span>|  
|<span data-ttu-id="9cb5c-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-188">ToolbarWindow32</span></span>|<span data-ttu-id="9cb5c-189">Кнопка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-189">Button</span></span>|  
|<span data-ttu-id="9cb5c-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-190">ToolbarWindow32</span></span>|<span data-ttu-id="9cb5c-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-191">CheckBox</span></span>|  
|<span data-ttu-id="9cb5c-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-192">ToolbarWindow32</span></span>|<span data-ttu-id="9cb5c-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="9cb5c-193">RadioButton</span></span>|  
|<span data-ttu-id="9cb5c-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-194">ToolbarWindow32</span></span>|<span data-ttu-id="9cb5c-195">Separator</span><span class="sxs-lookup"><span data-stu-id="9cb5c-195">Separator</span></span>|  
|<span data-ttu-id="9cb5c-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-196">tooltips_class32</span></span>|<span data-ttu-id="9cb5c-197">ToolTip</span><span class="sxs-lookup"><span data-stu-id="9cb5c-197">ToolTip</span></span>|  
|<span data-ttu-id="9cb5c-198">#32774</span><span class="sxs-lookup"><span data-stu-id="9cb5c-198">#32774</span></span>|<span data-ttu-id="9cb5c-199">ToolTip</span><span class="sxs-lookup"><span data-stu-id="9cb5c-199">ToolTip</span></span>|  
|<span data-ttu-id="9cb5c-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-200">ReBarWindow32</span></span>|<span data-ttu-id="9cb5c-201">Toolbar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-201">Toolbar</span></span>|  
|<span data-ttu-id="9cb5c-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-202">SysTreeView32</span></span>|<span data-ttu-id="9cb5c-203">Дерево</span><span class="sxs-lookup"><span data-stu-id="9cb5c-203">Tree</span></span>|  
|<span data-ttu-id="9cb5c-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-204">SysTreeView32</span></span>|<span data-ttu-id="9cb5c-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="9cb5c-205">TreeItem</span></span>|  
  
 <span data-ttu-id="9cb5c-206">**Примечание** . Элемент управления RichEdit поддерживается только для версий, поставляемых с Windows Vista (в RichEd20.dll версии 3,1 и более поздних версий и MsftEdit.dll версии 4,1 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="9cb5c-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="9cb5c-207">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="9cb5c-208">Имя класса</span><span class="sxs-lookup"><span data-stu-id="9cb5c-208">Class name</span></span>|<span data-ttu-id="9cb5c-209">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="9cb5c-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="9cb5c-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-210">SysAnimate32</span></span>|<span data-ttu-id="9cb5c-211">Образ —</span><span class="sxs-lookup"><span data-stu-id="9cb5c-211">Image</span></span>|  
|<span data-ttu-id="9cb5c-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="9cb5c-212">SysPager</span></span>|<span data-ttu-id="9cb5c-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="9cb5c-213">Spinner</span></span>|  
|<span data-ttu-id="9cb5c-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-214">SysDateTimePick32</span></span>|<span data-ttu-id="9cb5c-215">Другой</span><span class="sxs-lookup"><span data-stu-id="9cb5c-215">Custom</span></span>|  
|<span data-ttu-id="9cb5c-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="9cb5c-216">SysMonthCal32</span></span>|<span data-ttu-id="9cb5c-217">Календарь</span><span class="sxs-lookup"><span data-stu-id="9cb5c-217">Calendar</span></span>|  
|<span data-ttu-id="9cb5c-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="9cb5c-218">MS_WINNOTE</span></span>|<span data-ttu-id="9cb5c-219">Подсказка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-219">Tooltip</span></span>|  
|<span data-ttu-id="9cb5c-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="9cb5c-220">VBBubble</span></span>|<span data-ttu-id="9cb5c-221">Подсказка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-221">Tooltip</span></span>|  
|<span data-ttu-id="9cb5c-222">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="9cb5c-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="9cb5c-223">Slider</span><span class="sxs-lookup"><span data-stu-id="9cb5c-223">Slider</span></span>|  
|<span data-ttu-id="9cb5c-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="9cb5c-224">SuperGrid</span></span>|<span data-ttu-id="9cb5c-225">Другой</span><span class="sxs-lookup"><span data-stu-id="9cb5c-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>

## <a name="windows-forms-controls"></a><span data-ttu-id="9cb5c-226">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cb5c-226">Windows Forms Controls</span></span>  

 <span data-ttu-id="9cb5c-227">Windows Forms элементы управления предоставляются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="9cb5c-228">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="9cb5c-229">Как правило, элементы управления Windows Forms, являющиеся управляемыми оболочками для общих элементов управления Win32, поддерживаются [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9cb5c-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="9cb5c-230">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="9cb5c-231">Имя класса</span><span class="sxs-lookup"><span data-stu-id="9cb5c-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="9cb5c-232">Кнопка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-232">Button</span></span>|  
|<span data-ttu-id="9cb5c-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-233">CheckBox</span></span>|  
|<span data-ttu-id="9cb5c-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-234">CheckedListBox</span></span>|  
|<span data-ttu-id="9cb5c-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="9cb5c-235">ColorDialog</span></span>|  
|<span data-ttu-id="9cb5c-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-236">ComboBox</span></span>|  
|<span data-ttu-id="9cb5c-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="9cb5c-237">FolderBrowser</span></span>|  
|<span data-ttu-id="9cb5c-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="9cb5c-238">FontDialog</span></span>|  
|<span data-ttu-id="9cb5c-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-239">GroupBox</span></span>|  
|<span data-ttu-id="9cb5c-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-240">HscrollBar</span></span>|  
|<span data-ttu-id="9cb5c-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="9cb5c-241">ImageList</span></span>|  
|<span data-ttu-id="9cb5c-242">Метка</span><span class="sxs-lookup"><span data-stu-id="9cb5c-242">Label</span></span>|  
|<span data-ttu-id="9cb5c-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-243">ListBox</span></span>|  
|<span data-ttu-id="9cb5c-244">ListView</span><span class="sxs-lookup"><span data-stu-id="9cb5c-244">ListView</span></span>|  
|<span data-ttu-id="9cb5c-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="9cb5c-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="9cb5c-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-246">MonthCalendar</span></span>|  
|<span data-ttu-id="9cb5c-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="9cb5c-247">NotifyIcon</span></span>|  
|<span data-ttu-id="9cb5c-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="9cb5c-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="9cb5c-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="9cb5c-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="9cb5c-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="9cb5c-250">PrintDialog</span></span>|  
|<span data-ttu-id="9cb5c-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-251">ProgressBar</span></span>|  
|<span data-ttu-id="9cb5c-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="9cb5c-252">RadioButton</span></span>|  
|<span data-ttu-id="9cb5c-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-253">RichTextBox</span></span>|  
|<span data-ttu-id="9cb5c-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="9cb5c-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="9cb5c-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="9cb5c-255">ScrollableControl</span></span>|  
|<span data-ttu-id="9cb5c-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="9cb5c-256">SoundPlayer</span></span>|  
|<span data-ttu-id="9cb5c-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-257">StatusBar</span></span>|  
|<span data-ttu-id="9cb5c-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="9cb5c-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="9cb5c-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-259">TextBox</span></span>|  
|<span data-ttu-id="9cb5c-260">Таймер</span><span class="sxs-lookup"><span data-stu-id="9cb5c-260">Timer</span></span>|  
|<span data-ttu-id="9cb5c-261">Toolbar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-261">Toolbar</span></span>|  
|<span data-ttu-id="9cb5c-262">ToolTip</span><span class="sxs-lookup"><span data-stu-id="9cb5c-262">ToolTip</span></span>|  
|<span data-ttu-id="9cb5c-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-263">TrackBar</span></span>|  
|<span data-ttu-id="9cb5c-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="9cb5c-264">TreeView</span></span>|  
|<span data-ttu-id="9cb5c-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="9cb5c-265">VscrollBar</span></span>|  
|<span data-ttu-id="9cb5c-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="9cb5c-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="9cb5c-267">Следующие элементы управления доступны [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через поддержку Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="9cb5c-268">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="9cb5c-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="9cb5c-269">Название элемента управления</span><span class="sxs-lookup"><span data-stu-id="9cb5c-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="9cb5c-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="9cb5c-270">BindingSource</span></span>|  
|<span data-ttu-id="9cb5c-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="9cb5c-271">DataGrid</span></span>|  
|<span data-ttu-id="9cb5c-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="9cb5c-272">DataGridView</span></span>|  
|<span data-ttu-id="9cb5c-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="9cb5c-273">DataNavigator</span></span>|  
|<span data-ttu-id="9cb5c-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="9cb5c-274">DomainUpDown</span></span>|  
|<span data-ttu-id="9cb5c-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="9cb5c-275">ErrorProvider</span></span>|  
|<span data-ttu-id="9cb5c-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9cb5c-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="9cb5c-277">Form</span><span class="sxs-lookup"><span data-stu-id="9cb5c-277">Form</span></span>|  
|<span data-ttu-id="9cb5c-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="9cb5c-278">LinkLabel</span></span>|  
|<span data-ttu-id="9cb5c-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="9cb5c-279">HelpProvider</span></span>|  
|<span data-ttu-id="9cb5c-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="9cb5c-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="9cb5c-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="9cb5c-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="9cb5c-282">NumericUpDown</span></span>|  
|<span data-ttu-id="9cb5c-283">Panel</span><span class="sxs-lookup"><span data-stu-id="9cb5c-283">Panel</span></span>|  
|<span data-ttu-id="9cb5c-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="9cb5c-284">PictureBox</span></span>|  
|<span data-ttu-id="9cb5c-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="9cb5c-285">PrintDocument</span></span>|  
|<span data-ttu-id="9cb5c-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="9cb5c-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="9cb5c-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="9cb5c-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="9cb5c-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="9cb5c-288">PropertyGrid</span></span>|  
|<span data-ttu-id="9cb5c-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="9cb5c-289">UserControl</span></span>|  
|<span data-ttu-id="9cb5c-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9cb5c-290">ToolStrip</span></span>|  
|<span data-ttu-id="9cb5c-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9cb5c-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="9cb5c-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="9cb5c-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="9cb5c-293">Разделитель</span><span class="sxs-lookup"><span data-stu-id="9cb5c-293">Splitter</span></span>|  
|<span data-ttu-id="9cb5c-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="9cb5c-294">RaftingContainer</span></span>|  
|<span data-ttu-id="9cb5c-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="9cb5c-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cb5c-296">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb5c-296">See also</span></span>

- [<span data-ttu-id="9cb5c-297">Типы элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9cb5c-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
