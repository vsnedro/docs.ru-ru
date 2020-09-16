---
title: Типовые сценарии безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: cfd29f8cae8ac362a5fa1709864dce4ae11b5af6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558892"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="35123-102">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="35123-102">Common Security Scenarios</span></span>
<span data-ttu-id="35123-103">В подразделах этого раздела рассматривается множество возможных конфигураций безопасности клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="35123-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="35123-104">Конфигурация зависит от ряда факторов:</span><span class="sxs-lookup"><span data-stu-id="35123-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="35123-105">например, находится ли служба или клиент в интрасети, или чем обеспечивается безопасность - Windows или транспортом (таким как HTTPS).</span><span class="sxs-lookup"><span data-stu-id="35123-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35123-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="35123-106">In This Section</span></span>  
 [<span data-ttu-id="35123-107">Незащищенные интернет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="35123-107">Internet Unsecured Client and Service</span></span>](internet-unsecured-client-and-service.md)  
 <span data-ttu-id="35123-108">Пример общедоступных, незащищенных клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="35123-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="35123-109">Незащищенные интранет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="35123-109">Intranet Unsecured Client and Service</span></span>](intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="35123-110">Служба Basic Windows Communication Foundation (WCF), разработанная для предоставления информации о защищенной частной сети приложению WCF.</span><span class="sxs-lookup"><span data-stu-id="35123-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="35123-111">Безопасность транспорта с обычной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="35123-111">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)  
 <span data-ttu-id="35123-112">Приложение, позволяющее клиентам входить в систему с использованием пользовательской проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="35123-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="35123-113">Безопасность транспорта с проверкой подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="35123-113">Transport Security with Windows Authentication</span></span>](transport-security-with-windows-authentication.md)  
 <span data-ttu-id="35123-114">Клиент и служба, защищенные механизмом безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="35123-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="35123-115">Безопасность транспорта с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="35123-115">Transport Security with an Anonymous Client</span></span>](transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="35123-116">Сценарий с использованием механизма безопасности транспорта (такого как HTTPS) для обеспечения конфиденциальности и целостности.</span><span class="sxs-lookup"><span data-stu-id="35123-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="35123-117">Безопасность транспорта с проверкой подлинности с использованием сертификатов</span><span class="sxs-lookup"><span data-stu-id="35123-117">Transport Security with Certificate Authentication</span></span>](transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="35123-118">Клиент и служба, защищенные сертификатом.</span><span class="sxs-lookup"><span data-stu-id="35123-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="35123-119">Безопасность сообщений с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="35123-119">Message Security with an Anonymous Client</span></span>](message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="35123-120">Показывает клиент и службу, защищенные с помощью безопасности сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="35123-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="35123-121">Безопасность сообщений при использовании клиентом учетных данных пользователя</span><span class="sxs-lookup"><span data-stu-id="35123-121">Message Security with a User Name Client</span></span>](message-security-with-a-user-name-client.md)  
 <span data-ttu-id="35123-122">Клиент - приложение Windows Forms, позволяющее клиентам входить в систему с использованием имени пользователя и пароля домена.</span><span class="sxs-lookup"><span data-stu-id="35123-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="35123-123">Безопасность сообщений при использовании клиентом сертификата</span><span class="sxs-lookup"><span data-stu-id="35123-123">Message Security with a Certificate Client</span></span>](message-security-with-a-certificate-client.md)  
 <span data-ttu-id="35123-124">Серверы имеют сертификаты и каждый клиент имеет сертификат.</span><span class="sxs-lookup"><span data-stu-id="35123-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="35123-125">Контекст безопасности устанавливается посредством согласования по протоколу TLS.</span><span class="sxs-lookup"><span data-stu-id="35123-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="35123-126">Безопасность сообщений с клиентом Windows</span><span class="sxs-lookup"><span data-stu-id="35123-126">Message Security with a Windows Client</span></span>](message-security-with-a-windows-client.md)  
 <span data-ttu-id="35123-127">Разновидность клиента с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="35123-127">A variation of the certificate client.</span></span> <span data-ttu-id="35123-128">Серверы имеют сертификаты и каждый клиент имеет сертификат.</span><span class="sxs-lookup"><span data-stu-id="35123-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="35123-129">Контекст безопасности устанавливается посредством согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="35123-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="35123-130">Безопасность сообщений с использованием клиента Windows без согласования учетных данных</span><span class="sxs-lookup"><span data-stu-id="35123-130">Message Security with a Windows Client without Credential Negotiation</span></span>](message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="35123-131">Клиент и служба, защищенные доменом Kerberos.</span><span class="sxs-lookup"><span data-stu-id="35123-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="35123-132">Безопасность сообщений с использованием взаимных сертификатов</span><span class="sxs-lookup"><span data-stu-id="35123-132">Message Security with Mutual Certificates</span></span>](message-security-with-mutual-certificates.md)  
 <span data-ttu-id="35123-133">Серверы имеют сертификаты и каждый клиент имеет сертификат.</span><span class="sxs-lookup"><span data-stu-id="35123-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="35123-134">Сертификат сервера распространяется вместе с приложением и доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="35123-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="35123-135">Безопасность сообщений с использованием выданных маркеров</span><span class="sxs-lookup"><span data-stu-id="35123-135">Message Security with Issued Tokens</span></span>](message-security-with-issued-tokens.md)  
 <span data-ttu-id="35123-136">Федеративная безопасность, позволяющая установить доверие между независимыми доменами.</span><span class="sxs-lookup"><span data-stu-id="35123-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="35123-137">Доверенная подсистема</span><span class="sxs-lookup"><span data-stu-id="35123-137">Trusted Subsystem</span></span>](trusted-subsystem.md)  
 <span data-ttu-id="35123-138">Клиент обращается к одной или нескольким веб-службам, распределенным по сети.</span><span class="sxs-lookup"><span data-stu-id="35123-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="35123-139">Веб-службы обращаются к дополнительным ресурсам (таким как базы данных или другие веб-службы), которые должны быть защищены.</span><span class="sxs-lookup"><span data-stu-id="35123-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="35123-140">Справочник</span><span class="sxs-lookup"><span data-stu-id="35123-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="35123-141">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="35123-141">Related Sections</span></span>  
 [<span data-ttu-id="35123-142">Авторизация</span><span class="sxs-lookup"><span data-stu-id="35123-142">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="35123-143">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="35123-143">Security Overview</span></span>](security-overview.md)  
  
 [<span data-ttu-id="35123-144">Безопасность</span><span class="sxs-lookup"><span data-stu-id="35123-144">Security</span></span>](security.md)  
  
 [<span data-ttu-id="35123-145">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="35123-145">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="35123-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="35123-146">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
 [<span data-ttu-id="35123-147">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="35123-147">Authentication</span></span>](authentication-in-wcf.md)  
  
 [<span data-ttu-id="35123-148">Авторизация</span><span class="sxs-lookup"><span data-stu-id="35123-148">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="35123-149">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="35123-149">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="35123-150">Аудит</span><span class="sxs-lookup"><span data-stu-id="35123-150">Auditing</span></span>](auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="35123-151">См. также</span><span class="sxs-lookup"><span data-stu-id="35123-151">See also</span></span>

- [<span data-ttu-id="35123-152">Руководство и рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="35123-152">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)
- <span data-ttu-id="35123-153">[Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="35123-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
