---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
description: Получение сведений о поддержке модели автоматизации пользовательского интерфейса для стандартных элементов управления в приложениях, разработанных для Windows Presentation Foundation (WPF), Win32 и Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 17916a6978008439e91caae00d8b6f26045f9018
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166121"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="8d0fb-103">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="8d0fb-103">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="8d0fb-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="8d0fb-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8d0fb-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8d0fb-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8d0fb-106">В этом разделе содержатся сведения о [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] поддержке стандартных элементов управления в приложениях, разработанных для [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] платформ, Win32 и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="8d0fb-107">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="8d0fb-107">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="8d0fb-108">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d0fb-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8d0fb-109">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d0fb-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="8d0fb-110">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-110">Win32 Controls</span></span>  
 <span data-ttu-id="8d0fb-111">Большинство элементов управления Win32 предоставляются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8d0fb-112">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8d0fb-113">Полная поддержка предоставляется только для элементов управления из *ComCtrl32.dll*версии 6.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="8d0fb-114">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8d0fb-115">Имя класса</span><span class="sxs-lookup"><span data-stu-id="8d0fb-115">Class name</span></span>|<span data-ttu-id="8d0fb-116">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="8d0fb-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8d0fb-117">Button</span><span class="sxs-lookup"><span data-stu-id="8d0fb-117">Button</span></span>|<span data-ttu-id="8d0fb-118">Button</span><span class="sxs-lookup"><span data-stu-id="8d0fb-118">Button</span></span>|  
|<span data-ttu-id="8d0fb-119">Button</span><span class="sxs-lookup"><span data-stu-id="8d0fb-119">Button</span></span>|<span data-ttu-id="8d0fb-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8d0fb-120">RadioButton</span></span>|  
|<span data-ttu-id="8d0fb-121">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-121">Button</span></span>|<span data-ttu-id="8d0fb-122">Группа</span><span class="sxs-lookup"><span data-stu-id="8d0fb-122">Group</span></span>|  
|<span data-ttu-id="8d0fb-123">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-123">Button</span></span>|<span data-ttu-id="8d0fb-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-124">CheckBox</span></span>|  
|<span data-ttu-id="8d0fb-125">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-125">Button</span></span>|<span data-ttu-id="8d0fb-126">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-126">Hyperlink</span></span>|  
|<span data-ttu-id="8d0fb-127">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-127">Button</span></span>|<span data-ttu-id="8d0fb-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="8d0fb-128">SplitButton</span></span>|  
|<span data-ttu-id="8d0fb-129">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-129">Button</span></span>|<span data-ttu-id="8d0fb-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-130">CheckBox</span></span>|  
|<span data-ttu-id="8d0fb-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-131">ComboBoxEx32</span></span>|<span data-ttu-id="8d0fb-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-132">ComboBox</span></span>|  
|<span data-ttu-id="8d0fb-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-133">ComboBox</span></span>|<span data-ttu-id="8d0fb-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-134">ComboBox</span></span>|  
|<span data-ttu-id="8d0fb-135">Изменить</span><span class="sxs-lookup"><span data-stu-id="8d0fb-135">Edit</span></span>|<span data-ttu-id="8d0fb-136">Документ</span><span class="sxs-lookup"><span data-stu-id="8d0fb-136">Document</span></span>|  
|<span data-ttu-id="8d0fb-137">Изменить</span><span class="sxs-lookup"><span data-stu-id="8d0fb-137">Edit</span></span>|<span data-ttu-id="8d0fb-138">Изменить</span><span class="sxs-lookup"><span data-stu-id="8d0fb-138">Edit</span></span>|  
|<span data-ttu-id="8d0fb-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="8d0fb-139">SysLink</span></span>|<span data-ttu-id="8d0fb-140">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-140">Hyperlink</span></span>|  
|<span data-ttu-id="8d0fb-141">Статические</span><span class="sxs-lookup"><span data-stu-id="8d0fb-141">Static</span></span>|<span data-ttu-id="8d0fb-142">Text</span><span class="sxs-lookup"><span data-stu-id="8d0fb-142">Text</span></span>|  
|<span data-ttu-id="8d0fb-143">Статические</span><span class="sxs-lookup"><span data-stu-id="8d0fb-143">Static</span></span>|<span data-ttu-id="8d0fb-144">Образ —</span><span class="sxs-lookup"><span data-stu-id="8d0fb-144">Image</span></span>|  
|<span data-ttu-id="8d0fb-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-145">SysIPAddress32</span></span>|<span data-ttu-id="8d0fb-146">Особые настройки</span><span class="sxs-lookup"><span data-stu-id="8d0fb-146">Custom</span></span>|  
|<span data-ttu-id="8d0fb-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-147">SysHeader32</span></span>|<span data-ttu-id="8d0fb-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="8d0fb-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="8d0fb-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-149">SysListView32</span></span>|<span data-ttu-id="8d0fb-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8d0fb-150">DataGrid</span></span>|  
|<span data-ttu-id="8d0fb-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-151">SysListView32</span></span>|<span data-ttu-id="8d0fb-152">Список</span><span class="sxs-lookup"><span data-stu-id="8d0fb-152">List</span></span>|  
|<span data-ttu-id="8d0fb-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-153">ListBox</span></span>|<span data-ttu-id="8d0fb-154">Список</span><span class="sxs-lookup"><span data-stu-id="8d0fb-154">List</span></span>|  
|<span data-ttu-id="8d0fb-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-155">ListBox</span></span>|<span data-ttu-id="8d0fb-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="8d0fb-156">ListItem</span></span>|  
|<span data-ttu-id="8d0fb-157">#32768</span><span class="sxs-lookup"><span data-stu-id="8d0fb-157">#32768</span></span>|<span data-ttu-id="8d0fb-158">Меню</span><span class="sxs-lookup"><span data-stu-id="8d0fb-158">Menu</span></span>|  
|<span data-ttu-id="8d0fb-159">#32768</span><span class="sxs-lookup"><span data-stu-id="8d0fb-159">#32768</span></span>|<span data-ttu-id="8d0fb-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8d0fb-160">MenuItem</span></span>|  
|<span data-ttu-id="8d0fb-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-161">msctls_progress32</span></span>|<span data-ttu-id="8d0fb-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-162">ProgressBar</span></span>|  
|<span data-ttu-id="8d0fb-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="8d0fb-163">RichEdit</span></span>|<span data-ttu-id="8d0fb-164">Документ.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-164">Document.</span></span> <span data-ttu-id="8d0fb-165">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-165">See note.</span></span>|  
|<span data-ttu-id="8d0fb-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="8d0fb-166">RichEdit20A</span></span>|<span data-ttu-id="8d0fb-167">Документ</span><span class="sxs-lookup"><span data-stu-id="8d0fb-167">Document</span></span>|  
|<span data-ttu-id="8d0fb-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="8d0fb-168">RichEdit20W</span></span>|<span data-ttu-id="8d0fb-169">Документ</span><span class="sxs-lookup"><span data-stu-id="8d0fb-169">Document</span></span>|  
|<span data-ttu-id="8d0fb-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="8d0fb-170">RichEdit50W</span></span>|<span data-ttu-id="8d0fb-171">Документ</span><span class="sxs-lookup"><span data-stu-id="8d0fb-171">Document</span></span>|  
|<span data-ttu-id="8d0fb-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-172">ScrollBar</span></span>|<span data-ttu-id="8d0fb-173">Ползунок</span><span class="sxs-lookup"><span data-stu-id="8d0fb-173">Slider</span></span>|  
|<span data-ttu-id="8d0fb-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-174">msctls_trackbar32</span></span>|<span data-ttu-id="8d0fb-175">Ползунок</span><span class="sxs-lookup"><span data-stu-id="8d0fb-175">Slider</span></span>|  
|<span data-ttu-id="8d0fb-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-176">msctls_updown32</span></span>|<span data-ttu-id="8d0fb-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="8d0fb-177">Spinner</span></span>|  
|<span data-ttu-id="8d0fb-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-178">msctls_statusbar32</span></span>|<span data-ttu-id="8d0fb-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-179">StatusBar</span></span>|  
|<span data-ttu-id="8d0fb-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-180">SysTabControl32</span></span>|<span data-ttu-id="8d0fb-181">Вкладка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-181">Tab</span></span>|  
|<span data-ttu-id="8d0fb-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-182">SysTabControl32</span></span>|<span data-ttu-id="8d0fb-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="8d0fb-183">TabItem</span></span>|  
|<span data-ttu-id="8d0fb-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-184">ToolbarWindow32</span></span>|<span data-ttu-id="8d0fb-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-185">ToolBar</span></span>|  
|<span data-ttu-id="8d0fb-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-186">ToolbarWindow32</span></span>|<span data-ttu-id="8d0fb-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8d0fb-187">MenuItem</span></span>|  
|<span data-ttu-id="8d0fb-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-188">ToolbarWindow32</span></span>|<span data-ttu-id="8d0fb-189">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-189">Button</span></span>|  
|<span data-ttu-id="8d0fb-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-190">ToolbarWindow32</span></span>|<span data-ttu-id="8d0fb-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-191">CheckBox</span></span>|  
|<span data-ttu-id="8d0fb-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-192">ToolbarWindow32</span></span>|<span data-ttu-id="8d0fb-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8d0fb-193">RadioButton</span></span>|  
|<span data-ttu-id="8d0fb-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-194">ToolbarWindow32</span></span>|<span data-ttu-id="8d0fb-195">Separator</span><span class="sxs-lookup"><span data-stu-id="8d0fb-195">Separator</span></span>|  
|<span data-ttu-id="8d0fb-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-196">tooltips_class32</span></span>|<span data-ttu-id="8d0fb-197">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8d0fb-197">ToolTip</span></span>|  
|<span data-ttu-id="8d0fb-198">#32774</span><span class="sxs-lookup"><span data-stu-id="8d0fb-198">#32774</span></span>|<span data-ttu-id="8d0fb-199">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8d0fb-199">ToolTip</span></span>|  
|<span data-ttu-id="8d0fb-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-200">ReBarWindow32</span></span>|<span data-ttu-id="8d0fb-201">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="8d0fb-201">Toolbar</span></span>|  
|<span data-ttu-id="8d0fb-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-202">SysTreeView32</span></span>|<span data-ttu-id="8d0fb-203">Дерево</span><span class="sxs-lookup"><span data-stu-id="8d0fb-203">Tree</span></span>|  
|<span data-ttu-id="8d0fb-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-204">SysTreeView32</span></span>|<span data-ttu-id="8d0fb-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="8d0fb-205">TreeItem</span></span>|  
  
 <span data-ttu-id="8d0fb-206">**Примечание** . Элемент управления RichEdit поддерживается только для версий, поставляемых с Windows Vista (в RichEd20.dll версии 3,1 и более поздних версий и MsftEdit.dll версии 4,1 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="8d0fb-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="8d0fb-207">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="8d0fb-208">Имя класса</span><span class="sxs-lookup"><span data-stu-id="8d0fb-208">Class name</span></span>|<span data-ttu-id="8d0fb-209">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="8d0fb-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8d0fb-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-210">SysAnimate32</span></span>|<span data-ttu-id="8d0fb-211">Образ —</span><span class="sxs-lookup"><span data-stu-id="8d0fb-211">Image</span></span>|  
|<span data-ttu-id="8d0fb-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="8d0fb-212">SysPager</span></span>|<span data-ttu-id="8d0fb-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="8d0fb-213">Spinner</span></span>|  
|<span data-ttu-id="8d0fb-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-214">SysDateTimePick32</span></span>|<span data-ttu-id="8d0fb-215">Особые настройки</span><span class="sxs-lookup"><span data-stu-id="8d0fb-215">Custom</span></span>|  
|<span data-ttu-id="8d0fb-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="8d0fb-216">SysMonthCal32</span></span>|<span data-ttu-id="8d0fb-217">"Календарь"</span><span class="sxs-lookup"><span data-stu-id="8d0fb-217">Calendar</span></span>|  
|<span data-ttu-id="8d0fb-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="8d0fb-218">MS_WINNOTE</span></span>|<span data-ttu-id="8d0fb-219">Всплывающая подсказка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-219">Tooltip</span></span>|  
|<span data-ttu-id="8d0fb-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="8d0fb-220">VBBubble</span></span>|<span data-ttu-id="8d0fb-221">Всплывающая подсказка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-221">Tooltip</span></span>|  
|<span data-ttu-id="8d0fb-222">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="8d0fb-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="8d0fb-223">Ползунок</span><span class="sxs-lookup"><span data-stu-id="8d0fb-223">Slider</span></span>|  
|<span data-ttu-id="8d0fb-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="8d0fb-224">SuperGrid</span></span>|<span data-ttu-id="8d0fb-225">Особые настройки</span><span class="sxs-lookup"><span data-stu-id="8d0fb-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="8d0fb-226">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d0fb-226">Windows Forms Controls</span></span>  
 <span data-ttu-id="8d0fb-227">Windows Forms элементы управления предоставляются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8d0fb-228">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8d0fb-229">Как правило, элементы управления Windows Forms, являющиеся управляемыми оболочками для общих элементов управления Win32, поддерживаются [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d0fb-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8d0fb-230">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8d0fb-231">Имя класса</span><span class="sxs-lookup"><span data-stu-id="8d0fb-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="8d0fb-232">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-232">Button</span></span>|  
|<span data-ttu-id="8d0fb-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-233">CheckBox</span></span>|  
|<span data-ttu-id="8d0fb-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-234">CheckedListBox</span></span>|  
|<span data-ttu-id="8d0fb-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="8d0fb-235">ColorDialog</span></span>|  
|<span data-ttu-id="8d0fb-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-236">ComboBox</span></span>|  
|<span data-ttu-id="8d0fb-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="8d0fb-237">FolderBrowser</span></span>|  
|<span data-ttu-id="8d0fb-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="8d0fb-238">FontDialog</span></span>|  
|<span data-ttu-id="8d0fb-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-239">GroupBox</span></span>|  
|<span data-ttu-id="8d0fb-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-240">HscrollBar</span></span>|  
|<span data-ttu-id="8d0fb-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="8d0fb-241">ImageList</span></span>|  
|<span data-ttu-id="8d0fb-242">Метка</span><span class="sxs-lookup"><span data-stu-id="8d0fb-242">Label</span></span>|  
|<span data-ttu-id="8d0fb-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-243">ListBox</span></span>|  
|<span data-ttu-id="8d0fb-244">ListView</span><span class="sxs-lookup"><span data-stu-id="8d0fb-244">ListView</span></span>|  
|<span data-ttu-id="8d0fb-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="8d0fb-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="8d0fb-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-246">MonthCalendar</span></span>|  
|<span data-ttu-id="8d0fb-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="8d0fb-247">NotifyIcon</span></span>|  
|<span data-ttu-id="8d0fb-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="8d0fb-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="8d0fb-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="8d0fb-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="8d0fb-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="8d0fb-250">PrintDialog</span></span>|  
|<span data-ttu-id="8d0fb-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-251">ProgressBar</span></span>|  
|<span data-ttu-id="8d0fb-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8d0fb-252">RadioButton</span></span>|  
|<span data-ttu-id="8d0fb-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-253">RichTextBox</span></span>|  
|<span data-ttu-id="8d0fb-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="8d0fb-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="8d0fb-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="8d0fb-255">ScrollableControl</span></span>|  
|<span data-ttu-id="8d0fb-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="8d0fb-256">SoundPlayer</span></span>|  
|<span data-ttu-id="8d0fb-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-257">StatusBar</span></span>|  
|<span data-ttu-id="8d0fb-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="8d0fb-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="8d0fb-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-259">TextBox</span></span>|  
|<span data-ttu-id="8d0fb-260">Таймер</span><span class="sxs-lookup"><span data-stu-id="8d0fb-260">Timer</span></span>|  
|<span data-ttu-id="8d0fb-261">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="8d0fb-261">Toolbar</span></span>|  
|<span data-ttu-id="8d0fb-262">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8d0fb-262">ToolTip</span></span>|  
|<span data-ttu-id="8d0fb-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-263">TrackBar</span></span>|  
|<span data-ttu-id="8d0fb-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="8d0fb-264">TreeView</span></span>|  
|<span data-ttu-id="8d0fb-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="8d0fb-265">VscrollBar</span></span>|  
|<span data-ttu-id="8d0fb-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="8d0fb-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="8d0fb-267">Следующие элементы управления доступны [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через поддержку Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="8d0fb-268">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="8d0fb-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="8d0fb-269">Название элемента управления</span><span class="sxs-lookup"><span data-stu-id="8d0fb-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="8d0fb-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="8d0fb-270">BindingSource</span></span>|  
|<span data-ttu-id="8d0fb-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8d0fb-271">DataGrid</span></span>|  
|<span data-ttu-id="8d0fb-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="8d0fb-272">DataGridView</span></span>|  
|<span data-ttu-id="8d0fb-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="8d0fb-273">DataNavigator</span></span>|  
|<span data-ttu-id="8d0fb-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="8d0fb-274">DomainUpDown</span></span>|  
|<span data-ttu-id="8d0fb-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="8d0fb-275">ErrorProvider</span></span>|  
|<span data-ttu-id="8d0fb-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8d0fb-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="8d0fb-277">Form</span><span class="sxs-lookup"><span data-stu-id="8d0fb-277">Form</span></span>|  
|<span data-ttu-id="8d0fb-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="8d0fb-278">LinkLabel</span></span>|  
|<span data-ttu-id="8d0fb-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="8d0fb-279">HelpProvider</span></span>|  
|<span data-ttu-id="8d0fb-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="8d0fb-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="8d0fb-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="8d0fb-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="8d0fb-282">NumericUpDown</span></span>|  
|<span data-ttu-id="8d0fb-283">Panel</span><span class="sxs-lookup"><span data-stu-id="8d0fb-283">Panel</span></span>|  
|<span data-ttu-id="8d0fb-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="8d0fb-284">PictureBox</span></span>|  
|<span data-ttu-id="8d0fb-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="8d0fb-285">PrintDocument</span></span>|  
|<span data-ttu-id="8d0fb-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="8d0fb-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="8d0fb-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="8d0fb-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="8d0fb-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="8d0fb-288">PropertyGrid</span></span>|  
|<span data-ttu-id="8d0fb-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="8d0fb-289">UserControl</span></span>|  
|<span data-ttu-id="8d0fb-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8d0fb-290">ToolStrip</span></span>|  
|<span data-ttu-id="8d0fb-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8d0fb-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="8d0fb-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="8d0fb-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="8d0fb-293">Разделитель</span><span class="sxs-lookup"><span data-stu-id="8d0fb-293">Splitter</span></span>|  
|<span data-ttu-id="8d0fb-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="8d0fb-294">RaftingContainer</span></span>|  
|<span data-ttu-id="8d0fb-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="8d0fb-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d0fb-296">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8d0fb-296">See also</span></span>

- [<span data-ttu-id="8d0fb-297">Типы элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="8d0fb-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
