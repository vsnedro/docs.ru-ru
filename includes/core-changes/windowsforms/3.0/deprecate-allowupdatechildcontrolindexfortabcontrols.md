---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556233"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` поддерживается в Windows Forms в .NET Framework 4.6 и более поздних версиях, но не поддерживается в .NET Core,а также в .NET Core 5.0 и более поздних версий.

#### <a name="change-description"></a>Описание изменений

В .NET Framework 4.6 и более поздних версиях при выборе вкладки ее коллекция элементов управления переупорядочивается. Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` позволяет приложению отменить переупорядочивание, если оно не требуется.

В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- None

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
