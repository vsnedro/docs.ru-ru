---
title: Разрешение безопасности перенаправления привязки сборок
description: Сведения о разрешениях безопасности, необходимых для явного перенаправления привязки сборок в файле конфигурации приложения в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: a8596bcac4efb0aea07efcfde6726d8bbf148c24
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105095"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="166da-103">Разрешение безопасности перенаправления привязки сборок</span><span class="sxs-lookup"><span data-stu-id="166da-103">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="166da-104">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="166da-104">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="166da-105">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="166da-105">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="166da-106">Разрешение предоставляется путем установки <xref:System.Security.Permissions.SecurityPermissionFlag> флага для <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="166da-106">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="166da-107">По умолчанию управляемые сборки не имеют разрешений.</span><span class="sxs-lookup"><span data-stu-id="166da-107">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="166da-108">Разрешение безопасности предоставляется приложениям, выполняемым в зоне доверенной зоны (локального компьютера) и зоны интрасети.</span><span class="sxs-lookup"><span data-stu-id="166da-108">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="166da-109">Приложениям, выполняемым в зоне Интернета, строго запрещено выполнять перенаправление привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="166da-109">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="166da-110">Разрешение не требуется, если перенаправление сборок выполняется в файле политики издателя, который управляется издателем компонента, или в файле конфигурации компьютера, управляемом администратором.</span><span class="sxs-lookup"><span data-stu-id="166da-110">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="166da-111">Однако разрешение требуется для приложения, чтобы явно игнорировать политику издателя с помощью [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) элемента в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="166da-111">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="166da-112">В следующей таблице показаны параметры безопасности по умолчанию для флага **BindingRedirects** .</span><span class="sxs-lookup"><span data-stu-id="166da-112">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="166da-113">Зона</span><span class="sxs-lookup"><span data-stu-id="166da-113">Zone</span></span>|<span data-ttu-id="166da-114">Параметр флага BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="166da-114">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="166da-115">Доверенная зона (локальный компьютер)</span><span class="sxs-lookup"><span data-stu-id="166da-115">Trusted Zone (local machine)</span></span>|<span data-ttu-id="166da-116">**ON**</span><span class="sxs-lookup"><span data-stu-id="166da-116">**ON**</span></span>|  
|<span data-ttu-id="166da-117">Зона интрасети</span><span class="sxs-lookup"><span data-stu-id="166da-117">Intranet Zone</span></span>|<span data-ttu-id="166da-118">**ON**</span><span class="sxs-lookup"><span data-stu-id="166da-118">**ON**</span></span>|  
|<span data-ttu-id="166da-119">Зона Интернета</span><span class="sxs-lookup"><span data-stu-id="166da-119">Internet Zone</span></span>|<span data-ttu-id="166da-120">**OFF**</span><span class="sxs-lookup"><span data-stu-id="166da-120">**OFF**</span></span>|  
|<span data-ttu-id="166da-121">Недоверенные зоны</span><span class="sxs-lookup"><span data-stu-id="166da-121">Untrusted zones</span></span>|<span data-ttu-id="166da-122">**OFF**</span><span class="sxs-lookup"><span data-stu-id="166da-122">**OFF**</span></span>|  
  
 <span data-ttu-id="166da-123">Администратор может изменить эти параметры безопасности для поддержки или ограничения конкретных сценариев на определенном компьютере.</span><span class="sxs-lookup"><span data-stu-id="166da-123">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="166da-124">Нет средств для изменения значения флага **BindingRedirects** по умолчанию; Администратор должен вручную изменить файл Security.config на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="166da-124">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166da-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="166da-125">See also</span></span>

- <span data-ttu-id="166da-126">[Файлы политики издателя и параллельное выполнение](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="166da-126">[Publisher Policy Files and Side-by-Side Execution](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="166da-127">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="166da-127">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="166da-128">Параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="166da-128">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
