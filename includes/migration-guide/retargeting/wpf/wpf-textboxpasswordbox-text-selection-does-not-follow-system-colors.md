---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614979"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>Выделенный текст в текстовом поле или поле пароля WPF не соответствуют системным цветам

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.1 и более ранних версий `System.Windows.Controls.TextBox` и `System.Windows.Controls.PasswordBox` WPF могли отображать выделенный текст только в слое декоративных элементов. В некоторых системных темах это приводило к скрытию текста, что делало его трудно читаемым.  В .NET Framework 4.7.2 и более поздних версий разработчики имеют возможность включить механизм отрисовки выбранных участков не на основе декоративных элементов, что устраняет эту проблему.

#### <a name="suggestion"></a>Предложение

Разработчикам, желающим использовать это изменение, необходимо задать следующий флаг AppContext соответствующим образом.  Чтобы использовать эту функцию, должна быть установлена версия .NET Framework 4.7.2 или более поздняя. Для включения выбора не на основе декоративных элементов используйте следующий флаг AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
