---
title: Windows Forms добавить элемент конфигурации
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
ms.openlocfilehash: dc1786f1f2dcc7bd01488dd24c6ef454f7e1cfbd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557636"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms добавить элемент конфигурации

`<add>`Элемент добавляет предопределенный ключ, указывающий, поддерживает ли приложение Windows Form функции, добавленные в Windows Forms приложения в .NET Framework 4,7 или более поздней версии.

## <a name="syntax"></a>Синтаксис

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

| Атрибут | Описание |
| --------- | ----------- |
| `key`     | Обязательный атрибут. Предопределенное имя ключа, соответствующее определенной Windows Forms настраиваемой функции. |
| `value`   | Обязательный атрибут. Значение, присваиваемое параметру `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key` имена атрибутов и связанные значения

| Имя в `key` | Значения | Описание |
| ---------- | ------ | ----------- |
| "Анчорлайаут. Дисаблесинглепассконтролскалинг" | "true" &#124; "false" | Указывает, масштабируется ли привязанные элементы управления за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "Дпиаваренесс" | "PerMonitorV2" &#124; "false" | Указывает, учитывается ли в приложении разрешение DPI. Задайте для ключа значение "PerMonitorV2", чтобы обеспечить поддержку отслеживания dpi. в противном случае задайте для него значение "false". Поддержка DPI является функцией согласия; чтобы воспользоваться преимуществами Windows Forms "поддержка высокого DPI", следует присвоить ей значение "PerMonitorV2". Дополнительные сведения см. в разделе ["Примечания"](#remarks) . |
| CheckedListBox. Дисаблехигхдпиимпровементс | "true" &#124; "false" | Указывает, <xref:System.Windows.Forms.CheckedListBox> использует ли элемент управления преимущества масштабирования и улучшения макета, представленные в .NET Framework 4,7. значение true, чтобы отказаться от улучшений масштабирования и макета; в противном случае — значение false. |
| "DataGridView. Дисаблехигхдпиимпровементс" | "true" &#124; "false" | Указывает, <xref:System.Windows.Forms.DataGridView> появились ли улучшения масштабирования и разметки элемента управления в .NET Framework 4,7. значение true, чтобы отказаться от осведомленности о DPI; в противном случае — значение false. |
| "Дисабледпичанжедмессажехандлинг" | "true" &#124; "false" | значение true, чтобы отказаться от получения сообщений, связанных с изменениями масштабирования DPI; в противном случае — значение false. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . |
| "Енаблевиндовсформшигхдпиауторесизинг" | "true" &#124; "false" | Указывает, изменяется ли размер приложения Windows Forms автоматически из-за изменения масштабирования DPI. значение true, чтобы включить автоматическое изменение размера; в противном случае — значение false. |
| "Form. Дисаблесинглепассконтролскалинг" | "true" &#124; "false" | Указывает, <xref:System.Windows.Forms.Form> масштабируется ли объект за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "MonthCalendar. Дисаблесинглепассконтролскалинг" | "true" &#124; "false" | Указывает, <xref:System.Windows.Forms.MonthCalendar> масштабируется ли элемент управления за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "ToolStrip. Дисаблехигхдпиимпровементс" | "true" &#124; "false" | Указывает, <xref:System.Windows.Forms.ToolStrip> использует ли элемент управления преимущества масштабирования и улучшения макета, представленные в .NET Framework 4,7. значение true, чтобы отказаться от осведомленности о DPI; в противном случае — значение false. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](index.md) | Настраивает поддержку новых функций приложения Windows Forms. |

## <a name="remarks"></a>Примечания

Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework.

`<System.Windows.Forms.ApplicationConfigurationSection>`Элемент позволяет добавить один или несколько дочерних `<add>` элементов, каждый из которых определяет конкретный параметр конфигурации.

Общие сведения о поддержке Windows Forms высокого DPI см. [в разделе Поддержка высокого DPI в Windows Forms](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms).

### <a name="dpiawareness"></a>дпиаваренесс

Windows Forms приложения, работающие под управлением Windows 10 Creators Edition и целевые версии .NET Framework, начиная с .NET Framework 4,7, можно настроить так, чтобы воспользоваться преимуществами улучшений с высоким разрешением, появившихся в .NET Framework 4,7. Сюда входит следующее.

- Поддержка сценариев динамического МАСШТАБИРОВАНИЯ, при которой пользователь изменяет значение DPI или коэффициент масштабирования после запуска Windows Forms приложения.

- Улучшения в масштабировании и компоновке ряда элементов управления Windows Forms, таких как <xref:System.Windows.Forms.MonthCalendar> элемент управления и <xref:System.Windows.Forms.CheckedListBox> элемент управления.

Поддержка высокого DPI является функцией согласия. по умолчанию значение `DpiAwareness` равно `false` . Вы можете включить поддержку Windows Forms "для отслеживания DPI, задав для этого ключа значение `PerMonitorV2` в файле конфигурации приложения. Если включена поддержка DPI, также включаются все индивидуальные функции DPI. Сюда входит следующее.

- Измененные сообщения DPI, управляемые `DisableDpiChangedMessageHandling` ключом.

- Поддержка динамического DPI, управляемая `EnableWindowsFormsHighDpiAutoResizing` ключом.

- Масштабирование элемента управления с одним проходом, которое управляется `Form.DisableSinglePassControlScaling` для отдельных <xref:System.Windows.Forms.Form> элементов управления, `AnchorLayout.DisableSinglePassControlScaling` ключом для привязанных элементов управления и `MonthCalendar.DisableSinglePassControlScaling` ключом для <xref:System.Windows.Forms.MonthCalendar> элемента управления.

- Улучшенное масштабирование и улучшение макета, которые управляются ключом элемента управления, `CheckListBox.DisableHighDpiImprovements` <xref:System.Windows.Forms.CheckedListBox> ключом для элемента управления `DataGridView.DisableHighDpiImprovements` <xref:System.Windows.Forms.DataGridView> и `Toolstrip.DisableHighDpiImprovements` ключом для <xref:System.Windows.Forms.ToolStrip> элемента управления.

Параметр одиночного согласия по умолчанию, предоставляемый параметром, `DpiAwareness` `PerMonitorV2` обычно подходит для новых Windows Forms приложений. Однако можно отказаться от отдельных улучшений с высоким разрешением, добавив соответствующий ключ в файл конфигурации приложения. Например, чтобы воспользоваться преимуществами всех новых функций DPI, за исключением динамической поддержки DPI, добавьте в файл конфигурации приложения следующее:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Как правило, вы отказываетесь от конкретной функции, так как вы решили управлять ею программным способом.

Дополнительные сведения о поддержке высокого DPI в Windows Forms приложениях см. [в разделе Поддержка высокого DPI в Windows Forms](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms).

### <a name="disabledpichangedmessagehandling"></a>дисабледпичанжедмессажехандлинг

Начиная с .NET Framework 4,7, элементы управления Windows Forms создают ряд событий, связанных с изменениями масштабирования DPI. К ним относятся <xref:System.Windows.Forms.Control.DpiChangedAfterParent> <xref:System.Windows.Forms.Control.DpiChangedBeforeParent> события, и <xref:System.Windows.Forms.Form.DpiChanged> . Значение `DisableDpiChangedMessageHandling` ключа определяет, возникают ли эти события в Windows Forms приложении.

### <a name="single-pass-scaling"></a>Однопроходное масштабирование

Масштабирование одного или нескольких потоков влияет на скорость реагирования пользовательского интерфейса и визуальный внешний вид элементов пользовательского интерфейса по мере их масштабирования. Начиная с .NET Framework 4,7, Windows Forms использует однопроходное масштабирование. В предыдущих версиях .NET Framework масштабирование выполнялось с помощью нескольких проходов, что привело к увеличению количества элементов управления, чем требовалось. Если приложение зависит от старого поведения, необходимо отключить однопроходное масштабирование.

## <a name="see-also"></a>См. также

- [Раздел конфигурации Windows Forms](index.md)
- [Поддержка высокого DPI в Windows Forms](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
