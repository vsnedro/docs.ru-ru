---
ms.openlocfilehash: 06f4186e8f233f5c769dfc5e05d2de5eacd9b053
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622090"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Изменение режима высокой контрастности ComboBox svcTraceViewer

#### <a name="details"></a>Подробнее

В [программе Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) элементы управления ComboBox не отображались в правильном цвете в некоторых темах высокой контрастности. Проблема устранена в .NET Framework 4.7.2. Но из-за требований обратной совместимости пакета SDK для .NET Framework исправление не видно клиентам по умолчанию. .NET 4.8 предоставляет это изменение, добавив следующие [параметры конфигурации AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в файл конфигурации svcTraceViewer.exe.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a>Предложение

<ul><li>Как отказаться от изменения. Если вы не хотите менять поведение тем с высокой контрастностью, отключите его, удалив из файла svcTraceViewer.exe.config следующий раздел:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.8|
|Type|Среда выполнения|
