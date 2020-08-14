---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556225"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a>Параметр совместимости UseLegacyImages не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.8, не поддерживается в Windows Forms в .NET Core и .NET 5.0 и более поздних версий.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Framework 4.8 параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages` устраняет возможные проблемы с масштабированием изображений в сценариях ClickOnce в средах с высоким DPI. Если задано значение `true`, параметр позволяет пользователю восстановить прежний способ масштабирования изображений при высоком уровне DPI, когда масштаб составляет более 100 %. Дополнительные сведения см. в [заметках о выпуске .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) в GitHub.

В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.UseLegacyImages` не поддерживается.

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
