---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556230"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.7.1, не поддерживается в Windows Forms в .NET Core и .NET 5.0 и более поздних версий.

#### <a name="change-description"></a>Описание изменений

В .NET Framework 4.6.2 и предыдущих версиях элемент управления <xref:System.Windows.Forms.RichTextBox> создает экземпляр элемента управления Win32 RichEdit версии 3.0, а для приложений, предназначенных для .NET Framework 4.7.1, элемент управления <xref:System.Windows.Forms.RichTextBox> создает экземпляр элемента управления RichEdit версии 4.1 (в *msftedit.dll*). Параметр совместимости `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` был введен для того, чтобы в приложениях, предназначенных для .NET Framework 4.7.1 и более поздних версий, можно было отказаться от использования нового элемента управления RichEdit версии 4.1 и использовать вместо него прежнюю версию 3.

В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` не поддерживается. Поддерживаются только новые версии элемента управления <xref:System.Windows.Forms.RichTextBox>.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
