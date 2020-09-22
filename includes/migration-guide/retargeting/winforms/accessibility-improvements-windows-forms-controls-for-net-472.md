---
ms.openlocfilehash: a21824862d6cad046b5d6186f9d6db9c20438304
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606745"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-472"></a>Улучшения специальных возможностей для элементов управления Windows Forms в .NET Framework 4.7.2

#### <a name="details"></a>Подробнее

В платформе Windows Forms улучшено использование специальных возможностей, обеспечивающих большее удобство для пользователей Windows Forms. Внесены следующие изменения:

- Изменения для улучшения видимости в режиме высокой контрастности.
- Изменения для улучшения навигации с помощью клавиатуры в элементах управления DataGridView и MenuStrip.
- Изменения в порядке взаимодействия с экранным диктором.

#### <a name="suggestion"></a>Предложение

**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:

- Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.2. Эти специальные возможности включены по умолчанию для приложений Windows Forms, предназначенных для .NET Framework 4.7.2 или более поздней версии.
- Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения и получения значения `false`, как показано в следующем примере.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
  </runtime>
</configuration>
```

Обратите внимание, что для включения использования специальных возможностей, добавленных в .NET Framework 4.7.2, необходимо также включить специальные возможности платформы .NET Framework 4.7.1. В приложениях, предназначенных для .NET Framework 4.7.2 или более поздней версии, где требуется сохранить предыдущие функции специальных возможностей, можно выбрать прежние функции специальных возможностей, явно установив этот переключатель AppContext в значение `true`.

**Использование определенных в ОС цветов в темах высокой контрастности**

- Для кнопки со стрелкой раскрывающегося меню <xref:System.Windows.Forms.ToolStripDropDownButton> теперь используются определенные операционной системой цвета в теме высокой контрастности.
- Элементы управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox>, для которых свойству <xref:System.Windows.Forms.ButtonBase.FlatStyle> присвоено значение <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> или <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>, теперь используют определенные в ОС цвета при выборе темы высокой контрастности. Ранее цвета текста и фона не были контрастными, что ухудшало разборчивость.
- Для элементов управления, содержащихся в <xref:System.Windows.Forms.GroupBox>, для свойства <xref:System.Windows.Forms.Control.Enabled> которого задано значение `false`, теперь используются определенные в ОС цвета в теме высокой контрастности.
- Элементы управления <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> и <xref:System.Windows.Forms.ToolStripDropDownButton> имеют повышенное значение контрастности яркости в режиме высокой контрастности.
- <xref:System.Windows.Forms.DataGridViewLinkCell> по умолчанию будет использовать определяемые операционной системой цвета в режиме высокой контрастности для свойства <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType>.
Примечание. В Windows 10 изменены значения некоторых системных цветов для тем высокой контрастности. Платформа Windows Forms Framework построена на основе Win32. Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав следующий код:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Улучшенная поддержка экранного диктора**

- Экранный диктор теперь сообщает значение свойства <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> при объявлении текста <xref:System.Windows.Forms.ToolStripMenuItem>.
- Экранный диктор теперь указывает, когда для свойства <xref:System.Windows.Forms.Control.Enabled> элемента <xref:System.Windows.Forms.ToolStripMenuItem> задано значение `false`.
- Экранный диктор теперь предоставляет отзыв о состоянии флажка, если для свойства <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> задано значение `true`.
- Порядок фокуса экранного диктора теперь согласуется с визуальным порядком элементов управления в диалоговом окне загрузки ClickOnce.

**Улучшенная поддержка специальных возможностей DataGridView**

- Строки в <xref:System.Windows.Forms.DataGridView> теперь могут быть отсортированы с помощью клавиатуры. Теперь пользователь может использовать клавишу F3, чтобы выполнить сортировку по текущему столбцу.
- Когда <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, заголовок столбца меняет цвет для указания на текущий столбец, когда пользователь переходит по ячейкам в текущей строке.
- Свойство <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> теперь возвращает правильный родительский элемент управления.

**Улучшенные визуальные подсказки**

- Элементы управления <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox> с пустым свойством <xref:System.Windows.Forms.ButtonBase.Text> будут отображать индикатор фокуса при получении фокуса.

**Улучшенная поддержка сетки свойств**

- Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> теперь возвращают `true` для <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> свойства только в том случае, если включен элемент PropertyGrid.
- Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> теперь возвращают `false` для <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> свойства только в том случае, если элемент PropertyGrid может быть изменен пользователем.
Обзор автоматизации пользовательского интерфейса см. в разделе [Общие сведения об автоматизации пользовательского интерфейса](../../../../docs/framework/ui-automation/ui-automation-overview.md).</p>**Улучшение навигации с помощью клавиатуры**

- <xref:System.Windows.Forms.ToolStripButton> теперь позволяет отображать фокус, если он содержится в <xref:System.Windows.Forms.ToolStripPanel>, для свойства <xref:System.Windows.Forms.ToolStripPanel.TabStop> которого задано значение `true`.

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
