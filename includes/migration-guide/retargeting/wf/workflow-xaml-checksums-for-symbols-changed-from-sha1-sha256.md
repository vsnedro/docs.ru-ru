---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616292"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a><span data-ttu-id="67dd0-101">Контрольные суммы рабочего процесса XAML для символов изменены с SHA1 на SHA256</span><span class="sxs-lookup"><span data-stu-id="67dd0-101">Workflow XAML checksums for symbols changed from SHA1 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="67dd0-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="67dd0-102">Details</span></span>

<span data-ttu-id="67dd0-103">Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для файла XAML рабочего процесса, используя алгоритм хэширования.</span><span class="sxs-lookup"><span data-stu-id="67dd0-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow XAML file using a hashing algorithm.</span></span> <span data-ttu-id="67dd0-104">В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS.</span><span class="sxs-lookup"><span data-stu-id="67dd0-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="67dd0-105">Начиная с .NET Framework 4.7 алгоритм по умолчанию изменен на SHA-1.</span><span class="sxs-lookup"><span data-stu-id="67dd0-105">Starting with the .NET Framework 4.7, the default algorithm was changed to SHA1.</span></span> <span data-ttu-id="67dd0-106">Начиная с .NET Framework 4.8 алгоритм по умолчанию изменен на SHA256.</span><span class="sxs-lookup"><span data-stu-id="67dd0-106">Starting with the .NET Framework 4.8, the default algorithm was changed to SHA256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="67dd0-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="67dd0-107">Suggestion</span></span>

<span data-ttu-id="67dd0-108">Если код не может загрузить экземпляры рабочих процессов или найти подходящие символы из-за ошибки контрольной суммы, попробуйте установить для параметра `AppContext` "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" значение `true`.</span><span class="sxs-lookup"><span data-stu-id="67dd0-108">If your code is unable to load workflow instances or to find appropriate symbols due to a checksum failure, try setting the `AppContext` switch "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" to `true`.</span></span> <span data-ttu-id="67dd0-109">В коде:</span><span class="sxs-lookup"><span data-stu-id="67dd0-109">In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

<span data-ttu-id="67dd0-110">Или в конфигурации:</span><span class="sxs-lookup"><span data-stu-id="67dd0-110">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="67dd0-111">name</span><span class="sxs-lookup"><span data-stu-id="67dd0-111">Name</span></span>    | <span data-ttu-id="67dd0-112">Значение</span><span class="sxs-lookup"><span data-stu-id="67dd0-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="67dd0-113">Область</span><span class="sxs-lookup"><span data-stu-id="67dd0-113">Scope</span></span>   | <span data-ttu-id="67dd0-114">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="67dd0-114">Minor</span></span>       |
| <span data-ttu-id="67dd0-115">Version</span><span class="sxs-lookup"><span data-stu-id="67dd0-115">Version</span></span> | <span data-ttu-id="67dd0-116">4.8</span><span class="sxs-lookup"><span data-stu-id="67dd0-116">4.8</span></span>         |
| <span data-ttu-id="67dd0-117">Type</span><span class="sxs-lookup"><span data-stu-id="67dd0-117">Type</span></span>    | <span data-ttu-id="67dd0-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="67dd0-118">Retargeting</span></span> |
