---
title: Прозрачный с точки зрения безопасности код, уровень 2
description: Разобраться в прозрачном коде уровня 2. См. раздел примеры использования и поведения, шаблоны переопределения, правила наследования и многое другое.
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: bbff7b53bacd50746de56c8dba85cdc9e4b1ad9b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556412"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="f0299-104">Прозрачный с точки зрения безопасности код, уровень 2</span><span class="sxs-lookup"><span data-stu-id="f0299-104">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="f0299-105">Прозрачность уровня 2 появилась в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f0299-105">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="f0299-106">Ключевыми элементами этой модели являются следующие компоненты: прозрачный код, надежный с точки зрения безопасности код и критический с точки зрения безопасности код.</span><span class="sxs-lookup"><span data-stu-id="f0299-106">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="f0299-107">Прозрачный код (в том числе код с полным доверием) может вызывать только другой прозрачный или надежный с точки зрения безопасности код.</span><span class="sxs-lookup"><span data-stu-id="f0299-107">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="f0299-108">Прозрачный код может выполнять только действия, разрешенные набором разрешений частичного доверия домена (если он существует).</span><span class="sxs-lookup"><span data-stu-id="f0299-108">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="f0299-109">Прозрачный код не может выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f0299-109">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="f0299-110">выполнять метод <xref:System.Security.CodeAccessPermission.Assert%2A> или повышение привилегий;</span><span class="sxs-lookup"><span data-stu-id="f0299-110">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="f0299-111">содержать небезопасный или непроверяемый код;</span><span class="sxs-lookup"><span data-stu-id="f0299-111">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="f0299-112">напрямую вызывать критический код;</span><span class="sxs-lookup"><span data-stu-id="f0299-112">Directly call critical code.</span></span>

  - <span data-ttu-id="f0299-113">вызывать машинный код или код с атрибутом <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>;</span><span class="sxs-lookup"><span data-stu-id="f0299-113">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="f0299-114">вызывать член, защищенный с помощью <xref:System.Security.Permissions.SecurityAction.LinkDemand>;</span><span class="sxs-lookup"><span data-stu-id="f0299-114">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="f0299-115">наследовать от критических типов.</span><span class="sxs-lookup"><span data-stu-id="f0299-115">Inherit from critical types.</span></span>

  <span data-ttu-id="f0299-116">Кроме того, прозрачные методы не могут переопределять критические виртуальные методы или реализовывать критические методы интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f0299-116">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="f0299-117">Надежный с точки зрения безопасности код имеет полное доверие, но может вызываться прозрачным кодом.</span><span class="sxs-lookup"><span data-stu-id="f0299-117">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="f0299-118">Он предоставляет ограниченный объем кода с полным доверием. В надежном с точки зрения безопасности коде выполняются проверки на правильность и безопасность.</span><span class="sxs-lookup"><span data-stu-id="f0299-118">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="f0299-119">Критический с точки зрения безопасности код может вызывать любой код, но не может вызываться из прозрачного кода.</span><span class="sxs-lookup"><span data-stu-id="f0299-119">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="f0299-120">Примеры использования и поведение</span><span class="sxs-lookup"><span data-stu-id="f0299-120">Usage Examples and Behaviors</span></span>

<span data-ttu-id="f0299-121">Чтобы указать правила .NET Framework 4 (прозрачность уровня 2), используйте следующую аннотацию для сборки:</span><span class="sxs-lookup"><span data-stu-id="f0299-121">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="f0299-122">Чтобы зафиксировать правила платформы .NET Framework 2.0 (прозрачность уровня 1), используйте следующую заметку:</span><span class="sxs-lookup"><span data-stu-id="f0299-122">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="f0299-123">Если сборка не замечается, то по умолчанию используются правила .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f0299-123">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="f0299-124">Однако рекомендуется использовать <xref:System.Security.SecurityRulesAttribute> атрибут, а не в зависимости от значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0299-124">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="f0299-125">Заметка на уровне сборки</span><span class="sxs-lookup"><span data-stu-id="f0299-125">Assembly-wide Annotation</span></span>

<span data-ttu-id="f0299-126">Ниже перечислены правила, которые применяются к использованию атрибутов на уровне сборки.</span><span class="sxs-lookup"><span data-stu-id="f0299-126">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="f0299-127">Без атрибутов: если атрибуты не указаны, то среда выполнения рассматривает код как критический с точки зрения безопасности за исключением случаев, когда это нарушает правило наследования (например, при переопределении или при реализации прозрачного виртуального метода или метода интерфейса).</span><span class="sxs-lookup"><span data-stu-id="f0299-127">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="f0299-128">В таких случаях методы являются надежными с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f0299-128">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="f0299-129">Если атрибут не указан, то определение правил прозрачности выполняется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f0299-129">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="f0299-130">`SecurityTransparent`: весь код является прозрачным, а сборка не будет выполнять небезопасных действий или действий, требующих наличия особых привилегий.</span><span class="sxs-lookup"><span data-stu-id="f0299-130">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="f0299-131">`SecurityCritical`: весь код типов в этой сборке является критическим, а остальной код — прозрачным.</span><span class="sxs-lookup"><span data-stu-id="f0299-131">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="f0299-132">Этот случай аналогичен отсутствию атрибутов, но среда CLR не определяет правила прозрачности автоматически.</span><span class="sxs-lookup"><span data-stu-id="f0299-132">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="f0299-133">Например, если переопределить виртуальный или абстрактный метод или реализовать метод интерфейса, то такой метод по умолчанию будет прозрачным.</span><span class="sxs-lookup"><span data-stu-id="f0299-133">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="f0299-134">Следует явным образом пометить метод как `SecurityCritical` или `SecuritySafeCritical`. В противном случае при загрузке возникнет исключение <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="f0299-134">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="f0299-135">Это правило также применяется в том случае, если базовый и производный классы находятся в одной сборке.</span><span class="sxs-lookup"><span data-stu-id="f0299-135">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="f0299-136">`AllowPartiallyTrustedCallers` (только уровень 2): весь код по умолчанию является прозрачным.</span><span class="sxs-lookup"><span data-stu-id="f0299-136">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="f0299-137">Однако отдельные типы и члены могут иметь другие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f0299-137">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="f0299-138">В следующей таблице сравнивается поведение уровня сборки уровня 2 с уровнем 1.</span><span class="sxs-lookup"><span data-stu-id="f0299-138">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="f0299-139">Атрибут сборки</span><span class="sxs-lookup"><span data-stu-id="f0299-139">Assembly attribute</span></span>|<span data-ttu-id="f0299-140">Уровень 2</span><span class="sxs-lookup"><span data-stu-id="f0299-140">Level 2</span></span>|<span data-ttu-id="f0299-141">уровне 1</span><span class="sxs-lookup"><span data-stu-id="f0299-141">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="f0299-142">Частично доверенная сборка без атрибутов</span><span class="sxs-lookup"><span data-stu-id="f0299-142">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="f0299-143">Типы и члены по умолчанию являются прозрачными, но могут быть критическими или надежными с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f0299-143">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="f0299-144">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="f0299-144">All types and members are transparent.</span></span>|
|<span data-ttu-id="f0299-145">Атрибут не указан</span><span class="sxs-lookup"><span data-stu-id="f0299-145">No attribute</span></span>|<span data-ttu-id="f0299-146">Если атрибут не указан, то определение правил прозрачности выполняется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f0299-146">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="f0299-147">Все типы и члены являются критическими с точки зрения безопасности за исключением тех случаев, когда это нарушает правило наследования.</span><span class="sxs-lookup"><span data-stu-id="f0299-147">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="f0299-148">В сборке с полным доверием (в глобальном кэше сборок или в сборке, для которой полное доверие указано в домене `AppDomain`) все типы являются прозрачными, а члены — надежными с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f0299-148">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="f0299-149">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="f0299-149">All types and members are transparent.</span></span>|<span data-ttu-id="f0299-150">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="f0299-150">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="f0299-151">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="f0299-151">Not applicable.</span></span>|<span data-ttu-id="f0299-152">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="f0299-152">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="f0299-153">Код всех типов в этой сборке является критическим, а остальной код — прозрачным.</span><span class="sxs-lookup"><span data-stu-id="f0299-153">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="f0299-154">При переопределении виртуального или абстрактного метода или при реализации метода интерфейса следует явным образом пометить этот метод как `SecurityCritical` или `SecuritySafeCritical`.</span><span class="sxs-lookup"><span data-stu-id="f0299-154">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="f0299-155">Весь код по умолчанию является прозрачным.</span><span class="sxs-lookup"><span data-stu-id="f0299-155">All code defaults to transparent.</span></span> <span data-ttu-id="f0299-156">Однако отдельные типы и члены могут иметь другие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f0299-156">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="f0299-157">Заметки для типов и членов</span><span class="sxs-lookup"><span data-stu-id="f0299-157">Type and Member Annotation</span></span>

<span data-ttu-id="f0299-158">Атрибуты безопасности, которые применяются к типу, также применяются и к членам, которые представлены этим типом.</span><span class="sxs-lookup"><span data-stu-id="f0299-158">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="f0299-159">Однако они не применяются к виртуальным или абстрактным переопределениям базового класса, а также к реализациям интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f0299-159">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="f0299-160">Ниже перечислены правила, которые применяются к использованию атрибутов на уровне типов и членов.</span><span class="sxs-lookup"><span data-stu-id="f0299-160">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="f0299-161">`SecurityCritical`: тип или член является критическим и может быть вызван только кодом с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="f0299-161">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="f0299-162">Методы, представленные в критическом с точки зрения безопасности коде, также являются критическими.</span><span class="sxs-lookup"><span data-stu-id="f0299-162">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f0299-163">Виртуальные и абстрактные методы, представленные в базовых классах или интерфейсах и переопределяемые или реализуемые в критическом с точки зрения безопасности классе, по умолчанию являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="f0299-163">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="f0299-164">Их следует пометить как `SecuritySafeCritical` или `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="f0299-164">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="f0299-165">`SecuritySafeCritical`: тип или член является надежным с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f0299-165">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="f0299-166">В то же время этот тип или член может вызываться из прозрачного кода (с частичным доверием) и имеет те же возможности, что и любой другой критический код.</span><span class="sxs-lookup"><span data-stu-id="f0299-166">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="f0299-167">Код необходимо проверить на безопасность.</span><span class="sxs-lookup"><span data-stu-id="f0299-167">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="f0299-168">Схемы переопределения</span><span class="sxs-lookup"><span data-stu-id="f0299-168">Override Patterns</span></span>

<span data-ttu-id="f0299-169">В таблице ниже представлены разрешенные переопределения метода для прозрачности уровня 2.</span><span class="sxs-lookup"><span data-stu-id="f0299-169">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="f0299-170">Базовый виртуальный член или член интерфейса</span><span class="sxs-lookup"><span data-stu-id="f0299-170">Base virtual/interface member</span></span>|<span data-ttu-id="f0299-171">Переопределение или интерфейс</span><span class="sxs-lookup"><span data-stu-id="f0299-171">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="f0299-172">Правила наследования</span><span class="sxs-lookup"><span data-stu-id="f0299-172">Inheritance Rules</span></span>

<span data-ttu-id="f0299-173">В этом разделе коду `Transparent`, `Critical` и `SafeCritical` в зависимости от доступа и возможностей присваивается следующий порядок:</span><span class="sxs-lookup"><span data-stu-id="f0299-173">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="f0299-174">Правила для типов: по мере движения слева направо доступ становится более ограниченным.</span><span class="sxs-lookup"><span data-stu-id="f0299-174">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="f0299-175">Производные типы должны иметь как минимум те же ограничения, что и базовый тип.</span><span class="sxs-lookup"><span data-stu-id="f0299-175">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="f0299-176">Правила для методов: производные методы не могут изменять доступность из базового метода.</span><span class="sxs-lookup"><span data-stu-id="f0299-176">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="f0299-177">По умолчанию все производные методы без заметок являются методами `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="f0299-177">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="f0299-178">Типы, производные от критических, вызывают возникновение исключения, если переопределенный метод явным образом не помечен как `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="f0299-178">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="f0299-179">В таблице ниже показаны разрешенные схемы наследования типов.</span><span class="sxs-lookup"><span data-stu-id="f0299-179">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="f0299-180">Базовый класс</span><span class="sxs-lookup"><span data-stu-id="f0299-180">Base class</span></span>|<span data-ttu-id="f0299-181">Производный класс может быть</span><span class="sxs-lookup"><span data-stu-id="f0299-181">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="f0299-182">В таблице ниже показаны запрещенные схемы наследования типов.</span><span class="sxs-lookup"><span data-stu-id="f0299-182">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="f0299-183">Базовый класс</span><span class="sxs-lookup"><span data-stu-id="f0299-183">Base class</span></span>|<span data-ttu-id="f0299-184">Производный класс не может быть</span><span class="sxs-lookup"><span data-stu-id="f0299-184">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="f0299-185">В таблице ниже показаны разрешенные схемы наследования методов.</span><span class="sxs-lookup"><span data-stu-id="f0299-185">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="f0299-186">Базовый метод</span><span class="sxs-lookup"><span data-stu-id="f0299-186">Base method</span></span>|<span data-ttu-id="f0299-187">Производный метод может быть</span><span class="sxs-lookup"><span data-stu-id="f0299-187">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="f0299-188">В таблице ниже показаны запрещенные схемы наследования методов.</span><span class="sxs-lookup"><span data-stu-id="f0299-188">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="f0299-189">Базовый метод</span><span class="sxs-lookup"><span data-stu-id="f0299-189">Base method</span></span>|<span data-ttu-id="f0299-190">Производный метод не может быть</span><span class="sxs-lookup"><span data-stu-id="f0299-190">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="f0299-191">Эти правила наследования применяются к типам и членам уровня 2.</span><span class="sxs-lookup"><span data-stu-id="f0299-191">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="f0299-192">Типы в сборках уровня 1 могут наследоваться от критических с точки зрения безопасности типов и членов уровня 2.</span><span class="sxs-lookup"><span data-stu-id="f0299-192">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="f0299-193">Таким образом, типы и члены уровня 2 должны иметь различные требования к наследованию для наследуемых типов и членов уровня 1.</span><span class="sxs-lookup"><span data-stu-id="f0299-193">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="f0299-194">Дополнительные сведения и правила</span><span class="sxs-lookup"><span data-stu-id="f0299-194">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="f0299-195">Поддержка LinkDemand</span><span class="sxs-lookup"><span data-stu-id="f0299-195">LinkDemand Support</span></span>

<span data-ttu-id="f0299-196">Модель прозрачности уровня 2 заменяет <xref:System.Security.Permissions.SecurityAction.LinkDemand> атрибутом <xref:System.Security.SecurityCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f0299-196">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="f0299-197">В устаревшем коде (уровень 1) <xref:System.Security.Permissions.SecurityAction.LinkDemand> автоматически рассматривается как <xref:System.Security.Permissions.SecurityAction.Demand>.</span><span class="sxs-lookup"><span data-stu-id="f0299-197">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="f0299-198">Отражение</span><span class="sxs-lookup"><span data-stu-id="f0299-198">Reflection</span></span>

<span data-ttu-id="f0299-199">Вызов критического метода или чтение критического поля вызывает требование полного доверия (как при вызове закрытого метода или поля).</span><span class="sxs-lookup"><span data-stu-id="f0299-199">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="f0299-200">Таким образом, критический метод может вызываться только в коде с полным доверием, а не в коде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="f0299-200">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="f0299-201">В пространство имен <xref:System.Reflection> добавлены следующие свойства, позволяющие определить, является ли тип, метод или поле `SecurityCritical`, `SecuritySafeCritical` или `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> и <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0299-201">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="f0299-202">Используйте эти свойства, чтобы определить прозрачность с помощью отражения, вместо проверки присутствия атрибута.</span><span class="sxs-lookup"><span data-stu-id="f0299-202">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="f0299-203">Правила прозрачности достаточно сложны, и проверки существования атрибута может быть недостаточно.</span><span class="sxs-lookup"><span data-stu-id="f0299-203">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="f0299-204">`SafeCritical`Метод возвращает `true` для <xref:System.Type.IsSecurityCritical%2A> и <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> , поскольку `SafeCritical` действительно является критически важным (он имеет те же возможности, что и важный код, но он может быть вызван из прозрачного кода).</span><span class="sxs-lookup"><span data-stu-id="f0299-204">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="f0299-205">Динамические методы наследуют прозрачность модулей, к которым они присоединены. Они не наследуют прозрачность типа (если они присоединены к типу).</span><span class="sxs-lookup"><span data-stu-id="f0299-205">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="f0299-206">Пропуск проверки при полном доверии</span><span class="sxs-lookup"><span data-stu-id="f0299-206">Skip Verification in Full Trust</span></span>

<span data-ttu-id="f0299-207">Для прозрачных сборок с полным доверием проверку можно пропустить, установив свойство <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> равным `true` в атрибуте <xref:System.Security.SecurityRulesAttribute>:</span><span class="sxs-lookup"><span data-stu-id="f0299-207">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="f0299-208">Свойство <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> по умолчанию равно `false`, поэтому для пропуска проверки его нужно установить равным `true`.</span><span class="sxs-lookup"><span data-stu-id="f0299-208">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="f0299-209">Это следует делать только в целях оптимизации.</span><span class="sxs-lookup"><span data-stu-id="f0299-209">This should be done for optimization purposes only.</span></span> <span data-ttu-id="f0299-210">Необходимо убедиться, что прозрачный код в сборке может быть проверен с помощью `transparent` параметра в [средстве PEVerify](../tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f0299-210">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0299-211">См. также</span><span class="sxs-lookup"><span data-stu-id="f0299-211">See also</span></span>

- [<span data-ttu-id="f0299-212">Прозрачный с точки зрения безопасности код, уровень 1</span><span class="sxs-lookup"><span data-stu-id="f0299-212">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="f0299-213">Изменения системы безопасности</span><span class="sxs-lookup"><span data-stu-id="f0299-213">Security Changes</span></span>](/previous-versions/dotnet/framework/security/security-changes)
