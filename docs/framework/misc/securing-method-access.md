---
title: Безопасность доступа к методам
description: Узнайте, как обеспечить безопасность доступа к методу для методов, которые не предназначены для общедоступного использования, но должны быть общедоступными.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
ms.openlocfilehash: f9b9bc00058aefc8f58facff43509e717967c2a7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555722"
---
# <a name="securing-method-access"></a><span data-ttu-id="ef9e1-103">Безопасность доступа к методам</span><span class="sxs-lookup"><span data-stu-id="ef9e1-103">Securing Method Access</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="ef9e1-104">Некоторые методы не подходят для вызова из произвольного ненадежного кода.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-104">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="ef9e1-105">С такими методами связан ряд угроз: метод может предоставить некие закрытые сведения; он может доверять всем переданным ему данным; он может не осуществлять проверку параметров; либо при передаче неверных параметров он может работать неправильно или выполнить опасную операцию.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-105">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="ef9e1-106">Необходимо отслеживать такие ситуации и предпринимать меры для защиты метода.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-106">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="ef9e1-107">В некоторых случаях может потребоваться ограничить методы, которые не предназначены для общего использования, но по-прежнему должны быть открытыми.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-107">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="ef9e1-108">Например, имеется интерфейс, который должен вызываться через собственные библиотеки DLL и поэтому должен быть открытым, но вы не хотите предоставлять к нему общий доступ, чтобы предотвратить его использование клиентами или не позволить вредоносному коду использовать точку входа в компонент.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-108">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="ef9e1-109">Еще одна распространенная причина ограничения метода, не предназначенного для общего использования (но которая должна быть общедоступной), заключается в том, чтобы не документировать и поддерживать, что может быть внутренним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-109">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be an internal interface.</span></span>  
  
 <span data-ttu-id="ef9e1-110">Управляемый код позволяет ограничить доступ к методу несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-110">Managed code offers several ways to restrict method access:</span></span>  
  
- <span data-ttu-id="ef9e1-111">Ограничить область доступа классом, сборкой или производным классом, если они являются доверенными.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-111">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="ef9e1-112">Это самый простой способ ограничить доступ к методу.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-112">This is the simplest way to limit method access.</span></span> <span data-ttu-id="ef9e1-113">Как правило, производные классы могут быть менее надежными, чем класс, от которого они наследуются, но в некоторых случаях они совместно используют удостоверение родительского класса.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-113">In general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="ef9e1-114">В частности, не следует вычислять доверие от ключевого слова `protected` , которое не обязательно используется в контексте безопасности.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-114">In particular, do not infer trust from the keyword `protected`, which is not necessarily used in the security context.</span></span>  
  
- <span data-ttu-id="ef9e1-115">Ограничьте доступ к методу для вызывающих объектов указанного удостоверения, по сути, любого конкретного [свидетельства](/previous-versions/dotnet/netframework-4.0/7y5x1hcd(v=vs.100)) (строгое имя, издатель, зона и т. д.), которые вы выбираете.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-115">Limit the method access to callers of a specified identity--essentially, any particular [evidence](/previous-versions/dotnet/netframework-4.0/7y5x1hcd(v=vs.100)) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
- <span data-ttu-id="ef9e1-116">Ограничить доступ к методу вызывающим объектам, имеющим выбранные вами разрешения.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-116">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="ef9e1-117">Аналогичным образом декларативная безопасность позволяет контролировать и наследование классов.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-117">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="ef9e1-118">**InheritanceDemand** можно использовать для следующих задач:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-118">You can use **InheritanceDemand** to do the following:</span></span>  
  
- <span data-ttu-id="ef9e1-119">Потребовать, чтобы производные классы имели заданное удостоверение или разрешение.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-119">Require derived classes to have a specified identity or permission.</span></span>  
  
- <span data-ttu-id="ef9e1-120">Потребовать, чтобы производные классы, переопределяющие некоторые методы, имели заданное удостоверение или разрешение.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-120">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="ef9e1-121">В следующем примере показано, как ограничить доступ к открытому классу, требуя, чтобы вызывающие объекты были подписаны определенным строгим именем.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-121">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="ef9e1-122">В этом примере используется <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> с **требованием** строгого имени.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-122">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="ef9e1-123">Сведения о том, как подписать сборку строгим именем в зависимости от задач, см. в разделе [Создание и использование сборок со строгими именами](../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="ef9e1-123">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../standard/assembly/create-use-strong-named.md).</span></span>  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="ef9e1-124">Исключение использования классов и членов ненадежным кодом</span><span class="sxs-lookup"><span data-stu-id="ef9e1-124">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="ef9e1-125">Используйте объявления, приведенные в этом разделе, чтобы запретить частично доверенному коду использовать определенные классы и методы, а также свойства и события.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-125">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="ef9e1-126">Применяя эти объявления к классу, вы применяете защиту ко всем его методам, свойствам и событиям.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-126">By applying these declarations to a class, you apply the protection to all its methods, properties, and events.</span></span> <span data-ttu-id="ef9e1-127">Однако для доступа к полям не применяется декларативная безопасность.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-127">However, field access is not affected by declarative security.</span></span> <span data-ttu-id="ef9e1-128">Также обратите внимание, что связывание помогает защититься от только непосредственных вызывающих объектов, и не может пресечь отвлекающие атаки.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-128">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef9e1-129">В .NET Framework 4 появилась новая модель прозрачности.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-129">A new transparency model has been introduced in the .NET Framework 4.</span></span> <span data-ttu-id="ef9e1-130">[Прозрачный для системы безопасности код, модель уровня 2,](security-transparent-code-level-2.md) определяет защищенный код с помощью <xref:System.Security.SecurityCriticalAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-130">The [Security-Transparent Code, Level 2](security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="ef9e1-131">Критичный в плане безопасности код требует полного доверия как к вызывающим, так и к наследующим объектам.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-131">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="ef9e1-132">Сборки, выполняющиеся в соответствии с правилами безопасности доступа кода из более ранних версий .NET Framework, могут вызывать сборки с уровнем 2.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-132">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="ef9e1-133">В этом случае критически важные для безопасности атрибуты считаются запросами связи для полного доверия.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-133">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="ef9e1-134">В сборках со строгими именами [требование LinkDemand](link-demands.md) применяется ко всем общедоступным методам, свойствам и событиям, чтобы ограничить их использование для полностью доверенных вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-134">In strong-named assemblies, a [LinkDemand](link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="ef9e1-135">Чтобы отключить эту возможность, необходимо применить атрибут <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-135">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="ef9e1-136">Таким образом, явное выделение классов для исключения ненадежных вызывающих объектов необходимо только для сборки без подписи или с этим атрибутом; эти объявления можно использовать для пометки подмножества типов, которые не предназначены для ненадежных вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-136">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="ef9e1-137">В следующих примерах показано, как осуществить запрет использования классов и членов ненадежным кодом.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-137">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="ef9e1-138">Для открытых незапечатанных классов:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-138">For public nonsealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="ef9e1-139">Для открытых запечатанных классов:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-139">For public sealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="ef9e1-140">Для открытых абстрактных классов:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-140">For public abstract classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 <span data-ttu-id="ef9e1-141">Для открытых виртуальных функций:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-141">For public virtual functions:</span></span>  
  
```vb  
Class Base1
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 <span data-ttu-id="ef9e1-142">Для открытых абстрактных функций:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-142">For public abstract functions:</span></span>  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 <span data-ttu-id="ef9e1-143">Для открытых переопределяемых функций в случае, когда базовый класс не требует полного доверия:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-143">For public override functions where the base class does not demand full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="ef9e1-144">Для открытых переопределяемых функций в случае, когда базовый класс требует полного доверия:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-144">For public override functions where the base class demands full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="ef9e1-145">Для открытых интерфейсов:</span><span class="sxs-lookup"><span data-stu-id="ef9e1-145">For public interfaces:</span></span>  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="ef9e1-146">Переопределение объявлений Virtual и Internal или Overloads Overridable Friend</span><span class="sxs-lookup"><span data-stu-id="ef9e1-146">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef9e1-147">В этом разделе приводится предупреждение о проблемах безопасности при объявлении метода как `virtual` и `internal` ( `Overloads` `Overridable` `Friend` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ef9e1-147">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads` `Overridable` `Friend` in Visual Basic).</span></span> <span data-ttu-id="ef9e1-148">Это предупреждение относится только к версиям .NET Framework 1,0 и 1,1, она не применима к более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-148">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="ef9e1-149">В .NET Framework версиях 1,0 и 1,1 необходимо учитывать особенности специальных возможностей системы типов при подтверждении того, что код недоступен для других сборок.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-149">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="ef9e1-150">Метод, объявленный как **виртуальный** и **внутренний** (**перегрузки, переопределяемые** в Visual Basic), может переопределять запись vtable родительского класса и может использоваться только в той же сборке, поскольку она является внутренней.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-150">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="ef9e1-151">Однако доступность для переопределения определяется ключевым словом **Virtual** , и его можно переопределить из другой сборки, если этот код имеет доступ к самому классу.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-151">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="ef9e1-152">Если возможность переопределения представляет проблему, используйте декларативную безопасность для ее исправления или удалите ключевое слово **Virtual** , если оно не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-152">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="ef9e1-153">Даже если языковой компилятор предотвращает эти переопределения с помощью ошибки компиляции, можно переопределить код, написанный с другими компиляторами.</span><span class="sxs-lookup"><span data-stu-id="ef9e1-153">Even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9e1-154">См. также</span><span class="sxs-lookup"><span data-stu-id="ef9e1-154">See also</span></span>

- [<span data-ttu-id="ef9e1-155">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="ef9e1-155">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
