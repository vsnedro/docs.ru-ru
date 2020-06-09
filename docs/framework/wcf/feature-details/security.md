---
title: Безопасность Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 327fb509a5186a0b3f428efc2ddd7f983bcfa978
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595151"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="09fa2-102">Безопасность Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="09fa2-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="09fa2-103">В подразделах этого раздела описываются функции безопасности Windows Communication Foundation (WCF) и способы их использования для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="09fa2-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="09fa2-104">Дополнительные сведения о Windows Server AppFabric и безопасности см. в статье [модель безопасности для Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10)) .</span><span class="sxs-lookup"><span data-stu-id="09fa2-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09fa2-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="09fa2-105">In This Section</span></span>  
 [<span data-ttu-id="09fa2-106">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="09fa2-106">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="09fa2-107">Описание функций безопасности в WCF.</span><span class="sxs-lookup"><span data-stu-id="09fa2-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="09fa2-108">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="09fa2-108">Security Concepts</span></span>](security-concepts.md)  
 <span data-ttu-id="09fa2-109">Описывает основные термины и понятия, используемые в безопасности WCF.</span><span class="sxs-lookup"><span data-stu-id="09fa2-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="09fa2-110">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="09fa2-110">Common Security Scenarios</span></span>](common-security-scenarios.md)  
 <span data-ttu-id="09fa2-111">Описание сценариев и топологий, которые можно настроить с помощью WCF.</span><span class="sxs-lookup"><span data-stu-id="09fa2-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="09fa2-112">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="09fa2-112">Security Behaviors</span></span>](security-behaviors-in-wcf.md)  
 <span data-ttu-id="09fa2-113">Общие сведения о поведении WCF, которые оказывают влияние на безопасность, например на настройки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="09fa2-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="09fa2-114">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="09fa2-114">Bindings and Security</span></span>](bindings-and-security.md)  
 <span data-ttu-id="09fa2-115">Описание привязок с точки зрения безопасности, в том числе демонстрация создания настраиваемых привязок безопасности.</span><span class="sxs-lookup"><span data-stu-id="09fa2-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="09fa2-116">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="09fa2-116">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
 <span data-ttu-id="09fa2-117">Описывает, как защитить сообщения с помощью функций безопасности WCF.</span><span class="sxs-lookup"><span data-stu-id="09fa2-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="09fa2-118">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="09fa2-118">Authentication</span></span>](authentication-in-wcf.md)  
 <span data-ttu-id="09fa2-119">Примеры типичных задач, связанных с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="09fa2-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="09fa2-120">Авторизация</span><span class="sxs-lookup"><span data-stu-id="09fa2-120">Authorization</span></span>](authorization-in-wcf.md)  
 <span data-ttu-id="09fa2-121">Типичные сценарии авторизации с реализацией системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="09fa2-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="09fa2-122">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="09fa2-122">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
 <span data-ttu-id="09fa2-123">Основы федерации и принципы создания клиентов, взаимодействующих с федеративными серверами.</span><span class="sxs-lookup"><span data-stu-id="09fa2-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="09fa2-124">Частичное доверие</span><span class="sxs-lookup"><span data-stu-id="09fa2-124">Partial Trust</span></span>](partial-trust.md)  
 <span data-ttu-id="09fa2-125">Описывает, как выполнять частично доверенные сценарии и ограничения WCF при выполнении частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="09fa2-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="09fa2-126">Аудит</span><span class="sxs-lookup"><span data-stu-id="09fa2-126">Auditing</span></span>](auditing-security-events.md)  
 <span data-ttu-id="09fa2-127">Принципы аудита событий безопасности.</span><span class="sxs-lookup"><span data-stu-id="09fa2-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="09fa2-128">Руководство и рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="09fa2-128">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
 <span data-ttu-id="09fa2-129">Рекомендации по созданию безопасных приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="09fa2-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="09fa2-130">Справочник</span><span class="sxs-lookup"><span data-stu-id="09fa2-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="09fa2-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="09fa2-131">Related Sections</span></span>  
 [<span data-ttu-id="09fa2-132">Сведения о функции WCF</span><span class="sxs-lookup"><span data-stu-id="09fa2-132">WCF Feature Details</span></span>](index.md)  
  
 [<span data-ttu-id="09fa2-133">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="09fa2-133">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="09fa2-134">Учебник по начало работы</span><span class="sxs-lookup"><span data-stu-id="09fa2-134">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)  
  
 [<span data-ttu-id="09fa2-135">Обзор концепции</span><span class="sxs-lookup"><span data-stu-id="09fa2-135">Conceptual Overview</span></span>](../conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="09fa2-136">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="09fa2-136">See also</span></span>

- [<span data-ttu-id="09fa2-137">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="09fa2-137">Configuring Your Application</span></span>](../diagnostics/configuring-your-application.md)
