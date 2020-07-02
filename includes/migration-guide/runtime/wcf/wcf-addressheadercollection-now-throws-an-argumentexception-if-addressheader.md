---
ms.openlocfilehash: d29be721b50d1c93723b325774a06e86f77dbebf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621227"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="f2116-101">WCF AddressHeaderCollection теперь создает исключение ArgumentException, если элемент addressHeader равен NULL</span><span class="sxs-lookup"><span data-stu-id="f2116-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="f2116-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f2116-102">Details</span></span>

<span data-ttu-id="f2116-103">Начиная с версии .NET Framework 4.7.1, конструктор <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> создает исключение <xref:System.ArgumentException>, если один из элементов равен <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="f2116-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="f2116-104">В версии .NET Framework 4.7 и более ранних исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="f2116-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f2116-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="f2116-105">Suggestion</span></span>

<span data-ttu-id="f2116-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить его, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:</span><span class="sxs-lookup"><span data-stu-id="f2116-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f2116-107">name</span><span class="sxs-lookup"><span data-stu-id="f2116-107">Name</span></span>    | <span data-ttu-id="f2116-108">Значение</span><span class="sxs-lookup"><span data-stu-id="f2116-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f2116-109">Область</span><span class="sxs-lookup"><span data-stu-id="f2116-109">Scope</span></span>   |<span data-ttu-id="f2116-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f2116-110">Minor</span></span>|
|<span data-ttu-id="f2116-111">Версия</span><span class="sxs-lookup"><span data-stu-id="f2116-111">Version</span></span>|<span data-ttu-id="f2116-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="f2116-112">4.7.1</span></span>|
|<span data-ttu-id="f2116-113">Type</span><span class="sxs-lookup"><span data-stu-id="f2116-113">Type</span></span>|<span data-ttu-id="f2116-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f2116-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f2116-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f2116-115">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})></li></ul>|
