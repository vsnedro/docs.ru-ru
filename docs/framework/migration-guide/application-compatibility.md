---
title: Изменения среды выполнения и целевой платформы (.NET Framework)
description: Узнайте о совместимости приложений в .NET Framework и о том, какое влияние на нее оказывают среда выполнения и изменения целевой платформы при переходе на другую версию.
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: 26f36dd34c6c5ecae8fc5ab373ff60d9e56f8245
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475493"
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="e8dce-103">Совместимость приложений в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e8dce-103">Application compatibility in the .NET Framework</span></span>

<span data-ttu-id="e8dce-104">Совместимость считается важной задачей каждого выпуска .NET.</span><span class="sxs-lookup"><span data-stu-id="e8dce-104">Compatibility is an important goal of each .NET release.</span></span> <span data-ttu-id="e8dce-105">Совместимость гарантирует, что каждая версия дополняет предыдущие и позволяет им работать так же, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="e8dce-105">Compatibility ensures that each version is additive, so previous versions will continue to work.</span></span> <span data-ttu-id="e8dce-106">С другой стороны, изменения в функциях по сравнению с предыдущими версиями (например, для улучшения производительности, устранения проблем с безопасностью или исправления ошибок) могут привести к проблемам совместимости в существующем коде или приложениях, которые запускаются в более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e8dce-106">On the other hand, changes to previous functionality (for example, to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span>

<span data-ttu-id="e8dce-107">Каждое приложение разрабатывается для конкретной версии платформы .NET Framework, которую можно указать следующими способами:</span><span class="sxs-lookup"><span data-stu-id="e8dce-107">Each app targets a specific version of the .NET Framework by:</span></span>

- <span data-ttu-id="e8dce-108">Назначив требуемую версию .NET Framework в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e8dce-108">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="e8dce-109">Указав требуемую версию .NET Framework в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e8dce-109">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="e8dce-110">Применив <xref:System.Runtime.Versioning.TargetFrameworkAttribute> к исходному коду.</span><span class="sxs-lookup"><span data-stu-id="e8dce-110">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="e8dce-111">При переходе с одной версии .NET Framework на другую необходимо учитывать изменения двух типов:</span><span class="sxs-lookup"><span data-stu-id="e8dce-111">When migrating from one version of the .NET Framework to another, there are two types of changes to consider:</span></span>

- [<span data-ttu-id="e8dce-112">Изменения среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e8dce-112">Runtime changes</span></span>](#runtime-changes)
- [<span data-ttu-id="e8dce-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e8dce-113">Retargeting changes</span></span>](#retargeting-changes)

## <a name="runtime-changes"></a><span data-ttu-id="e8dce-114">Изменения в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="e8dce-114">Runtime changes</span></span>

<span data-ttu-id="e8dce-115">Проблемы среды выполнения возникают, когда на компьютере устанавливается новая среда выполнения и изменяется поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="e8dce-115">Runtime issues are those that arise when a new runtime is placed on a machine and an app's behavior changes.</span></span> <span data-ttu-id="e8dce-116">При использовании более новой версии .NET Framework по сравнению с целевой, платформа применяет *режим совместимости* для имитации поведения старой версии.</span><span class="sxs-lookup"><span data-stu-id="e8dce-116">When running on a newer version than what was targeted, the .NET Framework uses *quirked* behavior to mimic the older targeted version.</span></span> <span data-ttu-id="e8dce-117">Приложение будет работать на новой версии платформы, но все операции с ним выполняются так, как если бы оно было запущено на более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="e8dce-117">The app runs on the newer version but acts as if it's running on the older version.</span></span> <span data-ttu-id="e8dce-118">Такая имитация позволяет устранить многие проблемы совместимости между версиями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8dce-118">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span> <span data-ttu-id="e8dce-119">Например, если двоичный файл был скомпилирован для платформы .NET Framework 4.0 и выполняется на платформе .NET Framework 4.5 или более поздней версии, он выполняется в режиме совместимости с .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="e8dce-119">For example, if a binary was compiled for .NET Framework 4.0 but runs on a machine with .NET Framework 4.5 or later, it runs in .NET Framework 4.0 compatibility mode.</span></span> <span data-ttu-id="e8dce-120">Это означает, что на его работу не влияют многие изменения в более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e8dce-120">This means that many of the changes in the later version don't affect the binary.</span></span>

<span data-ttu-id="e8dce-121">Версия платформы .NET Framework, для которой предназначено приложение, определяется целевой версией начальной сборки для домена приложения, где выполняется код.</span><span class="sxs-lookup"><span data-stu-id="e8dce-121">The version of the .NET Framework that an application targets is determined by the target version of the entry assembly for the application domain that the code runs in.</span></span> <span data-ttu-id="e8dce-122">Все дополнительные сборки, загруженные в этот домен приложения, нацелены на эту версию.</span><span class="sxs-lookup"><span data-stu-id="e8dce-122">All additional assemblies loaded in that application domain target that version.</span></span> <span data-ttu-id="e8dce-123">Например, для исполняемого файла целевая платформа будет совпадать с режимом совместимости, в котором работают все сборки в этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="e8dce-123">For example, in the case of an executable, the version that the executable targets is the compatibility mode all assemblies in that application domain run under.</span></span>

<span data-ttu-id="e8dce-124">Чтобы просмотреть список изменений среды выполнения, которые применяются к вашей среде, выберите текущую целевую версию .NET Framework, а затем новую версию, на которую вы хотите перейти:</span><span class="sxs-lookup"><span data-stu-id="e8dce-124">To see a list of runtime changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a><span data-ttu-id="e8dce-125">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e8dce-125">Retargeting changes</span></span>

<span data-ttu-id="e8dce-126">Изменения, связанные с перенацеливанием, возникают при перекомпиляции сборки с нацеливанием на новую версию.</span><span class="sxs-lookup"><span data-stu-id="e8dce-126">Retargeting changes are those that arise when an assembly is recompiled to target a newer version.</span></span> <span data-ttu-id="e8dce-127">Нацеливание на новую версию означает, что в сборке становятся доступны новые возможности, но могут возникнуть проблемы совместимости со старыми функциями.</span><span class="sxs-lookup"><span data-stu-id="e8dce-127">Targeting a newer version means the assembly opts into the new features as well as potential compatibility issues for old features.</span></span>

<span data-ttu-id="e8dce-128">Чтобы просмотреть список изменений, связанных с перенацеливанием, которые применяются к вашей среде, выберите текущую целевую версию .NET Framework, а затем новую версию, на которую вы хотите перейти:</span><span class="sxs-lookup"><span data-stu-id="e8dce-128">To see a list of retargeting changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a><span data-ttu-id="e8dce-129">Классификация последствий</span><span class="sxs-lookup"><span data-stu-id="e8dce-129">Impact classification</span></span>

<span data-ttu-id="e8dce-130">В разделах с описанием изменений в среде выполнения и изменений, связанных с перенацеливанием, например в статье [о переходе с версии 4.7.2 на 4.8](retargeting/4.7.2-4.8.md), отдельные элементы классифицируются по ожидаемым последствиям следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e8dce-130">In the topics that describe runtime and retargeting changes, for example, [Retargeting changes for migrating from 4.7.2 to 4.8](retargeting/4.7.2-4.8.md), individual items are classified by their expected impact as follows:</span></span>

<span data-ttu-id="e8dce-131">**Major**</span><span class="sxs-lookup"><span data-stu-id="e8dce-131">**Major**</span></span>\
<span data-ttu-id="e8dce-132">Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода.</span><span class="sxs-lookup"><span data-stu-id="e8dce-132">A significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="e8dce-133">**Minor**</span><span class="sxs-lookup"><span data-stu-id="e8dce-133">**Minor**</span></span>\
<span data-ttu-id="e8dce-134">Изменение, влияющее на небольшое количество приложений или требующее незначительного изменения кода.</span><span class="sxs-lookup"><span data-stu-id="e8dce-134">A change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="e8dce-135">**Edge case (Пограничный случай)** </span><span class="sxs-lookup"><span data-stu-id="e8dce-135">**Edge case**</span></span>\
<span data-ttu-id="e8dce-136">Изменение влияет на приложения в исключительных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="e8dce-136">A change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="e8dce-137">**Transparent (Прозрачный)** </span><span class="sxs-lookup"><span data-stu-id="e8dce-137">**Transparent**</span></span>\
<span data-ttu-id="e8dce-138">Изменение не оказывает особого влияния на разработчика или пользователя приложения.</span><span class="sxs-lookup"><span data-stu-id="e8dce-138">A change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="e8dce-139">При этом вносить изменения в приложения не требуется.</span><span class="sxs-lookup"><span data-stu-id="e8dce-139">The app should not require modification because of this change.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8dce-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e8dce-140">See also</span></span>

- [<span data-ttu-id="e8dce-141">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="e8dce-141">Versions and dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="e8dce-142">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="e8dce-142">What's new</span></span>](../whats-new/index.md)
- [<span data-ttu-id="e8dce-143">Устаревшие возможности</span><span class="sxs-lookup"><span data-stu-id="e8dce-143">What's obsolete</span></span>](../whats-new/whats-obsolete.md)
