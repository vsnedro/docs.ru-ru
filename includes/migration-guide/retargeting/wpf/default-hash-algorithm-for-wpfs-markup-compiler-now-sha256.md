---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614930"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>Алгоритмом хэширования для компилятора разметки WPF по умолчанию теперь является SHA256

#### <a name="details"></a>Подробнее

Компилятор разметки (MarkupCompiler) WPF предоставляет службы компиляции для файлов разметки XAML.  В .NET Framework 4.7.1 и более ранних версиях для вычисления значений контрольной суммы по умолчанию использовался хэш-алгоритм SHA1. С учетом выявленных проблем с безопасностью SHA1, начиная с версии .NET Framework 4.7.2, теперь по умолчанию используется алгоритм SHA256.  Это изменение затрагивает все поколения контрольной суммы для файлов разметки во время компиляции.

#### <a name="suggestion"></a>Предложение

Разработчикам приложений, предназначенных для .NET Framework 4.7.2 или более поздних версий, которым требуется вернуться к режиму хэширования SHA1, необходимо установить следующий флаг AppContext.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Разработчикам, которым требуется использовать хэширование SHA256 для версий целевой платформы ниже .NET Framework 4.7.2, необходимо задать следующий флаг AppContext.  Обратите внимание, что установленная версия .NET Framework должна быть 4.7.2 или выше.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Прозрачный |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
