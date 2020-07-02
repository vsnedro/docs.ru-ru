---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614797"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a><span data-ttu-id="c102e-101">Трассировки стека, полученные при использовании переносимых PDB-файлов, теперь включают сведения об исходном файле и строке по запросу</span><span class="sxs-lookup"><span data-stu-id="c102e-101">Stack traces obtained when using portable PDBs now include source file and line information if requested</span></span>

#### <a name="details"></a><span data-ttu-id="c102e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c102e-102">Details</span></span>

<span data-ttu-id="c102e-103">Начиная с .NET Framework 4.7.2 трассировки стека, полученные при использовании переносимых PDB-файлов, включают сведения об исходном файле и строке по запросу.</span><span class="sxs-lookup"><span data-stu-id="c102e-103">Starting with .NET Framework 4.7.2, stack traces obtained when using portable PDBs include source file and line information when requested.</span></span> <span data-ttu-id="c102e-104">В версиях до .NET Framework 4.7.2 сведения об исходном файле и строке были недоступны при использовании переносимых PDB-файлов, даже по явному запросу.</span><span class="sxs-lookup"><span data-stu-id="c102e-104">In versions prior to .NET Framework 4.7.2, source file and line information would be unavailable when using portable PDBs even if explicitly requested.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c102e-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="c102e-105">Suggestion</span></span>

<span data-ttu-id="c102e-106">Для приложений, предназначенных для .NET Framework 4.7.2, можно отказаться от вывода сведений об исходном файле и строке при использовании переносимых PDB-файлов, если это нежелательно, добавив следующую строку в раздел `<runtime>` файла `app.config`:</span><span class="sxs-lookup"><span data-stu-id="c102e-106">For applications that target the .NET Framework 4.7.2, you can opt out of the source file and line information when using portable PDBs if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

<span data-ttu-id="c102e-107">Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.7.2 или более поздней версии, можно включить вывод сведений об исходном файле и строке при использовании переносимых PDB-файлов, добавив следующую строку в раздел `<runtime>` файла `app.config`:</span><span class="sxs-lookup"><span data-stu-id="c102e-107">For applications that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.2 or later, you can opt in to the source file and line information when using portable PDBs by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| <span data-ttu-id="c102e-108">name</span><span class="sxs-lookup"><span data-stu-id="c102e-108">Name</span></span>    | <span data-ttu-id="c102e-109">Значение</span><span class="sxs-lookup"><span data-stu-id="c102e-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c102e-110">Область</span><span class="sxs-lookup"><span data-stu-id="c102e-110">Scope</span></span>   | <span data-ttu-id="c102e-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="c102e-111">Edge</span></span>        |
| <span data-ttu-id="c102e-112">Version</span><span class="sxs-lookup"><span data-stu-id="c102e-112">Version</span></span> | <span data-ttu-id="c102e-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="c102e-113">4.7.2</span></span>       |
| <span data-ttu-id="c102e-114">Type</span><span class="sxs-lookup"><span data-stu-id="c102e-114">Type</span></span>    | <span data-ttu-id="c102e-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="c102e-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c102e-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c102e-116">Affected APIs</span></span>

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
