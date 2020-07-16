---
ms.openlocfilehash: f87d0dbeda6094bd745f5b580772b1161f30d0d5
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218130"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>Изменение знака разделения пути в свойстве FullName объектов ZipArchiveEntry

#### <a name="details"></a>Подробнее

Для приложений, предназначенных для .NET Framework 4.6.1 и более поздних версий, в качестве знака разделения пути в свойстве <xref:System.IO.Compression.ZipArchiveEntry.FullName> объектов <xref:System.IO.Compression.ZipArchiveEntry>, созданных перегрузками метода <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A>, вместо обратной косой черты ("\\") используется символ косой черты ("/") . Изменение обеспечивает соответствие реализации .NET разделу 4.4.17.1 [спецификации формата ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) и позволяет распаковывать ZIP-архивы в системах, отличных от Windows.<br />При распаковке ZIP-файла, созданного приложением, предназначенным для предыдущей версии платформы .NET Framework в операционных системах, отличающихся от Windows, таких как Macintosh, не удается сохранить структуру каталогов. Например, на компьютерах Macintosh создается набор файлов, имя которых объединяет путь к каталогу, вместе со всеми символами обратной косой черты ("\\"), и имя файла. В результате структура каталогов распакованных файлов не сохраняется.

#### <a name="suggestion"></a>Предложение

Влияние этого изменения на ZIP-файлы, которые распаковываются в операционной системе Windows API-интерфейсами из пространства имен .NET Framework <xref:System.IO?displayProperty=nameWithType>, должно быть минимальным, так как эти API-интерфейсы без проблем принимают в качестве знака разделения в пути как косую черту ("/"), так и обратную косую черту ("\\").<br />Если такое изменение нежелательно, от него можно отказаться, добавив параметр конфигурации в раздел [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. В следующем примере показан как раздел `<runtime>`, так и параметр отключения `Switch.System.IO.Compression.ZipFile.UseBackslash`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

Кроме того, в приложениях, предназначенных для предыдущих версий .NET Framework, но выполняемых в .NET Framework 4.6.1 и более поздних версий, можно включить такое поведение, добавив параметр конфигурации в раздел [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. Ниже показаны как раздел `<runtime>`, так и параметр включения функции `Switch.System.IO.Compression.ZipFile.UseBackslash`.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
