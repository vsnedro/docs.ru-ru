---
ms.openlocfilehash: fa24c664e9f7cf6da78d0703c7ebb52c8ebbec20
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606162"
---
### <a name="accessibility-improvements-in-windows-forms-controls"></a>Улучшения специальных возможностей для элементов управления Windows Forms

#### <a name="details"></a>Подробнее

В Windows Forms улучшено использование специальных возможностей, обеспечивающих большее удобство для пользователей Windows Forms. К ним относятся следующие изменения, начиная с .NET Framework 4.7.1:

- Изменения для улучшения видимости в режиме высокой контрастности.
- Изменения для улучшения работы с обозревателем свойств. Список усовершенствований обозревателя свойств включает:
- Улучшенная навигация с помощью клавиатуры посредством различных окон выбора с раскрывающимися списками.
- Уменьшение числа ненужных позиций табуляции.
- Улучшенные отчеты о типах элементов управления.
- Улучшенная работа экранного диктора.
- Изменения в реализации отсутствующих шаблонов специальных возможностей пользовательского интерфейса в элементах управления.

#### <a name="suggestion"></a>Предложение

**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.1 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:

- Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.1. Эти специальные возможности включены по умолчанию для приложений Windows Forms, ориентированных на .NET Framework 4.7.1 или более поздней версии.
- Для отказа от функций специальных возможностей предыдущих версий [переключатель AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) добавляется в раздел `<runtime>` файла конфигурации приложения и получает значение `false`, как показано в следующем примере.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, где требуется сохранить предыдущие функции специальных возможностей, можно выбрать прежние функции специальных возможностей, явно установив этот переключатель AppContext в значение `true`.<p/>Обзор автоматизации пользовательского интерфейса см. в разделе [Общие сведения об автоматизации пользовательского интерфейса](~/docs/framework/ui-automation/ui-automation-overview.md).<p/>**Добавлена поддержка шаблонов и свойств автоматизации пользовательского интерфейса**<br/>Клиенты специальных возможностей могут использовать новые функции WinForms с помощью общедоступных и описанных шаблонов вызова. Эти шаблоны предназначены не только для WinForms. Например, клиенты специальных возможностей могут вызывать метод QueryInterface для интерфейса IAccessible (MAAS), чтобы получить интерфейс IServiceProvider. Если этот интерфейс доступен, клиенты могут использовать его метод QueryService для запроса интерфейса IAccessibleEx. Дополнительные сведения см. в разделе [Использование интерфейса IAccessibleEx из клиента](/windows/desktop/WinAuto/using-iaccessibleex-from-a-client). Начиная с версии .NET Framework 4.7.1 интерфейсы IServiceProvider и [IAccessibleEx](/windows/desktop/WinAuto/iaccessibleex) (где применимо) доступны объектам специальных возможностей WinForms.<p/>В .NET Framework 4.7.1 добавлена поддержка следующих шаблонов и свойств автоматизации пользовательского интерфейса:

- Элементы управления <xref:System.Windows.Forms.ToolStripSplitButton> и <xref:System.Windows.Forms.ComboBox> поддерживают [шаблон развертывания/свертывания](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Элемент управления <xref:System.Windows.Forms.ToolStripMenuItem> использует для свойства [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) значение <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- Элемент управления <xref:System.Windows.Forms.ToolStripItem> поддерживает свойство <xref:System.Windows.Automation.AutomationElement.NameProperty> и [шаблон развертывания/свертывания](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Элемент управления <xref:System.Windows.Forms.ToolStripDropDownItem> поддерживает <xref:System.Windows.Forms.AccessibleEvents> с указанием StateChange и NameChange при развертывании или свертывании раскрывающегося списка.
- Элемент управления <xref:System.Windows.Forms.ToolStripDropDownButton> использует для свойства [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) значение <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- Элемент управления <xref:System.Windows.Forms.DataGridViewCheckBoxCell> поддерживает <xref:System.Windows.Automation.TogglePattern>.
- Элементы управления <xref:System.Windows.Forms.NumericUpDown> и <xref:System.Windows.Forms.DomainUpDown> поддерживают свойство <xref:System.Windows.Automation.AutomationElement.NameProperty> и используют для [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md) значение <xref:System.Windows.Automation.ControlType.Spinner?displayProperty=nameWithType>.</p>
**Улучшения элемента управления PropertyGrid** В .NET Framework 4.7.1 добавлены следующие улучшения браузерного элемента управления PropertyBrowser:

- Кнопка **Подробнее** в диалоговом окне ошибки, которое появляется при вводе пользователем неверного значения в элемент управления <xref:System.Windows.Forms.PropertyGrid>, поддерживает [шаблон развертывания/свертывания](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md), уведомления об изменении имени и состояния, а также свойство [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) со значением <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- Область сообщений, которая отображается при развертывании кнопки **Подробнее** в диалоговом окне ошибки, теперь доступна с клавиатуры и поддерживает объявление содержимого сообщения об ошибке с помощью экранного диктора.
- Значение <xref:System.Windows.Forms.AccessibleRole> для строк в элементе управления <xref:System.Windows.Forms.PropertyGrid> изменилось со &quot;Строка&quot; на &quot;Ячейка&quot;. Ячейка сопоставляется с типом элемента управления &quot;DataItem&quot; модели автоматизации пользовательского интерфейса, благодаря чему обеспечивается поддержка соответствующих сочетаний клавиш и объявлений экранного диктора.
- Строки элемента управления <xref:System.Windows.Forms.PropertyGrid>, которые представляют элементы заголовка в том случае, если для элемента управления <xref:System.Windows.Forms.PropertyGrid> свойство <xref:System.Windows.Forms.PropertyGrid.PropertySort> имеет значение <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType>, имеют значение свойства [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md), равное <xref:System.Windows.Automation.ControlType.Button?displayProperty=nameWithType>.
- Строки элемента управления <xref:System.Windows.Forms.PropertyGrid>, которые представляют элементы заголовка в том случае, если для элемента управления <xref:System.Windows.Forms.PropertyGrid> свойство <xref:System.Windows.Forms.PropertyGrid.PropertySort> имеет значение <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType>, поддерживают [шаблон развертывания/свертывания](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Улучшена навигация с помощью клавиатуры между сеткой и расположенной над ней панелью инструментов. При нажатии клавиш &quot;SHIFT+TAB&quot; теперь выбирается не вся панель инструментов, а только ее первая кнопка.
- Элементы управления <xref:System.Windows.Forms.PropertyGrid>, отображаемые в режиме высокой контрастности, теперь отрисовывают прямоугольник фокуса вокруг кнопки панели инструментов, которая соответствует текущему значению свойства <xref:System.Windows.Forms.PropertyGrid.PropertySort>.
- Элементы управления <xref:System.Windows.Forms.PropertyGrid>, которые отображаются в режиме высокой контрастности и имеют свойство <xref:System.Windows.Forms.PropertyGrid.PropertySort>, равное <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType>, теперь используют цвет высокой контрастности для отображения фона заголовков категорий.
- Элементы управления <xref:System.Windows.Forms.PropertyGrid> обеспечивают более заметные различия между находящимися в фокусе элементами панели инструментов и теми элементами панели инструментов, которые указывают текущее значение свойства <xref:System.Windows.Forms.PropertyGrid.PropertySort>. Это исправление включает в себя изменение режима высокой контрастности, а также изменения других сценариев.
- Элементы панели инструментов для элемента управления <xref:System.Windows.Forms.PropertyGrid>, которые указывают текущее значение свойства <xref:System.Windows.Forms.PropertyGrid.PropertySort>, поддерживают <xref:System.Windows.Automation.TogglePattern>.
- Улучшенная поддержка экранного диктора для различения выбранного режима выравнивания в соответствующем средстве.
- Если в форме отображается пустой элемент управления <xref:System.Windows.Forms.PropertyGrid>, он будет получать фокус в тех случаях, в которых это ранее не происходило.

**Использование определенных в ОС цветов в темах высокой контрастности**

- Элементы управления <xref:System.Windows.Forms.Button> и <xref:System.Windows.Forms.CheckBox>, для которых свойству <xref:System.Windows.Forms.ButtonBase.FlatStyle> присвоено значение <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType> (стиль по умолчанию), теперь используют определенные в ОС цвета при выборе темы высокой контрастности. Ранее цвета текста и фона не были контрастными, что ухудшало разборчивость.
- Элементы управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.LinkLabel> и <xref:System.Windows.Forms.GroupBox>, для которых свойству <xref:System.Windows.Forms.Control.Enabled> присвоено значение **false**, использовали затененный цвет для отображения текста в темах высокой контрастности, в результате чего не обеспечивался достаточный контраст между текстом и фоном. Теперь для этих элементов управления используется цвет &quot;Выключенный текст&quot;, определенный в ОС. Это исправление применяется к элементам управления, для которых свойству `FlatStyle` присвоено значение, отличное от <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>. Последние элементы управления отображаются операционной системой.
- <xref:System.Windows.Forms.DataGridView> теперь отображает видимый прямоугольник вокруг содержимого ячейки, в которой в данный момент установлен фокус. Ранее в некоторых темах высокой контрастности этот прямоугольник был незаметен.
- Элементы управления <xref:System.Windows.Forms.ToolStripMenuItem>, для которых свойству <xref:System.Windows.Forms.ToolStripMenuItem.Enabled> присвоено значение **false**, теперь используют цвет &quot;Выключенный текст&quot;, определенный в ОС.
- Элементы управления <xref:System.Windows.Forms.ToolStripMenuItem>, для которых свойству <xref:System.Windows.Forms.ToolStripMenuItem.Checked> присвоено значение **true**, теперь отображают соответствующий флажок с использованием контрастного системного цвета.  Ранее цвет флажка был недостаточно контрастным, в результате чего он был не виден в некоторых темах высокой контрастности.
Примечание. В Windows 10 изменены значения некоторых системных цветов для тем высокой контрастности. Платформа Windows Forms Framework построена на основе Win32. Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав следующий код:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Улучшение навигации с помощью клавиатуры**

- Если для элемента управления <xref:System.Windows.Forms.ComboBox> свойство <xref:System.Windows.Forms.ComboBox.DropDownStyle> имеет значение <xref:System.Windows.Forms.ComboBoxStyle.DropDownList?displayProperty=nameWithType> и он является первым элементом управления на вкладке формы, при открытии родительской формы с помощью клавиатуры он теперь отображает прямоугольник фокуса. До этого изменения фокус устанавливался в этот элемент управления, однако индикатор фокуса не отображался.

**Улучшенная поддержка экранного диктора**

- Для элемента управления <xref:System.Windows.Forms.MonthCalendar> добавлена поддержка вспомогательных технологий, обеспечивающих доступ к элементу управления, в том числе возможность объявления значения элемента управления с помощью экранного диктора, которая ранее отсутствовала.

- Элемент управления <xref:System.Windows.Forms.CheckedListBox> теперь направляет в экранный диктор уведомления об изменении свойства <xref:System.Windows.Forms.CheckBox.CheckState?displayProperty=nameWithType>. Ранее экранный диктор не получал уведомления, в результате чего пользователи на знали об обновлении свойства <xref:System.Windows.Forms.CheckBox.CheckState>.
- Для элемента управления <xref:System.Windows.Forms.LinkLabel> изменился способ уведомления экранного диктора о тексте элемента управления. Ранее экранный диктор объявлял этот текст дважды и читал символы &quot;&amp;&quot; как реальный текст, хотя они не были видны пользователю. Из объявлений экранного диктора исключены ненужные символы &quot;&amp;&quot; и повторяющийся текст.
- Типы элемента управления <xref:System.Windows.Forms.DataGridViewCell> теперь корректно сообщают о состоянии только для чтения экранному диктору и другим вспомогательным технологиям.
- Экранный диктор теперь может считывать системное меню дочерних окон в приложении [Multiple-Document Interface]~/docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md).
- Экранный диктор теперь может читать элементы управления <xref:System.Windows.Forms.ToolStripMenuItem>, для которых свойству <xref:System.Windows.Forms.ToolStripItem.Enabled?displayProperty=nameWithType> присвоено значение **false**. Ранее экранный диктор не мог получить фокус для отключенных пунктов меню, чтобы считывать их содержимое.

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.8         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.ToolStripDropDownButton.CreateAccessibilityInstance?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownAccessibleObject.Name?displayProperty=nameWithType>
- [MonthCalendar.AccessibilityObject](xref:System.Windows.Forms.Control.AccessibilityObject)
