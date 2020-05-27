---
ms.openlocfilehash: 55c13aa70a03bcc548ce1d096cca8f40de6cda84
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721789"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Параметр совместимости DontSupportReentrantFilterMessage не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, появившийся в .NET Framework 4.6.1, не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Framework 4.6.1, параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` устраняет возможные исключения <xref:System.IndexOutOfRangeException> при вызове сообщения <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> с пользовательской реализацией <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Устранение рисков: пользовательские реализации IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

В .NET Core параметр `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

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
