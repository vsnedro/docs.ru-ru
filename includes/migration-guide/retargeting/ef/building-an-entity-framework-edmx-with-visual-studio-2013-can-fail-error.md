---
ms.openlocfilehash: c5099f610569f7788bb829a2153006d20d8a4ea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615760"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a><span data-ttu-id="de9a0-101">Построение EDMX Entity Framework с помощью Visual Studio 2013 может завершиться ошибкой MSB4062, если используются задачи EntityDeploySplit или EntityClean</span><span class="sxs-lookup"><span data-stu-id="de9a0-101">Building an Entity Framework edmx with Visual Studio 2013 can fail with error MSB4062 if using the EntityDeploySplit or EntityClean tasks</span></span>

#### <a name="details"></a><span data-ttu-id="de9a0-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="de9a0-102">Details</span></span>

<span data-ttu-id="de9a0-103">Инструменты MSBuild 12.0 (в составе Visual Studio 2013) изменили расположение файлов MSBuild, что привело к недействительности старых файлов целей построения Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="de9a0-103">MSBuild 12.0 tools (included in Visual Studio 2013) changed MSBuild file locations, causing older Entity Framework targets files to be invalid.</span></span> <span data-ttu-id="de9a0-104">В результате задачи `EntityDeploySplit` и `EntityClean` завершаются ошибкой, так как они не могут найти `Microsoft.Data.Entity.Build.Tasks.dll`.</span><span class="sxs-lookup"><span data-stu-id="de9a0-104">The result is that `EntityDeploySplit` and `EntityClean` tasks fail because they are unable to find `Microsoft.Data.Entity.Build.Tasks.dll`.</span></span> <span data-ttu-id="de9a0-105">Обратите внимание, что это нарушение возникает вследствие изменения набора инструментов (MSBuild и Visual Studio), а не из-за изменения платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de9a0-105">Note that this break is because of a toolset (MSBuild/VS) change, not because of a .NET Framework change.</span></span> <span data-ttu-id="de9a0-106">Оно происходит только при обновлении средств разработчика, а не просто при обновлении .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de9a0-106">It will only occur when upgrading developer tools, not when merely upgrading the .NET Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="de9a0-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="de9a0-107">Suggestion</span></span>

<span data-ttu-id="de9a0-108">Начиная с .NET Framework 4.6 файлы целей построения Entity Framework предназначены для работы с новым макетом MSBuild.</span><span class="sxs-lookup"><span data-stu-id="de9a0-108">Entity Framework targets files are fixed to work with the new MSBuild layout beginning in the .NET Framework 4.6.</span></span> <span data-ttu-id="de9a0-109">Проблема будет решена после обновления до этой версии.</span><span class="sxs-lookup"><span data-stu-id="de9a0-109">Upgrading to that version of the Framework will fix this issue.</span></span> <span data-ttu-id="de9a0-110">Кроме того, [это](https://stackoverflow.com/a/24249247/131944) решение можно использовать для исправления файлов целей построения напрямую.</span><span class="sxs-lookup"><span data-stu-id="de9a0-110">Alternatively, [this workaround](https://stackoverflow.com/a/24249247/131944) can be used to patch the targets files directly.</span></span>

| <span data-ttu-id="de9a0-111">name</span><span class="sxs-lookup"><span data-stu-id="de9a0-111">Name</span></span>    | <span data-ttu-id="de9a0-112">Значение</span><span class="sxs-lookup"><span data-stu-id="de9a0-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="de9a0-113">Область</span><span class="sxs-lookup"><span data-stu-id="de9a0-113">Scope</span></span>   | <span data-ttu-id="de9a0-114">Значительно</span><span class="sxs-lookup"><span data-stu-id="de9a0-114">Major</span></span>       |
| <span data-ttu-id="de9a0-115">Version</span><span class="sxs-lookup"><span data-stu-id="de9a0-115">Version</span></span> | <span data-ttu-id="de9a0-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="de9a0-116">4.5.1</span></span>       |
| <span data-ttu-id="de9a0-117">Type</span><span class="sxs-lookup"><span data-stu-id="de9a0-117">Type</span></span>    | <span data-ttu-id="de9a0-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="de9a0-118">Retargeting</span></span> |
