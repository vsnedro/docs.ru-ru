---
ms.openlocfilehash: 8b804d23247b95381f3ff83bc12c32215a420fb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614958"
---
### <a name="wpf-appdomain-shutdown-handling-may-now-call-dispatcherinvoke-in-cleanup-of-weak-events"></a>При обработке завершения работы домена приложения в WPF теперь может вызываться Dispatcher.Invoke при очистке слабых событий

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.1 и более ранних версий во время завершения работы домена приложения WPF может создавать <xref:System.Windows.Threading.Dispatcher?displayProperty=nameWithType> в потоке метода завершения .NET.  Эта проблема была исправлена в .NET Framework 4.7.2 и последующих версиях путем реализации поддержки потоков при очистке слабых событий.  Благодаря этому WPF может вызывать <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> для завершения процесса очистки. В некоторых приложениях это изменение в управлении временем для метода завершения может привести к возникновению исключений в процессе завершения работы домена приложения или процесса.  Как правило, это происходит в приложениях, в которых перед завершением работы процесса или домена приложения не завершается корректным образом работа диспетчеров, выполняющихся в рабочих потоках.  В таких приложениях следует оптимизировать управление временем существования диспетчеров.

#### <a name="suggestion"></a>Предложение

В .NET Framework 4.7.2 и более поздних версий разработчики могут отключить это исправление, чтобы смягчить (но не исключить полностью) проблемы с задержкой, которые могут возникнуть из-за изменения в процессе очистки. Чтобы отключить это изменение, используйте следующий флаг AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotInvokeInWeakEventTableShutdownListener=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
