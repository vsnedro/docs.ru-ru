---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614881"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>Свойство ContextMenuStrip.SourceControl содержит допустимый элемент управления при наличии вложенных объектов ToolStripMenuItem

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.1 и предыдущих версиях свойство <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> некорректно возвращает значение null, когда пользователь открывает меню из вложенных элементов управления <xref:System.Windows.Forms.ToolStripMenuItem>. В платформе .NET Framework 4.7.2 и более поздних версий для свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> всегда задана фактическая система управления версиями.

#### <a name="suggestion"></a>Предложение

**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:

- Приложение предназначено для платформы .NET Framework 4.7.2. Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.
- Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) в раздел `<runtime>` файла конфигурации приложения и получения значения `false`, как показано в следующем примере.

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
