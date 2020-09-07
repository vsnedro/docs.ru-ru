---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497946"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus вызывается повторно, если соответствующий обработчик выводит окно сообщения Windows Forms

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5, вызов <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> из обработчика <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> приведет к повторному запуску обработчика после закрытия окна сообщения. В результате может начаться бесконечный цикл вывода окон сообщений.

#### <a name="suggestion"></a>Предложение

Существует два способа решения этой проблемы:<ol><li>Ее можно избежать, вызвав <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> вместо <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</li><li>Ее можно избежать, открыв окно сообщения из обработчика событий <xref:System.Windows.UIElement.LostKeyboardFocus> (в отличие от обработчика событий <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>).</li></ol>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
