---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616101"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a><span data-ttu-id="6bffa-101">Задача ResolveAssemblyReference теперь предупреждает о зависимостях с неправильной архитектурой</span><span class="sxs-lookup"><span data-stu-id="6bffa-101">ResolveAssemblyReference task now warns of dependencies with the wrong architecture</span></span>

#### <a name="details"></a><span data-ttu-id="6bffa-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6bffa-102">Details</span></span>

<span data-ttu-id="6bffa-103">Задача выдает предупреждение (MSB3270), которое означает, что ссылка или ее зависимости не соответствуют архитектуре приложения.</span><span class="sxs-lookup"><span data-stu-id="6bffa-103">The task emits a warning, MSB3270, which indicates that a reference or any of its dependencies does not match the app's architecture.</span></span> <span data-ttu-id="6bffa-104">Например, это происходит, если приложение, скомпилированное с параметром `AnyCPU`, содержит 32-разрядную ссылку.</span><span class="sxs-lookup"><span data-stu-id="6bffa-104">For example, this occurs if an app that was compiled with the `AnyCPU` option includes an x86 reference.</span></span> <span data-ttu-id="6bffa-105">Такой сценарий может привести к сбою приложения во время выполнения (в этом случае: если приложение развертывается как 64-разрядный процесс).</span><span class="sxs-lookup"><span data-stu-id="6bffa-105">Such a scenario could result in an app failure at run time (in this case, if the app is deployed as an x64 process).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6bffa-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="6bffa-106">Suggestion</span></span>

<span data-ttu-id="6bffa-107">Существует две области влияния.</span><span class="sxs-lookup"><span data-stu-id="6bffa-107">There are two areas of impact:</span></span>

- <span data-ttu-id="6bffa-108">Во время перекомпиляции выдаются предупреждения, которые отсутствовали при компиляции в предыдущей версии MSBuild.</span><span class="sxs-lookup"><span data-stu-id="6bffa-108">Recompilation generates warnings that did not appear when the app was compiled under a previous version of MSBuild.</span></span> <span data-ttu-id="6bffa-109">Однако поскольку в предупреждении указан возможный источник ошибки среды выполнения, его следует проверить.</span><span class="sxs-lookup"><span data-stu-id="6bffa-109">However, because the warning identifies a possible source of runtime failure, it should be investigated and addressed.</span></span>
- <span data-ttu-id="6bffa-110">Если предупреждения считаются ошибками, приложение скомпилировано не будет.</span><span class="sxs-lookup"><span data-stu-id="6bffa-110">If warnings are treated as errors, the app will fail to compile.</span></span>

| <span data-ttu-id="6bffa-111">name</span><span class="sxs-lookup"><span data-stu-id="6bffa-111">Name</span></span>    | <span data-ttu-id="6bffa-112">Значение</span><span class="sxs-lookup"><span data-stu-id="6bffa-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6bffa-113">Область</span><span class="sxs-lookup"><span data-stu-id="6bffa-113">Scope</span></span>   | <span data-ttu-id="6bffa-114">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="6bffa-114">Minor</span></span>       |
| <span data-ttu-id="6bffa-115">Version</span><span class="sxs-lookup"><span data-stu-id="6bffa-115">Version</span></span> | <span data-ttu-id="6bffa-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="6bffa-116">4.5.1</span></span>       |
| <span data-ttu-id="6bffa-117">Type</span><span class="sxs-lookup"><span data-stu-id="6bffa-117">Type</span></span>    | <span data-ttu-id="6bffa-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="6bffa-118">Retargeting</span></span> |
