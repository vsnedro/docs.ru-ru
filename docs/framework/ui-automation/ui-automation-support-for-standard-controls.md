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
# <a name="ui-automation-support-for-standard-controls"></a>Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] поддержке стандартных элементов управления в приложениях, разработанных для [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] платформ, Win32 и Windows Forms.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a>Элементы представления Windows Presentation Foundation  
 Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a>Элементы управления Win32  
 Большинство элементов управления Win32 предоставляются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Полная поддержка предоставляется только для элементов управления из *ComCtrl32.dll*версии 6.  
  
 Поддерживаются следующие элементы управления.  
  
|Имя класса|Тип элемента управления|  
|----------------|------------------|  
|Button|Button|  
|Button|RadioButton|  
|Кнопка|Группа|  
|Кнопка|CheckBox|  
|Кнопка|Гиперссылка|  
|Кнопка|SplitButton|  
|Кнопка|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Изменить|Документ|  
|Изменить|Изменить|  
|SysLink|Гиперссылка|  
|Статические|Text|  
|Статические|Образ —|  
|SysIPAddress32|Особые настройки|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|Список|  
|ListBox|Список|  
|ListBox|ListItem|  
|#32768|Меню|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Документ. См. примечание.|  
|RichEdit20A|Документ|  
|RichEdit20W|Документ|  
|RichEdit50W|Документ|  
|ScrollBar|Ползунок|  
|msctls_trackbar32|Ползунок|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Вкладка|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Кнопка|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separator|  
|tooltips_class32|ToolTip|  
|#32774|ToolTip|  
|ReBarWindow32|Панель инструментов|  
|SysTreeView32|Дерево|  
|SysTreeView32|TreeItem|  
  
 **Примечание** . Элемент управления RichEdit поддерживается только для версий, поставляемых с Windows Vista (в RichEd20.dll версии 3,1 и более поздних версий и MsftEdit.dll версии 4,1 и более поздних версий).  
  
 Следующие элементы управления не поддерживаются.  
  
|Имя класса|Тип элемента управления|  
|----------------|------------------|  
|SysAnimate32|Образ —|  
|SysPager|Spinner|  
|SysDateTimePick32|Особые настройки|  
|SysMonthCal32|"Календарь"|  
|MS_WINNOTE|Всплывающая подсказка|  
|VBBubble|Всплывающая подсказка|  
|ScrollBar (при использовании в качестве отдельного элемента управления)|Ползунок|  
|SuperGrid|Особые настройки|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a>Элементы управления Windows Forms  
 Windows Forms элементы управления предоставляются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Как правило, элементы управления Windows Forms, являющиеся управляемыми оболочками для общих элементов управления Win32, поддерживаются [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Поддерживаются следующие элементы управления.  
  
|Имя класса|  
|----------------|  
|Кнопка|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|Метка|  
|ListBox|  
|ListView|  
|MainMenu/ContextMenu|  
|MonthCalendar|  
|NotifyIcon|  
|OpenFileDialog|  
|PageSetupDialog|  
|PrintDialog|  
|ProgressBar|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|TextBox|  
|Таймер|  
|Панель инструментов|  
|ToolTip|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|WebBrowser|  
  
 Следующие элементы управления доступны [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через поддержку Microsoft Active Accessibility. Некоторые функциональные возможности могут оказаться недоступными.  
  
|Название элемента управления|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Form|  
|LinkLabel|  
|HelpProvider|  
|MaskedTextBox|  
|MenuStrip/ContextMenuStrip|  
|NumericUpDown|  
|Panel|  
|PictureBox|  
|PrintDocument|  
|PrintPreview-Control|  
|PrintPreview-Dialog|  
|PropertyGrid|  
|UserControl|  
|ToolStrip|  
|TableLayoutPanel|  
|SplitContainer/SplitterPanel|  
|Разделитель|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>См. также раздел

- [Типы элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types.md)
