---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614944"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>Фокус клавиатуры теперь правильно перемещается на нескольких слоях размещения WinForms и WPF

#### <a name="details"></a>Подробнее

Рассмотрим приложение WPF для размещения элемента управления WinForms, который, в свою очередь, содержит элементы управления WPF. Пользователи не могут перейти из слоя WinForms, если первый или последний элемент управления в этом слое является `System.Windows.Forms.Integration.ElementHost` WPF. Это изменение устраняет эту проблему: теперь пользователи могут выйти из слоя WinForms. Автоматические приложения, зависящие от фокуса, который никогда не должен выходить из слоя WinForms, могут перестать работать должным образом.

#### <a name="suggestion"></a>Предложение

Разработчики, желающие использовать это изменение в приложениях для целевой платформы .NET Framework 4.7.2 и более ранних версий, могут задать для следующего набора флагов AppContext значение false, чтобы включить изменение.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Для приложений WPF необходимо включить использование всех более ранних усовершенствований специальных возможностей для получения более поздних усовершенствований. Другими словами, оба переключателя, `Switch.UseLegacyAccessibilityFeatures` и `Switch.UseLegacyAccessibilityFeatures.2`, должны быть заданы. Разработчики, которым требуются прежние функции при нацеливании на .NET 4.7.2 и более поздних версий, могут установить для следующего флага AppContext значение true, чтобы отключить изменение.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
