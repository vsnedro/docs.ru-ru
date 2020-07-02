---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614839"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a><span data-ttu-id="ab58b-101">Контрольные суммы рабочего процесса переведены с MD5 на SHA1</span><span class="sxs-lookup"><span data-stu-id="ab58b-101">Workflow checksums changed from MD5 to SHA1</span></span>

#### <a name="details"></a><span data-ttu-id="ab58b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ab58b-102">Details</span></span>

<span data-ttu-id="ab58b-103">Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для экземпляра рабочего процесса, используя алгоритм хэширования.</span><span class="sxs-lookup"><span data-stu-id="ab58b-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow instance using a hashing algorithm.</span></span> <span data-ttu-id="ab58b-104">В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS.</span><span class="sxs-lookup"><span data-stu-id="ab58b-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="ab58b-105">Начиная с .NET Framework 4.7 используется алгоритм SHA-1.</span><span class="sxs-lookup"><span data-stu-id="ab58b-105">Starting with the .NET Framework 4.7, the algorithm is SHA1.</span></span> <span data-ttu-id="ab58b-106">Если в коде материализованы эти контрольные суммы, они будут несовместимы.</span><span class="sxs-lookup"><span data-stu-id="ab58b-106">If your code has persisted these checksums, they will be incompatible.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ab58b-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="ab58b-107">Suggestion</span></span>

<span data-ttu-id="ab58b-108">Если код не может загрузить экземпляры рабочих процессов из-за ошибки контрольной суммы, попробуйте установить для параметра &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; переключателя `AppContext` значение true. В коде:</span><span class="sxs-lookup"><span data-stu-id="ab58b-108">If your code is unable to load workflow instances due to a checksum failure, try setting the `AppContext` switch &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; to true.In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

<span data-ttu-id="ab58b-109">Или в конфигурации:</span><span class="sxs-lookup"><span data-stu-id="ab58b-109">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="ab58b-110">name</span><span class="sxs-lookup"><span data-stu-id="ab58b-110">Name</span></span>    | <span data-ttu-id="ab58b-111">Значение</span><span class="sxs-lookup"><span data-stu-id="ab58b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ab58b-112">Область</span><span class="sxs-lookup"><span data-stu-id="ab58b-112">Scope</span></span>   | <span data-ttu-id="ab58b-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ab58b-113">Minor</span></span>       |
| <span data-ttu-id="ab58b-114">Version</span><span class="sxs-lookup"><span data-stu-id="ab58b-114">Version</span></span> | <span data-ttu-id="ab58b-115">4.7</span><span class="sxs-lookup"><span data-stu-id="ab58b-115">4.7</span></span>         |
| <span data-ttu-id="ab58b-116">Type</span><span class="sxs-lookup"><span data-stu-id="ab58b-116">Type</span></span>    | <span data-ttu-id="ab58b-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ab58b-117">Retargeting</span></span> |
