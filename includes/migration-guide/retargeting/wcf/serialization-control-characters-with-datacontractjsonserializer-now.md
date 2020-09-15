---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614790"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a><span data-ttu-id="a8c9e-101">Сериализация управляющих символов с помощью DataContractJsonSerializer теперь совместима с ECMAScript версии 6 и 8</span><span class="sxs-lookup"><span data-stu-id="a8c9e-101">Serialization of control characters with DataContractJsonSerializer is now compatible with ECMAScript V6 and V8</span></span>

#### <a name="details"></a><span data-ttu-id="a8c9e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a8c9e-102">Details</span></span>

<span data-ttu-id="a8c9e-103">В .NET Framework 4.6.2 и более ранних версиях объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> сериализовал некоторые специальные управляющие символы, например \b, \f и \t, не так, как требуют стандарты ECMAScript версии 6 и 8.</span><span class="sxs-lookup"><span data-stu-id="a8c9e-103">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> did not serialize some special control characters, such as \b, \f, and \t, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span> <span data-ttu-id="a8c9e-104">Начиная с .NET Framework 4.7, сериализация таких управляющих символов совместима с ECMAScript версий 6 и 8.</span><span class="sxs-lookup"><span data-stu-id="a8c9e-104">Starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a8c9e-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="a8c9e-105">Suggestion</span></span>

<span data-ttu-id="a8c9e-106">В приложениях, предназначенных для .NET Framework 4.7, эта функция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a8c9e-106">For apps that target the .NET Framework 4.7, this feature is enabled by default.</span></span> <span data-ttu-id="a8c9e-107">Если оно нежелательно, данную функцию можно отключить, добавив следующую строку в раздел `<runtime>` файла app.config или web.config:</span><span class="sxs-lookup"><span data-stu-id="a8c9e-107">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| <span data-ttu-id="a8c9e-108">name</span><span class="sxs-lookup"><span data-stu-id="a8c9e-108">Name</span></span>    | <span data-ttu-id="a8c9e-109">Значение</span><span class="sxs-lookup"><span data-stu-id="a8c9e-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a8c9e-110">Область</span><span class="sxs-lookup"><span data-stu-id="a8c9e-110">Scope</span></span>   | <span data-ttu-id="a8c9e-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="a8c9e-111">Edge</span></span>        |
| <span data-ttu-id="a8c9e-112">Version</span><span class="sxs-lookup"><span data-stu-id="a8c9e-112">Version</span></span> | <span data-ttu-id="a8c9e-113">4.7</span><span class="sxs-lookup"><span data-stu-id="a8c9e-113">4.7</span></span>         |
| <span data-ttu-id="a8c9e-114">Type</span><span class="sxs-lookup"><span data-stu-id="a8c9e-114">Type</span></span>    | <span data-ttu-id="a8c9e-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="a8c9e-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a8c9e-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a8c9e-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
