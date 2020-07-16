---
ms.openlocfilehash: f87d0dbeda6094bd745f5b580772b1161f30d0d5
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218130"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a><span data-ttu-id="651cc-101">Изменение знака разделения пути в свойстве FullName объектов ZipArchiveEntry</span><span class="sxs-lookup"><span data-stu-id="651cc-101">Change in path separator character in FullName property of ZipArchiveEntry objects</span></span>

#### <a name="details"></a><span data-ttu-id="651cc-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="651cc-102">Details</span></span>

<span data-ttu-id="651cc-103">Для приложений, предназначенных для .NET Framework 4.6.1 и более поздних версий, в качестве знака разделения пути в свойстве <xref:System.IO.Compression.ZipArchiveEntry.FullName> объектов <xref:System.IO.Compression.ZipArchiveEntry>, созданных перегрузками метода <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A>, вместо обратной косой черты ("\\") используется символ косой черты ("/") .</span><span class="sxs-lookup"><span data-stu-id="651cc-103">For apps that target the .NET Framework 4.6.1 and later versions, the path separator character has changed from a backslash ("\\") to a forward slash ("/") in the <xref:System.IO.Compression.ZipArchiveEntry.FullName> property of <xref:System.IO.Compression.ZipArchiveEntry>  objects created by overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> method.</span></span> <span data-ttu-id="651cc-104">Изменение обеспечивает соответствие реализации .NET разделу 4.4.17.1 [спецификации формата ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) и позволяет распаковывать ZIP-архивы в системах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="651cc-104">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span><br /><span data-ttu-id="651cc-105">При распаковке ZIP-файла, созданного приложением, предназначенным для предыдущей версии платформы .NET Framework в операционных системах, отличающихся от Windows, таких как Macintosh, не удается сохранить структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="651cc-105">Decompressing a zip file created by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="651cc-106">Например, на компьютерах Macintosh создается набор файлов, имя которых объединяет путь к каталогу, вместе со всеми символами обратной косой черты ("\\"), и имя файла.</span><span class="sxs-lookup"><span data-stu-id="651cc-106">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="651cc-107">В результате структура каталогов распакованных файлов не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="651cc-107">As a result, the directory structure of decompressed files is not preserved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="651cc-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="651cc-108">Suggestion</span></span>

<span data-ttu-id="651cc-109">Влияние этого изменения на ZIP-файлы, которые распаковываются в операционной системе Windows API-интерфейсами из пространства имен .NET Framework <xref:System.IO?displayProperty=nameWithType>, должно быть минимальным, так как эти API-интерфейсы без проблем принимают в качестве знака разделения в пути как косую черту ("/"), так и обратную косую черту ("\\").</span><span class="sxs-lookup"><span data-stu-id="651cc-109">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO?displayProperty=nameWithType> namespace should be minimal, since these APIs can seamlessly handle either a forward slash ("/") or a backslash ("\\") as the path separator character.</span></span><br /><span data-ttu-id="651cc-110">Если такое изменение нежелательно, от него можно отказаться, добавив параметр конфигурации в раздел [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="651cc-110">If this change is undesirable, you can opt out of it by adding a configuration setting to the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="651cc-111">В следующем примере показан как раздел `<runtime>`, так и параметр отключения `Switch.System.IO.Compression.ZipFile.UseBackslash`:</span><span class="sxs-lookup"><span data-stu-id="651cc-111">The following example shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-out switch:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

<span data-ttu-id="651cc-112">Кроме того, в приложениях, предназначенных для предыдущих версий .NET Framework, но выполняемых в .NET Framework 4.6.1 и более поздних версий, можно включить такое поведение, добавив параметр конфигурации в раздел [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="651cc-112">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="651cc-113">Ниже показаны как раздел `<runtime>`, так и параметр включения функции `Switch.System.IO.Compression.ZipFile.UseBackslash`.</span><span class="sxs-lookup"><span data-stu-id="651cc-113">The following shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-in switch.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| <span data-ttu-id="651cc-114">name</span><span class="sxs-lookup"><span data-stu-id="651cc-114">Name</span></span>    | <span data-ttu-id="651cc-115">Значение</span><span class="sxs-lookup"><span data-stu-id="651cc-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="651cc-116">Область</span><span class="sxs-lookup"><span data-stu-id="651cc-116">Scope</span></span>   | <span data-ttu-id="651cc-117">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="651cc-117">Edge</span></span>        |
| <span data-ttu-id="651cc-118">Version</span><span class="sxs-lookup"><span data-stu-id="651cc-118">Version</span></span> | <span data-ttu-id="651cc-119">4.6.1</span><span class="sxs-lookup"><span data-stu-id="651cc-119">4.6.1</span></span>       |
| <span data-ttu-id="651cc-120">Type</span><span class="sxs-lookup"><span data-stu-id="651cc-120">Type</span></span>    | <span data-ttu-id="651cc-121">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="651cc-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="651cc-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="651cc-122">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
