---
title: Федерация и выданные маркеры
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: aeffc1e2a7b61dfd9406b9f06678064533ea61ec
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595509"
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="987ec-102">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="987ec-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="987ec-103">С помощью Windows Communication Foundation (WCF) можно создавать клиенты, которые безопасно обмениваются данными со службами, реализующими спецификации WS-Federation и WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="987ec-103">With Windows Communication Foundation (WCF), you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="987ec-104">В этих спецификациях XML, протокол SOAP и язык WSDL используются для предоставления механизмов, позволяющих производить проверку подлинности и авторизацию в различных областях доверия.</span><span class="sxs-lookup"><span data-stu-id="987ec-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="987ec-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="987ec-105">In This Section</span></span>  
 [<span data-ttu-id="987ec-106">Федерация</span><span class="sxs-lookup"><span data-stu-id="987ec-106">Federation</span></span>](federation.md)  
 <span data-ttu-id="987ec-107">Общие сведения о федерации.</span><span class="sxs-lookup"><span data-stu-id="987ec-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="987ec-108">Федерация и доверие</span><span class="sxs-lookup"><span data-stu-id="987ec-108">Federation and Trust</span></span>](federation-and-trust.md)  
 <span data-ttu-id="987ec-109">Список вопросов архитектуры, о которых необходимо помнить при создании федеративных служб или клиентов.</span><span class="sxs-lookup"><span data-stu-id="987ec-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="987ec-110">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="987ec-110">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)  
 <span data-ttu-id="987ec-111">Основные сведения о создании федеративного клиента с помощью WCF.</span><span class="sxs-lookup"><span data-stu-id="987ec-111">Describes the basics of creating a federated client with WCF.</span></span>  
  
 [<span data-ttu-id="987ec-112">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="987ec-112">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="987ec-113">Основные этапы создания федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="987ec-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="987ec-114">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="987ec-114">How to: Create a WSFederationHttpBinding</span></span>](how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="987ec-115">Порядок настройки клиентов и служб, использующих `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="987ec-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="987ec-116">Практическое руководство. Создание службы маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="987ec-116">How to: Create a Security Token Service</span></span>](how-to-create-a-security-token-service.md)  
 <span data-ttu-id="987ec-117">Этапы создания службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="987ec-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="987ec-118">Утверждения и маркеры языка SAML (Security Assertions Markup Language)</span><span class="sxs-lookup"><span data-stu-id="987ec-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](saml-tokens-and-claims.md)  
 <span data-ttu-id="987ec-119">Маркеры языка Security Assertions Markup Language (SAML), допускающие расширение и позволяющие создавать типы утверждений с широкими функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="987ec-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="987ec-120">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="987ec-120">How to: Configure a Local Issuer</span></span>](how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="987ec-121">Порядок создания локального издателя маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="987ec-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="987ec-122">Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="987ec-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="987ec-123">Порядок отключения безопасных сеансов в `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="987ec-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="987ec-124">Отключение безопасных сеансов необходимо при создании веб-фермы, требующей сеансы для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="987ec-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="987ec-125">Справочник</span><span class="sxs-lookup"><span data-stu-id="987ec-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="987ec-126">См. также</span><span class="sxs-lookup"><span data-stu-id="987ec-126">See also</span></span>

- [<span data-ttu-id="987ec-127">Авторизация</span><span class="sxs-lookup"><span data-stu-id="987ec-127">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="987ec-128">Пользовательские маркеры</span><span class="sxs-lookup"><span data-stu-id="987ec-128">Custom Tokens</span></span>](../extending/custom-tokens.md)
- <span data-ttu-id="987ec-129">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="987ec-129">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
