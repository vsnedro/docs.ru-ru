---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614937"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a>Событие SelectionChanged и свойство SelectedValue селектора

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.7.1 <xref:System.Windows.Controls.Primitives.Selector> всегда обновляет значение своего свойства <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> до порождения события <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> при изменении его выбора. Это позволяет согласовать свойство SelectedValue с другими свойствами выбора (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> и <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), которые изменяются перед порождением события.<p/>В .NET Framework 4.7 и более ранних версий изменение SelectedValue в большинстве случаев происходило до события, но оно выполнялось после события, если изменение выбора было вызвано изменением свойства <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.

#### <a name="suggestion"></a>Предложение

В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, данное изменение можно отключить и использовать устаревшее поведение, добавив следующее в раздел `<runtime>` файла конфигурации приложения:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

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
