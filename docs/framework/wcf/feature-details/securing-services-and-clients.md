---
title: Защита служб и клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: 713737b129771967958fddf44e9ef28583d49422
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554082"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="512da-102">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="512da-102">Securing Services and Clients</span></span>
<span data-ttu-id="512da-103">Сведения в этом разделе посвящены безопасности программирования в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="512da-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="512da-104">Обычно обеспечение безопасности включает выбор подходящей предоставляемой системой привязки, задание свойств элемента безопасности и задание свойств поведений службы, управляющих извлечением учетных данных для использования службой или клиентом.</span><span class="sxs-lookup"><span data-stu-id="512da-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="512da-105">Эти методы охватывают требования большинства пользователей для большинства сценариев, как показано в [типичных сценариях безопасности](common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="512da-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](common-security-scenarios.md).</span></span> <span data-ttu-id="512da-106">Если ваш сценарий требует больше возможностей, сначала ознакомьтесь [с возможностями безопасности с помощью пользовательских привязок](security-capabilities-with-custom-bindings.md). Если решение не очевидно, см. раздел [расширение безопасности](../extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="512da-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../extending/extending-security.md).</span></span> <span data-ttu-id="512da-107">При создании (или взаимодействии с) системой, использующей обширные утверждения, см. разделы в разделе [авторизация](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="512da-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="512da-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="512da-108">In This Section</span></span>  
 [<span data-ttu-id="512da-109">Программирование безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="512da-109">Programming WCF Security</span></span>](programming-wcf-security.md)  
 <span data-ttu-id="512da-110">Общие сведения о модели программирования, используемой для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="512da-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="512da-111">Общие сведения о безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="512da-111">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="512da-112">Общие сведения о защите сообщений на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="512da-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="512da-113">Безопасность сообщений</span><span class="sxs-lookup"><span data-stu-id="512da-113">Message Security</span></span>](message-security-in-wcf.md)  
 <span data-ttu-id="512da-114">Суммирует причины использования безопасности на уровне сообщений в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="512da-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="512da-115">Безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="512da-115">Secure Sessions</span></span>](secure-sessions.md)  
 <span data-ttu-id="512da-116">Обсуждение вопросов, необходимых при защите сеанса WCF.</span><span class="sxs-lookup"><span data-stu-id="512da-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="512da-117">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="512da-117">Working with Certificates</span></span>](working-with-certificates.md)  
 <span data-ttu-id="512da-118">Описание некоторых стандартных задач, которые требуется выполнять при использовании сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="512da-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="512da-119">Справочник</span><span class="sxs-lookup"><span data-stu-id="512da-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="512da-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="512da-120">Related Sections</span></span>  
 [<span data-ttu-id="512da-121">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="512da-121">Security Concepts</span></span>](security-concepts.md)  
  
 [<span data-ttu-id="512da-122">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="512da-122">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="512da-123">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="512da-123">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
 [<span data-ttu-id="512da-124">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="512da-124">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="512da-125">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="512da-125">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="512da-126">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="512da-126">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="512da-127">Авторизация</span><span class="sxs-lookup"><span data-stu-id="512da-127">Authorization</span></span>](authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="512da-128">См. также</span><span class="sxs-lookup"><span data-stu-id="512da-128">See also</span></span>

- [<span data-ttu-id="512da-129">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="512da-129">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- <span data-ttu-id="512da-130">[Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="512da-130">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
