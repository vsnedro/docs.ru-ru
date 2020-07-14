---
title: Совместимость политики разграничения доступа кода и ее миграция
description: Ознакомьтесь со сводкой и ссылками на раздел о совместимости и миграции политик управления доступом для кода в .NET 4.
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: e5affd9d16635fa28342b5b7390a083185975f2b
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281736"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="f614b-103">Совместимость политики разграничения доступа кода и ее миграция</span><span class="sxs-lookup"><span data-stu-id="f614b-103">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="f614b-104">Часть политики разграничения доступа кода (CAS) стала устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f614b-104">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="f614b-105">В результате вы можете столкнуться с предупреждениями компиляции и исключениями среды выполнения, если вы вызываете устаревшие типы и члены [явно](#explicit_use) или [неявно](#implicit_use) (через другие типы и члены).</span><span class="sxs-lookup"><span data-stu-id="f614b-105">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="f614b-106">Избежать появления таких предупреждений и ошибок можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="f614b-106">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="f614b-107">[Переход](#migration) на .NET Framework 4 замен для устаревших вызовов.</span><span class="sxs-lookup"><span data-stu-id="f614b-107">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="f614b-108">\- или -</span><span class="sxs-lookup"><span data-stu-id="f614b-108">\- or -</span></span>

- <span data-ttu-id="f614b-109">Использование [ \<NetFx40_LegacySecurityPolicy> элемента конфигурации](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) для выбора устаревшей политики разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="f614b-109">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="f614b-110">В этом разделе содержатся следующие подразделы.</span><span class="sxs-lookup"><span data-stu-id="f614b-110">This topic contains the following sections:</span></span>

- [<span data-ttu-id="f614b-111">Явное использование</span><span class="sxs-lookup"><span data-stu-id="f614b-111">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="f614b-112">Неявное использование</span><span class="sxs-lookup"><span data-stu-id="f614b-112">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="f614b-113">Ошибки и предупреждения</span><span class="sxs-lookup"><span data-stu-id="f614b-113">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="f614b-114">Миграция: замена устаревших вызовов</span><span class="sxs-lookup"><span data-stu-id="f614b-114">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="f614b-115">Совместимость: использование политики разграничения доступа кода прежних версий</span><span class="sxs-lookup"><span data-stu-id="f614b-115">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="f614b-116">Явное использование</span><span class="sxs-lookup"><span data-stu-id="f614b-116">Explicit Use</span></span>

<span data-ttu-id="f614b-117">Члены, которые непосредственно управляют политикой безопасности или требуют политики разграничения доступа кода для изоляции в "песочнице", являются устаревшими и по умолчанию вызывают ошибки.</span><span class="sxs-lookup"><span data-stu-id="f614b-117">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="f614b-118">Примеры:</span><span class="sxs-lookup"><span data-stu-id="f614b-118">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="f614b-119">Неявное использование</span><span class="sxs-lookup"><span data-stu-id="f614b-119">Implicit Use</span></span>

<span data-ttu-id="f614b-120">Несколько перегруженных методов загрузки сборки вызывают ошибки из-за неявного использования политики разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="f614b-120">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="f614b-121">Эти перегруженные методы принимают параметр <xref:System.Security.Policy.Evidence>, разрешающий политику разграничения доступа кода, и предоставляют сборке набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="f614b-121">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="f614b-122">Рассмотрим некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="f614b-122">Here are some examples.</span></span> <span data-ttu-id="f614b-123">Устаревшие перегрузки — это перегрузки, принимающие в качестве параметра <xref:System.Security.Policy.Evidence>.</span><span class="sxs-lookup"><span data-stu-id="f614b-123">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="f614b-124">Ошибки и предупреждения</span><span class="sxs-lookup"><span data-stu-id="f614b-124">Errors and Warnings</span></span>

<span data-ttu-id="f614b-125">При использовании устаревших типов и членов возникают указанные ниже сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f614b-125">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="f614b-126">Обратите внимание, что сам тип <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> не является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="f614b-126">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="f614b-127">Предупреждение времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="f614b-127">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="f614b-128">Исключение времени выполнения:</span><span class="sxs-lookup"><span data-stu-id="f614b-128">Run-time exception:</span></span>

<span data-ttu-id="f614b-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="f614b-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="f614b-130">Миграция: замена устаревших вызовов</span><span class="sxs-lookup"><span data-stu-id="f614b-130">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="f614b-131">Определение уровня доверия сборки</span><span class="sxs-lookup"><span data-stu-id="f614b-131">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="f614b-132">Политика разграничения доступа кода часто используется для определения набора разрешений или уровня доверия, предоставляемых сборке или домену приложения.</span><span class="sxs-lookup"><span data-stu-id="f614b-132">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="f614b-133">.NET Framework 4 предоставляет следующие полезные свойства, не требующие разрешения политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="f614b-133">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="f614b-134">Изолирование домена приложения</span><span class="sxs-lookup"><span data-stu-id="f614b-134">Application Domain Sandboxing</span></span>

<span data-ttu-id="f614b-135">Метод <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>, как правило, используется для изолирования сборок в домене приложений.</span><span class="sxs-lookup"><span data-stu-id="f614b-135">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="f614b-136">.NET Framework 4 предоставляет члены, которые не должны использоваться <xref:System.Security.Policy.PolicyLevel> для этой цели.</span><span class="sxs-lookup"><span data-stu-id="f614b-136">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="f614b-137">Дополнительные сведения см. [в разделе инструкции. Запуск частично доверенного кода в песочнице](how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="f614b-137">For more information, see [How to: Run Partially Trusted Code in a Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="f614b-138">Определение безопасного или приемлемого набора разрешений для частично доверенного кода</span><span class="sxs-lookup"><span data-stu-id="f614b-138">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="f614b-139">Основным приложениям часто требуется определить разрешения, подходящие для изоляции кода, запускаемого из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="f614b-139">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="f614b-140">Прежде чем приступить к работе с .NET Framework 4, политика CAS предоставила способ сделать это с помощью <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> метода.</span><span class="sxs-lookup"><span data-stu-id="f614b-140">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f614b-141">В качестве замены .NET Framework 4 предоставляет <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> метод, который возвращает надежный стандартный набор разрешений для предоставленного свидетельства.</span><span class="sxs-lookup"><span data-stu-id="f614b-141">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="f614b-142">Сценарии без использования "песочницы": перегруженные методы для загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="f614b-142">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="f614b-143">Перегруженные методы загрузки сборок применяются, если вместо изоляции сборки в "песочнице" необходимо использовать параметры, которые недоступны иначе.</span><span class="sxs-lookup"><span data-stu-id="f614b-143">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="f614b-144">Начиная с .NET Framework 4, перегрузки загрузки сборок, не требующие объекта в <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> качестве параметра, следует <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType> включить этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="f614b-144">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="f614b-145">Чтобы поместить сборку в изолированную среду, воспользуйтесь перегрузкой <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f614b-145">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="f614b-146">Совместимость: использование политики разграничения доступа кода прежних версий</span><span class="sxs-lookup"><span data-stu-id="f614b-146">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="f614b-147">[ \<NetFx40_LegacySecurityPolicy> Элемент Configuration](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) позволяет указать, что процесс или библиотека использует устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="f614b-147">The [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="f614b-148">При включении этого элемента политика и перегруженные объекты свидетельств будут работать как в предыдущих версиях платформы.</span><span class="sxs-lookup"><span data-stu-id="f614b-148">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="f614b-149">Поведение политики разграничения доступа кода определяется для каждой версии среды выполнения, поэтому изменение этой политики для одной версии среды выполнения не повлияет на ее поведение в других версиях.</span><span class="sxs-lookup"><span data-stu-id="f614b-149">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f614b-150">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f614b-150">See also</span></span>

- [<span data-ttu-id="f614b-151">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="f614b-151">How to: Run Partially Trusted Code in a Sandbox</span></span>](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="f614b-152">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="f614b-152">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
