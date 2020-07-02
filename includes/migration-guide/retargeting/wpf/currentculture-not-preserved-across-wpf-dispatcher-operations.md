---
ms.openlocfilehash: bd656478a55856e676853e57f3e7386ea0aa0211
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614825"
---
### <a name="currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>CurrentCulture не сохраняется в операциях диспетчера WPF

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.6, изменения <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>, внесенные в операции <xref:System.Windows.Threading.Dispatcher?displayProperty=fullName>, будут утеряны в конце операции диспетчеризации. Аналогичным образом, изменения <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>, внесенные за пределами операции Dispatcher, не будут учитываться при выполнении этой операции. С практической точки зрения это означает, что изменения <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> могут не передаваться между обратными вызовами пользовательского интерфейса WPF и другим кодом приложения WPF. Это связано с изменением в <xref:System.Threading.ExecutionContext?displayProperty=fullName>, в результате которого <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> сохраняются в контексте выполнения, начиная с приложений, предназначенных для версии .NET Framework 4.6. Операции диспетчеризации WPF сохраняют контекст выполнения, который используется для запуска операции и восстановления предыдущего контекста при завершении операции. Поскольку <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> теперь являются частью этого контекста, внесенные в рамках операции диспетчеризации изменения не сохраняются вне этой операции.

#### <a name="suggestion"></a>Предложение

В приложениях, затронутых данным изменением, можно обойти эту проблему, сохранив <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> в поле и проверив все тексты операций диспетчеризации (включая обработчики обратного вызова событий пользовательского интерфейса) на установку правильных значений <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>. Кроме того, поскольку изменение ExecutionContext, являющееся базовым для этого изменения WPF, влияет только на приложения, предназначенные для .NET Framework 4.6 или более поздних версий, это нарушение можно исключить путем нацеливания на .NET Framework 4.5.2. В приложениях, ориентированных на платформу .NET Framework 4.6 или более поздней версии, эту проблему можно обойти, установив следующий параметр совместимости:

<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>

Эта проблема была устранена с помощью WPF в .NET Framework 4.6.2. Она также была устранена в .NET Framework версий 4.6 и 4.6.1 посредством [KB 3139549](https://support.microsoft.com/kb/3139549). Приложения, предназначенные для .NET Framework 4.6 или более поздней версии, автоматически получают правильное поведение в приложениях WPF — <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) будет сохранено в операциях диспетчера.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6         |
| Type    | Изменение целевой платформы |
