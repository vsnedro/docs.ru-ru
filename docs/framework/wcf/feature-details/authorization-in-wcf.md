---
title: Авторизация в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: d67d64dcf0003de28775ac947f8b5f72d7c2ba2a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597635"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="3d305-102">Авторизация в WCF</span><span class="sxs-lookup"><span data-stu-id="3d305-102">Authorization in WCF</span></span>
<span data-ttu-id="3d305-103">Авторизация - процесс управления доступом и правами на ресурсы, например службы и файлы.</span><span class="sxs-lookup"><span data-stu-id="3d305-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="3d305-104">В подразделах этого раздела показано, как выполнить эту базовую задачу в Windows Communication Foundation (WCF) различными способами.</span><span class="sxs-lookup"><span data-stu-id="3d305-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d305-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3d305-105">In This Section</span></span>  
 [<span data-ttu-id="3d305-106">Механизмы управления доступом</span><span class="sxs-lookup"><span data-stu-id="3d305-106">Access Control Mechanisms</span></span>](access-control-mechanisms.md)  
 <span data-ttu-id="3d305-107">Краткий обзор механизмов авторизации в WCF и предлагаемых вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="3d305-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="3d305-108">Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="3d305-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="3d305-109">Показывает процесс ограничения доступа к сервису с помощью класса <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3d305-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="3d305-110">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="3d305-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="3d305-111">Пошаговые инструкции по настройке службы, позволяющие использовать функцию поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3d305-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="3d305-112">Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="3d305-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="3d305-113">ASP.NET может использовать диспетчер авторизации для управления авторизацией веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="3d305-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="3d305-114">WCF также может использовать сочетание ASP.NET/Authorization Manager для авторизации клиентов.</span><span class="sxs-lookup"><span data-stu-id="3d305-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="3d305-115">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="3d305-115">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="3d305-116">Объясняет основы использования инфраструктуры модели удостоверения для механизма авторизации на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="3d305-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="3d305-117">Делегирование и олицетворение</span><span class="sxs-lookup"><span data-stu-id="3d305-117">Delegation and Impersonation</span></span>](delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="3d305-118">Объясняет разницу между делегированием и олицетворением.</span><span class="sxs-lookup"><span data-stu-id="3d305-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3d305-119">Справочник</span><span class="sxs-lookup"><span data-stu-id="3d305-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="3d305-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3d305-120">Related Sections</span></span>  
 [<span data-ttu-id="3d305-121">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="3d305-121">Authentication</span></span>](authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d305-122">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="3d305-122">See also</span></span>

- [<span data-ttu-id="3d305-123">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="3d305-123">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="3d305-124">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3d305-124">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
