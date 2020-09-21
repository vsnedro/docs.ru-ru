---
ms.openlocfilehash: 5529b8379c5cb9f1bc525e0c2340f6b885e35822
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606424"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>Свойство ContextMenuStrip.SourceControl содержит допустимый элемент управления при наличии вложенных объектов ToolStripMenuItem

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.1 и предыдущих версиях свойство <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> некорректно возвращает значение null, когда пользователь открывает меню из вложенных элементов управления <xref:System.Windows.Forms.ToolStripMenuItem>. В платформе .NET Framework 4.7.2 и более поздних версий для свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> всегда задана фактическая система управления версиями.

#### <a name="suggestion"></a>Предложение

**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:

- Приложение предназначено для платформы .NET Framework 4.7.2. Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.
- Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения и получения значения `false`, как показано в следующем примере.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

В приложениях, предназначенных для .NET Framework 4.7.2 или более поздней версии, где требуется сохранить предыдущие функции, можно выбрать использование прежнего значения системы управления версиями, явно установив этот переключатель AppContext в значение `true`.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
