---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614724"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a><span data-ttu-id="29e3c-101">DeflateStream использует собственные интерфейсы API для распаковки</span><span class="sxs-lookup"><span data-stu-id="29e3c-101">DeflateStream uses native APIs for decompression</span></span>

#### <a name="details"></a><span data-ttu-id="29e3c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="29e3c-102">Details</span></span>

<span data-ttu-id="29e3c-103">Начиная с .NET Framework 4.7.2 реализация распаковки в классе `T:System.IO.Compression.DeflateStream` была изменена и теперь использует собственные API Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="29e3c-103">Starting with the .NET Framework 4.7.2, the implementation of decompression in the `T:System.IO.Compression.DeflateStream` class has changed to use native Windows APIs by default.</span></span> <span data-ttu-id="29e3c-104">Как правило, это приводит к значительному повышению производительности.</span><span class="sxs-lookup"><span data-stu-id="29e3c-104">Typically, this results in a substantial performance improvement.</span></span> <span data-ttu-id="29e3c-105">Во всех приложениях .NET, предназначенных для .NET Framework 4.7.2 или более поздней версии, используется собственная реализация. Это изменение может привести к некоторым отличиям в поведении, в том числе:</span><span class="sxs-lookup"><span data-stu-id="29e3c-105">All .NET applications targeting the .NET Framework version 4.7.2 or higher use the native implementation.This change might result in some differences in behavior, which include:</span></span>

- <span data-ttu-id="29e3c-106">Могут отличаться сообщения об исключениях.</span><span class="sxs-lookup"><span data-stu-id="29e3c-106">Exception messages may be different.</span></span> <span data-ttu-id="29e3c-107">Однако тип исключения не изменится.</span><span class="sxs-lookup"><span data-stu-id="29e3c-107">However, the type of exception thrown remains the same.</span></span>
- <span data-ttu-id="29e3c-108">Могут иначе обрабатываться некоторые особые ситуации, например, если для завершения операции недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="29e3c-108">Some special situations, such as not having enough memory to complete an operation, may be handled differently.</span></span>
- <span data-ttu-id="29e3c-109">Существуют известные различия в анализе заголовка gzip (примечание: это затрагивает только набор `GZipStream` для распаковки):</span><span class="sxs-lookup"><span data-stu-id="29e3c-109">There are known differences for parsing gzip header (note: only `GZipStream` set for decompression is affected):</span></span>
- <span data-ttu-id="29e3c-110">При анализе недопустимых заголовков исключения могут возникать в разное время.</span><span class="sxs-lookup"><span data-stu-id="29e3c-110">Exceptions when parsing invalid headers may be thrown at different times.</span></span>
- <span data-ttu-id="29e3c-111">Собственная реализация требует установку значений для некоторых зарезервированных флагов в заголовке gzip (т. е. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) в соответствии со спецификацией, что может приводить к исключению там, где ранее недопустимые значения игнорировались.</span><span class="sxs-lookup"><span data-stu-id="29e3c-111">The native implementation enforces that values for some reserved flags inside the gzip header (i.e. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) are set according to the specification, which may cause it to throw an exception where previously invalid values were ignored.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="29e3c-112">Предложение</span><span class="sxs-lookup"><span data-stu-id="29e3c-112">Suggestion</span></span>

<span data-ttu-id="29e3c-113">Если распаковка с собственными API-интерфейсами отрицательно повлияла на поведение приложения, этот компонент можно отключить, добавив переключатель `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` в раздел `runtime` файла app.config и установив для него значение `true`:</span><span class="sxs-lookup"><span data-stu-id="29e3c-113">If decompression with native APIs has adversely affected the behavior of your app, you can opt out of this feature by adding the `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` switch to the `runtime` section of your app.config file and setting it to `true`:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="29e3c-114">name</span><span class="sxs-lookup"><span data-stu-id="29e3c-114">Name</span></span>    | <span data-ttu-id="29e3c-115">Значение</span><span class="sxs-lookup"><span data-stu-id="29e3c-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="29e3c-116">Область</span><span class="sxs-lookup"><span data-stu-id="29e3c-116">Scope</span></span>   | <span data-ttu-id="29e3c-117">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="29e3c-117">Minor</span></span>       |
| <span data-ttu-id="29e3c-118">Version</span><span class="sxs-lookup"><span data-stu-id="29e3c-118">Version</span></span> | <span data-ttu-id="29e3c-119">4.7.2</span><span class="sxs-lookup"><span data-stu-id="29e3c-119">4.7.2</span></span>       |
| <span data-ttu-id="29e3c-120">Type</span><span class="sxs-lookup"><span data-stu-id="29e3c-120">Type</span></span>    | <span data-ttu-id="29e3c-121">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="29e3c-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="29e3c-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="29e3c-122">Affected APIs</span></span>

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
