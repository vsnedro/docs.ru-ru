---
ms.openlocfilehash: 95aa243a5790d4201c7871e617dbe4ccafb7c1a1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556246"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Параметр совместимости DontSupportReentrantFilterMessage не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, появившийся в .NET Framework 4.6.1, не поддерживается в Windows Forms в .NET Core и .NET 5.0 и более поздних версий.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Framework 4.6.1, параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` устраняет возможные исключения <xref:System.IndexOutOfRangeException> при вызове сообщения <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> с пользовательской реализацией <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Устранение рисков: пользовательские реализации IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

В .NET Core и .NET 5.0 и более поздних версий параметр `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
