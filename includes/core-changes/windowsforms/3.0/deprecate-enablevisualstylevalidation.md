---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556222"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>Параметр совместимости EnableVisualStyleValidation не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается в Windows Forms в .NET Core или .NET 5.0 и более поздних версий.

#### <a name="change-description"></a>Описание изменений

В .NET Framework параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` позволял приложению отказаться от проверки визуальных стилей, предоставленных в числовой форме.

В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается.

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
