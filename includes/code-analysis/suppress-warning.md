---
ms.openlocfilehash: b26e346f7076a57aef8ae7587ab1222b4100a323
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957940"
---
## <a name="suppress-a-warning"></a>Подавлять предупреждение

Чтобы отключить нарушение правил, установите параметр серьезности для конкретного идентификатора правила `none` в файл EditorConfig. Пример:

```ini
[*.{cs,vb}]
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio предоставляет дополнительные способы отключения предупреждений из правил анализа кода. Дополнительные сведения см. в разделе [подавлять нарушения](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Дополнительные сведения о серьезности правил см. в разделе [Настройка серьезности правила](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).
