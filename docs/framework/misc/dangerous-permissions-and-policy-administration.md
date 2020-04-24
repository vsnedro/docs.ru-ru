---
title: Опасные разрешения и администрирование политик
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: 15d28ff7d11b5d15ce44d9ab1f56548256850ff8
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645762"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="bbb65-102">Опасные разрешения и администрирование политик</span><span class="sxs-lookup"><span data-stu-id="bbb65-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="bbb65-103">Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbb65-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="bbb65-104">Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="bbb65-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="bbb65-105">Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="bbb65-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bbb65-106">В рамках .NET Framework 4 произошли важные изменения в модели безопасности и терминологии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bbb65-106">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="bbb65-107">Для получения дополнительной информации об этих изменениях [см.](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)</span><span class="sxs-lookup"><span data-stu-id="bbb65-107">For more information about these changes, see [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="bbb65-108">Небезопасные разрешения приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bbb65-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="bbb65-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="bbb65-109">Permission</span></span>|<span data-ttu-id="bbb65-110">Потенциальный риск</span><span class="sxs-lookup"><span data-stu-id="bbb65-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="bbb65-111">Позволяет управляемому коду вызывать неуправляемый код, который часто небезопасен.</span><span class="sxs-lookup"><span data-stu-id="bbb65-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="bbb65-112">Без проверки код может что-либо сделать.</span><span class="sxs-lookup"><span data-stu-id="bbb65-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="bbb65-113">Непроверенное свидетельство может обмануть систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbb65-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="bbb65-114">Возможность изменять политику безопасности может отключить систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbb65-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="bbb65-115">Использование сериализации позволяет обойти механизмы специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="bbb65-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="bbb65-116">Подробные сведения см. в разделе [Безопасность и сериализация](security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="bbb65-116">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="bbb65-117">Возможность установки текущего участника может сбить с толку безопасность на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="bbb65-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="bbb65-118">Управление потоками представляет опасность, поскольку состояние безопасности связано с потоками.</span><span class="sxs-lookup"><span data-stu-id="bbb65-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="bbb65-119">Можно использовать закрытые члены для нарушения правил доступа.</span><span class="sxs-lookup"><span data-stu-id="bbb65-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbb65-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bbb65-120">See also</span></span>

- [<span data-ttu-id="bbb65-121">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="bbb65-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
