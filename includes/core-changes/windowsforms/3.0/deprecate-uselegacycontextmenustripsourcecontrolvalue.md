---
ms.openlocfilehash: 3ada05a13ec7acde1d8374ed733d0d51cdfb408c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721117"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, появившийся в .NET Framework 4.7.2, не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

Начиная с версии .NET Framework 4.7.2, параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` позволяет разработчикам отказаться от нового поведения свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, которое теперь возвращает ссылку на систему управления версиями. Ранее это свойство возвращало `null`. Дополнительные сведения см. в статье [Элемент \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

В .NET Core параметр `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

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
