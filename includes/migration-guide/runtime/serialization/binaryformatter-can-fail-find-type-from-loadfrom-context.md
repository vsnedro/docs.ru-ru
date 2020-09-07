---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496156"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>BinaryFormatter может не находить тип в контексте LoadFrom

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5 ряд изменений <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> может привести к различиям в десериализации при использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> для десериализации типов, загруженных в контекст LoadFrom. Эти изменения связаны с тем, что <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> теперь иначе загружает тип. Это приводит к другому поведению, когда <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> пытается выполнить десериализацию в этот тип позднее. Модуль привязки сериализации по умолчанию не выполняет автоматический поиск контекста LoadFrom, хотя это могло работать в некоторых случаях при старом поведении XmlSerializer. В связи с изменениями, когда этот тип загружается из сборки, загруженной в другом контексте, может возникнуть исключение <xref:System.IO.FileNotFoundException?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Если это исключение возникает, в свойстве <code>Binder</code><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> можно задать пользовательский модуль привязки, который найдет правильный тип.<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>А затем пользовательский модуль привязки:<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
