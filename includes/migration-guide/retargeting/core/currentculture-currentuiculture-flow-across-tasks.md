---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614669"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>Поток CurrentCulture и CurrentUICulture между задачами

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> хранятся в <xref:System.Threading.ExecutionContext?displayProperty=fullName> потока, который проходит через асинхронные операции. Это означает, что изменения <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> будут отражены в задачах, которые позже выполняются асинхронно. Это отличается от поведения предыдущих версий .NET Framework (которые во всех асинхронных задачах сбрасывали <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>).

#### <a name="suggestion"></a>Предложение

Приложения, которых коснулось это изменение, могут обойти его, явно задав <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> в качестве первой операции в асинхронной задаче. Кроме того, можно выбрать прежнее поведение (без потока <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) путем установки следующего переключателя совместимости:

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

Эта проблема была устранена с помощью WPF в .NET Framework 4.6.2. Она также была устранена в .NET Framework версий 4.6 и 4.6.1 посредством [KB 3139549](https://support.microsoft.com/kb/3139549). Приложения, предназначенные для .NET Framework 4.6 или более поздней версии, автоматически получают правильное поведение в приложениях WPF — <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) будет сохранено в операциях диспетчера.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
