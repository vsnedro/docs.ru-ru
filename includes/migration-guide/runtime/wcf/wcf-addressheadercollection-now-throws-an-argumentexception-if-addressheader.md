---
ms.openlocfilehash: 3506653bfc749ae3d8002715ca72ca89de7a681b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "91025344"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="3446d-101">WCF AddressHeaderCollection теперь создает исключение ArgumentException, если элемент addressHeader равен NULL</span><span class="sxs-lookup"><span data-stu-id="3446d-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="3446d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3446d-102">Details</span></span>

<span data-ttu-id="3446d-103">Начиная с версии .NET Framework 4.7.1, конструктор <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> создает исключение <xref:System.ArgumentException>, если один из элементов равен `null`.</span><span class="sxs-lookup"><span data-stu-id="3446d-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is `null`.</span></span> <span data-ttu-id="3446d-104">В версии .NET Framework 4.7 и более ранних исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="3446d-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3446d-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="3446d-105">Suggestion</span></span>

<span data-ttu-id="3446d-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить его, добавив следующую строку в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="3446d-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="3446d-107">Имя</span><span class="sxs-lookup"><span data-stu-id="3446d-107">Name</span></span>    | <span data-ttu-id="3446d-108">Значение</span><span class="sxs-lookup"><span data-stu-id="3446d-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="3446d-109">Область</span><span class="sxs-lookup"><span data-stu-id="3446d-109">Scope</span></span>   | <span data-ttu-id="3446d-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="3446d-110">Minor</span></span>   |
| <span data-ttu-id="3446d-111">Версия</span><span class="sxs-lookup"><span data-stu-id="3446d-111">Version</span></span> | <span data-ttu-id="3446d-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="3446d-112">4.7.1</span></span>   |
| <span data-ttu-id="3446d-113">Type</span><span class="sxs-lookup"><span data-stu-id="3446d-113">Type</span></span>    | <span data-ttu-id="3446d-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="3446d-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3446d-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3446d-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
