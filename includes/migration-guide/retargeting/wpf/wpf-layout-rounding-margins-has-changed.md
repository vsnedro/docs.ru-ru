---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615773"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Изменились параметры округления полей макета WPF

#### <a name="details"></a>Подробнее

Способ округления полей, а также их границ и фона, изменен. В результате этого изменения:

- ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;
- расположение объекта может измениться максимум на один пиксель;
- выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.
По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.

#### <a name="suggestion"></a>Предложение

Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел `<runtime>` файла app.config.

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

Для приложений, предназначенных для .NET Framework 4.6, в которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел `<runtime>` файла app.config:

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6         |
| Type    | Изменение целевой платформы |
