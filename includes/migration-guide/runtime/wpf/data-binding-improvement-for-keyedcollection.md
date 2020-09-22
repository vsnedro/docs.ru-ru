---
ms.openlocfilehash: 9cd1d0955b8b77cb77d5c6938b37d9042d8144f6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606900"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="a0c84-101">Улучшение производительности привязки данных для KeyedCollection</span><span class="sxs-lookup"><span data-stu-id="a0c84-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="a0c84-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a0c84-102">Details</span></span>

<span data-ttu-id="a0c84-103">Исправлено некорректное использование <xref:System.Windows.Data.Binding> индексатора IList, если исходный объект объявляет настраиваемый индексатор с такой же сигнатурой (например, KeyedCollection&lt;int,TItem&gt;).</span><span class="sxs-lookup"><span data-stu-id="a0c84-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a0c84-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="a0c84-104">Suggestion</span></span>

<span data-ttu-id="a0c84-105">Чтобы приложение, предназначенное для более старой версии, могло использовать это изменение, необходимо запустить его на платформе .NET Framework 4.8 или более поздней версии и включить это изменение, добавив следующий [параметр AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе <code>&lt;runtime&gt;</code> файла конфигурации приложения и установив для него значение <code>false</code>:</span><span class="sxs-lookup"><span data-stu-id="a0c84-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="a0c84-106">name</span><span class="sxs-lookup"><span data-stu-id="a0c84-106">Name</span></span>    | <span data-ttu-id="a0c84-107">Значение</span><span class="sxs-lookup"><span data-stu-id="a0c84-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a0c84-108">Область</span><span class="sxs-lookup"><span data-stu-id="a0c84-108">Scope</span></span>   |<span data-ttu-id="a0c84-109">Значительно</span><span class="sxs-lookup"><span data-stu-id="a0c84-109">Major</span></span>|
|<span data-ttu-id="a0c84-110">Version</span><span class="sxs-lookup"><span data-stu-id="a0c84-110">Version</span></span>|<span data-ttu-id="a0c84-111">4.8</span><span class="sxs-lookup"><span data-stu-id="a0c84-111">4.8</span></span>|
|<span data-ttu-id="a0c84-112">Type</span><span class="sxs-lookup"><span data-stu-id="a0c84-112">Type</span></span>|<span data-ttu-id="a0c84-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="a0c84-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a0c84-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a0c84-114">Affected APIs</span></span>

<span data-ttu-id="a0c84-115">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="a0c84-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
