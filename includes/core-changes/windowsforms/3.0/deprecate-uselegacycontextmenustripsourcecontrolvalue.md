---
ms.openlocfilehash: df6169289fb96df5f7daf8bd58ccaeebc33ad87c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556238"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, появившийся в .NET Framework 4.7.2, не поддерживается в Windows Forms в .NET Core и .NET 5.0 и более поздних версий.

#### <a name="change-description"></a>Описание изменений

Начиная с версии .NET Framework 4.7.2 параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` позволяет разработчикам отказаться от нового поведения свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, которое теперь возвращает ссылку на систему управления версиями. Ранее это свойство возвращало `null`. Дополнительные сведения см. в разделе [Элемент \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
