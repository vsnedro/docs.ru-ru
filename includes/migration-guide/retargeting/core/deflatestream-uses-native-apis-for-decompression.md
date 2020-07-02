---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614724"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a>DeflateStream использует собственные интерфейсы API для распаковки

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.7.2 реализация распаковки в классе `T:System.IO.Compression.DeflateStream` была изменена и теперь использует собственные API Windows по умолчанию. Как правило, это приводит к значительному повышению производительности. Во всех приложениях .NET, предназначенных для .NET Framework 4.7.2 или более поздней версии, используется собственная реализация. Это изменение может привести к некоторым отличиям в поведении, в том числе:

- Могут отличаться сообщения об исключениях. Однако тип исключения не изменится.
- Могут иначе обрабатываться некоторые особые ситуации, например, если для завершения операции недостаточно памяти.
- Существуют известные различия в анализе заголовка gzip (примечание: это затрагивает только набор `GZipStream` для распаковки):
- При анализе недопустимых заголовков исключения могут возникать в разное время.
- Собственная реализация требует установку значений для некоторых зарезервированных флагов в заголовке gzip (т. е. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) в соответствии со спецификацией, что может приводить к исключению там, где ранее недопустимые значения игнорировались.

#### <a name="suggestion"></a>Предложение

Если распаковка с собственными API-интерфейсами отрицательно повлияла на поведение приложения, этот компонент можно отключить, добавив переключатель `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` в раздел `runtime` файла app.config и установив для него значение `true`:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
