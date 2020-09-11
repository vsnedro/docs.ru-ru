---
ms.openlocfilehash: 895d09e4ec39bd4a92ed1f4910da80474334d99b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496493"
---
### <a name="accessibility-improvements-in-wpf"></a>Улучшения специальных возможностей в WPF

#### <a name="details"></a>Подробнее

**Улучшения режима высокой контрастности**

- Фокус для элемента управления <xref:System.Windows.Controls.Expander> теперь отображается. В предыдущих версиях .NET Framework это было не так.
- При выборе элементов управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> текст в них более удобен для восприятия по сравнению с предыдущими версиями .NET Framework.
- Граница отключенного элемента <xref:System.Windows.Controls.ComboBox> теперь отображается тем же цветом, что и его текст. В предыдущих версиях .NET Framework это было не так.
- Отключенные и находящиеся в фокусе кнопки теперь используют правильный цвет темы. В предыдущих версиях .NET Framework это было не так.
- Теперь, когда для стиля элемента управления <xref:System.Windows.Controls.ComboBox> задано значение <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>, отображается кнопка раскрывающегося списка. В предыдущих версиях .NET Framework это было не так.
- Для индикатора стрелки направления сортировки в элементе управления <xref:System.Windows.Controls.DataGrid> теперь используются цвета темы. В предыдущих версиях .NET Framework это было не так.
- Стиль по умолчанию для гиперссылки теперь изменяется на соответствующий цвет темы при наведении указателя мыши. В предыдущих версиях .NET Framework это было не так.
- Теперь отображается фокус клавиатуры на переключателях. В предыдущих версиях .NET Framework это было не так.
- Для столбца флажков элемента управления <xref:System.Windows.Controls.DataGrid> теперь используются соответствующие цвета, отражающие фокус клавиатуры. В предыдущих версиях .NET Framework это было не так.
- Визуальные элементы фокуса клавиатуры теперь отображаются на элементах управления <xref:System.Windows.Controls.ComboBox> и <xref:System.Windows.Controls.ListBox>. В предыдущих версиях .NET Framework это было не так.

**Улучшения взаимодействия со средством чтения с экрана**

- Средства чтения с экрана теперь правильно объявляют элементы управления <xref:System.Windows.Controls.Expander> как группы (развертывание/свертывание).
- Средства чтения с экрана теперь правильно объявляют элементы управления <xref:System.Windows.Controls.DataGridCell> как ячейки сетки данных (локализованные).
- Средства чтения с экрана теперь объявляют имя редактируемого элемента управления <xref:System.Windows.Controls.ComboBox>.
- Элементы управления <xref:System.Windows.Controls.PasswordBox> больше не объявляются с ошибкой «Не выбран элемент для просмотра» в средствах чтения с экрана.

**Поддержка динамических областей**

Средства чтения с экрана, такие как экранный диктор, помогают людям понять пользовательский интерфейс приложения, обычно путем описания элемента пользовательского интерфейса, который в данный момент находится в фокусе. Однако если элемент пользовательского интерфейса изменяется в каком-либо месте экрана и находится не в фокусе, пользователь может не получить уведомление и пропустить важные сведения. Решить эту проблему позволяет применение динамических областей. Разработчик может использовать их для информирования средства чтения с экрана или любого другого клиента [автоматизации пользовательского интерфейса](~/docs/framework/ui-automation/ui-automation-overview.md) о важных изменениях элемента пользовательского интерфейса. После этого средство чтения с экрана может решить, уведомлять ли пользователя об этом изменении. Свойство LiveSetting также позволяет средствам чтения с экрана узнать, насколько важно информировать пользователя о произошедшем в пользовательском интерфейсе изменении.

#### <a name="suggestion"></a>Предложение

**Как принять или отклонить изменения**

Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.1 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:

- Целевая платформа .NET Framework 4.7.1. Этот способ является рекомендуемым. Эти специальные возможности включены по умолчанию для приложений WPF, ориентированных на .NET Framework 4.7.1 или более поздней версии.
- Для отказа от функций специальных возможностей предыдущих версий [переключатель AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) добавляется в раздел `<runtime>` файла конфигурации приложения и получает значение `false`, как показано в следующем примере.

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
    </startup>
    <runtime>
      <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
    </runtime>
  </configuration>
  ```

В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, где требуется сохранить предыдущие функции специальных возможностей, можно выбрать прежние функции специальных возможностей, явно установив этот переключатель AppContext в значение `true`.
Обзор автоматизации пользовательского интерфейса см. в разделе [Общие сведения об автоматизации пользовательского интерфейса](~/docs/framework/ui-automation/ui-automation-overview.md).

| Имя    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.7.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType>
