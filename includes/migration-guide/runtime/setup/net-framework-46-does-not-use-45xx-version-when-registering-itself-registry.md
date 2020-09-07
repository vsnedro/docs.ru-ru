---
ms.openlocfilehash: a9011514c7c4393ec44de2c7fae88768cdccf435
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496479"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="dca5d-101">.NET Framework 4.6 не использует версию 4.5.x.x для собственной регистрации в реестре</span><span class="sxs-lookup"><span data-stu-id="dca5d-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

#### <a name="details"></a><span data-ttu-id="dca5d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="dca5d-102">Details</span></span>

<span data-ttu-id="dca5d-103">Ключ версии, установленный в реестре (<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) для платформы .NET Framework 4.6, ожидаемо начинается с "4.6", а не с "4.5".</span><span class="sxs-lookup"><span data-stu-id="dca5d-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="dca5d-104">Приложения, которые используют эти разделы реестра для определения установленных на компьютере версий .NET Framework, следует обновить таким образом, чтобы понимать, что 4.6 — это новая возможная версия, совместимая с предыдущими выпусками 4.5.x.</span><span class="sxs-lookup"><span data-stu-id="dca5d-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dca5d-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="dca5d-105">Suggestion</span></span>

<span data-ttu-id="dca5d-106">Обновите приложения, проверяющие установку версию .NET Framework 4.5 в соответствующих разделах реестра, так, чтобы они принимали версию 4.6.</span><span class="sxs-lookup"><span data-stu-id="dca5d-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>

| <span data-ttu-id="dca5d-107">name</span><span class="sxs-lookup"><span data-stu-id="dca5d-107">Name</span></span>    | <span data-ttu-id="dca5d-108">Значение</span><span class="sxs-lookup"><span data-stu-id="dca5d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dca5d-109">Область</span><span class="sxs-lookup"><span data-stu-id="dca5d-109">Scope</span></span>   |<span data-ttu-id="dca5d-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="dca5d-110">Edge</span></span>|
|<span data-ttu-id="dca5d-111">Version</span><span class="sxs-lookup"><span data-stu-id="dca5d-111">Version</span></span>|<span data-ttu-id="dca5d-112">4.6</span><span class="sxs-lookup"><span data-stu-id="dca5d-112">4.6</span></span>|
|<span data-ttu-id="dca5d-113">Type</span><span class="sxs-lookup"><span data-stu-id="dca5d-113">Type</span></span>|<span data-ttu-id="dca5d-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="dca5d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dca5d-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="dca5d-115">Affected APIs</span></span>

<span data-ttu-id="dca5d-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="dca5d-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
