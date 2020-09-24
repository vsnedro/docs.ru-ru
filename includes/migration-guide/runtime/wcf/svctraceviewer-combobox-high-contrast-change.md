---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770814"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Изменение режима высокой контрастности ComboBox svcTraceViewer

#### <a name="details"></a>Подробнее

В [программе Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) элементы управления ComboBox не отображались в правильном цвете в некоторых темах высокой контрастности. Проблема устранена в .NET Framework 4.7.2. Но из-за требований обратной совместимости пакета SDK для .NET Framework исправление не видно клиентам по умолчанию. .NET 4.8 предоставляет это изменение, добавив следующие [параметры конфигурации AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в файл конфигурации svcTraceViewer.exe.config:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a>Предложение

Если вы не хотите менять поведение тем с высокой контрастностью, отключите его, удалив из файла svcTraceViewer.exe.config следующий раздел:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| name    | Значение   |
|:--------|:--------|
| Область   | Пограничный случай    |
| Version | 4.8     |
| Type    | Среда выполнения |

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
