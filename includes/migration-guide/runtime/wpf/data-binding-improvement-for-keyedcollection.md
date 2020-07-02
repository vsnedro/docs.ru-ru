---
ms.openlocfilehash: beb869208e8d48d762d94b5989a558fa2f1aaf29
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622110"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Улучшение производительности привязки данных для KeyedCollection

#### <a name="details"></a>Подробнее

Исправлено некорректное использование <xref:System.Windows.Data.Binding> индексатора IList, если исходный объект объявляет настраиваемый индексатор с такой же сигнатурой (например, KeyedCollection&lt;int,TItem&gt;).

#### <a name="suggestion"></a>Предложение

Чтобы приложение, предназначенное для более старой версии, могло использовать это изменение, необходимо запустить его на платформе .NET Framework 4.8 или более поздней версии и включить это изменение, добавив следующий [параметр AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) в разделе <code>&lt;runtime&gt;</code> файла конфигурации приложения и установив для него значение <code>false</code>:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.8|
|Type|Среда выполнения|
