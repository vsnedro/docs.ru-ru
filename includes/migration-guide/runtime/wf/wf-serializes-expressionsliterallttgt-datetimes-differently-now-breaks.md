---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496407"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>Теперь WF сериализует Expressions.Literal&lt;T&gt; DateTimes по-другому (нарушает работу пользовательских средств синтаксического анализа XAML)

#### <a name="details"></a>Подробнее

Связанный объект <xref:System.Windows.Markup.ValueSerializer> преобразует объект <xref:System.DateTime?displayProperty=fullName> или <xref:System.DateTimeOffset?displayProperty=fullName>, компоненты Second и <xref:System.DateTime.Millisecond?displayProperty=fullName> которого не равны нулю и (для значения <xref:System.DateTime?displayProperty=fullName>) свойство <xref:System.DateTime.Kind> которого не равно Unspecified, в синтаксис элемента свойства вместо строки. Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=fullName> и <xref:System.DateTimeOffset?displayProperty=fullName> в оба конца. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.

#### <a name="suggestion"></a>Предложение

Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=fullName> и <xref:System.DateTimeOffset?displayProperty=fullName> в оба конца. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
