---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614951"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a>Событие SelectionChanged и свойство SelectedContent для TabControl

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.7.1, <xref:System.Windows.Controls.TabControl> обновляет значение своего свойства <xref:System.Windows.Controls.TabControl.SelectedContent> до того, как создать событие <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>, даже в случае изменения выделения. В .NET Framework 4.7 и более ранних версий обновление SelectedContent происходило после создания события.

#### <a name="suggestion"></a>Предложение

В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, данное изменение можно отключить и использовать устаревшее поведение, добавив следующее в раздел `<runtime>` файла конфигурации приложения:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

В приложениях, предназначенных для .NET Framework 4.7 или более ранней версии, но работающих на платформе .NET Framework 4.7.1 или более поздней версии, можно включить новое поведение, добавив следующее в раздел `<runtime>` файла конфигурации приложения:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Версия | 4.7.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
