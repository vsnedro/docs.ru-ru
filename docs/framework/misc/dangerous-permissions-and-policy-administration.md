---
title: Опасные разрешения и администрирование политик
description: См. ссылки на различные опасные разрешения в .NET. Эти разрешения должны быть предоставлены только доверенному коду и только при необходимости.
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: 1d3fb53775a4d88f9372b582189a38e18376761a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855820"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="dc83b-104">Опасные разрешения и администрирование политик</span><span class="sxs-lookup"><span data-stu-id="dc83b-104">Dangerous Permissions and Policy Administration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="dc83b-105">Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc83b-105">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="dc83b-106">Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="dc83b-106">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="dc83b-107">Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="dc83b-107">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc83b-108">В .NET Framework 4 были внесены важные изменения в модель и терминологию безопасности .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc83b-108">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="dc83b-109">Дополнительные сведения об этих изменениях см. в разделе [изменения в системе безопасности](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="dc83b-109">For more information about these changes, see [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="dc83b-110">Небезопасные разрешения приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="dc83b-110">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="dc83b-111">Разрешение</span><span class="sxs-lookup"><span data-stu-id="dc83b-111">Permission</span></span>|<span data-ttu-id="dc83b-112">Потенциальный риск</span><span class="sxs-lookup"><span data-stu-id="dc83b-112">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="dc83b-113">Позволяет управляемому коду вызывать неуправляемый код, который часто небезопасен.</span><span class="sxs-lookup"><span data-stu-id="dc83b-113">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="dc83b-114">Без проверки код может что-либо сделать.</span><span class="sxs-lookup"><span data-stu-id="dc83b-114">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="dc83b-115">Непроверенное свидетельство может обмануть систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc83b-115">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="dc83b-116">Возможность изменять политику безопасности может отключить систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc83b-116">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="dc83b-117">Использование сериализации позволяет обойти механизмы специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="dc83b-117">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="dc83b-118">Подробные сведения см. в разделе [Безопасность и сериализация](security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="dc83b-118">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="dc83b-119">Возможность установки текущего участника может сбить с толку безопасность на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="dc83b-119">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="dc83b-120">Управление потоками представляет опасность, поскольку состояние безопасности связано с потоками.</span><span class="sxs-lookup"><span data-stu-id="dc83b-120">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="dc83b-121">Можно использовать закрытые члены для нарушения правил доступа.</span><span class="sxs-lookup"><span data-stu-id="dc83b-121">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc83b-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dc83b-122">See also</span></span>

- [<span data-ttu-id="dc83b-123">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="dc83b-123">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
