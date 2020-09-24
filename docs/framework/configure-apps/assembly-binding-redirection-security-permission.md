---
title: Разрешение безопасности перенаправления привязки сборок
description: Сведения о разрешениях безопасности, необходимых для явного перенаправления привязки сборок в файле конфигурации приложения в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: 2de2c50f5adb9e9fa36ea015ef498e9953c83005
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165225"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="5ecba-103">Разрешение безопасности перенаправления привязки сборок</span><span class="sxs-lookup"><span data-stu-id="5ecba-103">Assembly Binding Redirection Security Permission</span></span>

<span data-ttu-id="5ecba-104">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="5ecba-104">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="5ecba-105">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="5ecba-105">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="5ecba-106">Разрешение предоставляется путем установки <xref:System.Security.Permissions.SecurityPermissionFlag> флага для <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="5ecba-106">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="5ecba-107">По умолчанию управляемые сборки не имеют разрешений.</span><span class="sxs-lookup"><span data-stu-id="5ecba-107">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="5ecba-108">Разрешение безопасности предоставляется приложениям, выполняемым в зоне доверенной зоны (локального компьютера) и зоны интрасети.</span><span class="sxs-lookup"><span data-stu-id="5ecba-108">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="5ecba-109">Приложениям, выполняемым в зоне Интернета, строго запрещено выполнять перенаправление привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="5ecba-109">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="5ecba-110">Разрешение не требуется, если перенаправление сборок выполняется в файле политики издателя, который управляется издателем компонента, или в файле конфигурации компьютера, управляемом администратором.</span><span class="sxs-lookup"><span data-stu-id="5ecba-110">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="5ecba-111">Однако разрешение требуется для приложения, чтобы явно игнорировать политику издателя с помощью [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) элемента в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5ecba-111">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="5ecba-112">В следующей таблице показаны параметры безопасности по умолчанию для флага **BindingRedirects** .</span><span class="sxs-lookup"><span data-stu-id="5ecba-112">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="5ecba-113">Зона</span><span class="sxs-lookup"><span data-stu-id="5ecba-113">Zone</span></span>|<span data-ttu-id="5ecba-114">Параметр флага BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="5ecba-114">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="5ecba-115">Доверенная зона (локальный компьютер)</span><span class="sxs-lookup"><span data-stu-id="5ecba-115">Trusted Zone (local machine)</span></span>|<span data-ttu-id="5ecba-116">**ON**</span><span class="sxs-lookup"><span data-stu-id="5ecba-116">**ON**</span></span>|  
|<span data-ttu-id="5ecba-117">Зона интрасети</span><span class="sxs-lookup"><span data-stu-id="5ecba-117">Intranet Zone</span></span>|<span data-ttu-id="5ecba-118">**ON**</span><span class="sxs-lookup"><span data-stu-id="5ecba-118">**ON**</span></span>|  
|<span data-ttu-id="5ecba-119">Зона Интернета</span><span class="sxs-lookup"><span data-stu-id="5ecba-119">Internet Zone</span></span>|<span data-ttu-id="5ecba-120">**OFF**</span><span class="sxs-lookup"><span data-stu-id="5ecba-120">**OFF**</span></span>|  
|<span data-ttu-id="5ecba-121">Недоверенные зоны</span><span class="sxs-lookup"><span data-stu-id="5ecba-121">Untrusted zones</span></span>|<span data-ttu-id="5ecba-122">**OFF**</span><span class="sxs-lookup"><span data-stu-id="5ecba-122">**OFF**</span></span>|  
  
 <span data-ttu-id="5ecba-123">Администратор может изменить эти параметры безопасности для поддержки или ограничения конкретных сценариев на определенном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5ecba-123">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="5ecba-124">Нет средств для изменения значения флага **BindingRedirects** по умолчанию; Администратор должен вручную изменить файл Security.config на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="5ecba-124">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecba-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5ecba-125">See also</span></span>

- <span data-ttu-id="5ecba-126">[Файлы политики издателя и параллельное выполнение](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5ecba-126">[Publisher Policy Files and Side-by-Side Execution](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="5ecba-127">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="5ecba-127">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="5ecba-128">Параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="5ecba-128">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
