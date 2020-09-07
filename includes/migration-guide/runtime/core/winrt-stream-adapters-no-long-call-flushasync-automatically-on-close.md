---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497188"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Адаптеры потока WinRT больше не вызывают FlushAsync автоматически при закрытии

#### <a name="details"></a>Подробнее

В приложениях для магазина Windows адаптеры потока среды выполнения Windows больше не вызывают метод FlushAsync из метода Dispose.

#### <a name="suggestion"></a>Предложение

Это изменение должно быть прозрачным. Разработчики могут восстановить прежнее поведение, написав следующий код.<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Прозрачный|
|Version|4.5.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
