---
ms.openlocfilehash: 97e38685777c7c418c0ccd91f4c433501ecf3aaa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721247"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>Параметр совместимости EnableVisualStyleValidation не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

В .NET Framework параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` позволял приложению отказаться от проверки визуальных стилей, предоставленных в числовой форме.

В .NET Core параметр `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

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
