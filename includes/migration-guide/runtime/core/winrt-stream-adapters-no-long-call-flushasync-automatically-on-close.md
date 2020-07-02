---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620595"
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
