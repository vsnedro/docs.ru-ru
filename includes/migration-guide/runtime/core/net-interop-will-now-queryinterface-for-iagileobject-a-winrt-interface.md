---
ms.openlocfilehash: 65fa5d8629ce8e426cf1623590a056e5cad0b91f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496518"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a><span data-ttu-id="6a11b-101">Взаимодействие .NET теперь будет использовать QueryInterface для IAgileObject (интерфейс WinRT)</span><span class="sxs-lookup"><span data-stu-id="6a11b-101">.NET Interop will now QueryInterface for IAgileObject (a WinRT interface)</span></span>

#### <a name="details"></a><span data-ttu-id="6a11b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6a11b-102">Details</span></span>

<span data-ttu-id="6a11b-103">При использовании события WinRT с делегатом .NET Windows будет использовать QI для IAgileObject начиная с .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="6a11b-103">When using a WinRT event with a .NET delegate, Windows will QI for IAgileObject starting with the .NET Framework 4.8.</span></span>  <span data-ttu-id="6a11b-104">В предыдущих версиях .NET Framework среда выполнения некорректно обрабатывала QI и на событие невозможно было подписаться.</span><span class="sxs-lookup"><span data-stu-id="6a11b-104">In previous versions of the .NET Framework, the runtime would fail that QI, and the event could not be subscribed.</span></span><ul><li><span data-ttu-id="6a11b-105">[x] Режим совместимости</span><span class="sxs-lookup"><span data-stu-id="6a11b-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="6a11b-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="6a11b-106">Suggestion</span></span>

<span data-ttu-id="6a11b-107">Если включение QI для IAgileObject прерывает выполнение, этот код можно отключить, задав следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="6a11b-107">If enabling the QI for IAgileObject breaks execution, you can disable this code by setting the following configuration.</span></span> <h4><span data-ttu-id="6a11b-108">Метод 1. переменная среды;</span><span class="sxs-lookup"><span data-stu-id="6a11b-108">Method 1: Environment variable</span></span></h4> <span data-ttu-id="6a11b-109">Установите следующую переменную среды: COMPLUS_DisableCCWSupportIAgileObject=1. Этот метод влияет на любую среду, которая наследует эту переменную среды.</span><span class="sxs-lookup"><span data-stu-id="6a11b-109">Set the following environment variable:COMPLUS_DisableCCWSupportIAgileObject=1This method affects any environment that inherits this environment variable.</span></span> <span data-ttu-id="6a11b-110">Это может быть только один консольный сеанс или весь компьютер, если задать переменную среды глобально.</span><span class="sxs-lookup"><span data-stu-id="6a11b-110">This might be just a single console session, or it might affect the entire machine if you set the environment variable globally.</span></span> <span data-ttu-id="6a11b-111">Имя переменной среды не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="6a11b-111">The environment variable name is not case-sensitive.</span></span> <h4><span data-ttu-id="6a11b-112">Метод 2. Реестр</span><span class="sxs-lookup"><span data-stu-id="6a11b-112">Method 2: Registry</span></span></h4> <span data-ttu-id="6a11b-113">В редакторе реестра (regedit.exe) найдите один из следующих подключей: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFramework. Затем добавьте следующее: Имя значения: DisableCCWSupportIAgileObject. Тип: DWORD (32-разрядный). Значение (также называется REG_WORD). Значение: 1. Вы можете использовать средство Windows REG.EXE, чтобы добавить это значение из командной строки или среды сценария.</span><span class="sxs-lookup"><span data-stu-id="6a11b-113">Using Registry Editor (regedit.exe), find either of the following subkeys:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkThen add the following:Value name: DisableCCWSupportIAgileObject Type: DWORD (32-bit) Value (also called REG_WORD) Value: 1You can use the Windows REG.EXE tool to add this value from a command-line or scripting environment.</span></span> <span data-ttu-id="6a11b-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="6a11b-114">For example:</span></span><pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre><span data-ttu-id="6a11b-115">В этом случае <code>HKLM</code> используется вместо <code>HKEY_LOCAL_MACHINE</code>.</span><span class="sxs-lookup"><span data-stu-id="6a11b-115">In this case, <code>HKLM</code> is used instead of <code>HKEY_LOCAL_MACHINE</code>.</span></span> <span data-ttu-id="6a11b-116">Для просмотра справки по этому синтаксису используйте <code>reg add /?</code>.</span><span class="sxs-lookup"><span data-stu-id="6a11b-116">Use <code>reg add /?</code> to see help on this syntax.</span></span> <span data-ttu-id="6a11b-117">Имя значения реестра обрабатывается без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="6a11b-117">The registry value name is not case-sensitive.</span></span>

| <span data-ttu-id="6a11b-118">name</span><span class="sxs-lookup"><span data-stu-id="6a11b-118">Name</span></span>    | <span data-ttu-id="6a11b-119">Значение</span><span class="sxs-lookup"><span data-stu-id="6a11b-119">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6a11b-120">Область</span><span class="sxs-lookup"><span data-stu-id="6a11b-120">Scope</span></span>   |<span data-ttu-id="6a11b-121">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="6a11b-121">Edge</span></span>|
|<span data-ttu-id="6a11b-122">Version</span><span class="sxs-lookup"><span data-stu-id="6a11b-122">Version</span></span>|<span data-ttu-id="6a11b-123">4.8</span><span class="sxs-lookup"><span data-stu-id="6a11b-123">4.8</span></span>|
|<span data-ttu-id="6a11b-124">Type</span><span class="sxs-lookup"><span data-stu-id="6a11b-124">Type</span></span>|<span data-ttu-id="6a11b-125">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6a11b-125">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6a11b-126">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6a11b-126">Affected APIs</span></span>

<span data-ttu-id="6a11b-127">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="6a11b-127">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
