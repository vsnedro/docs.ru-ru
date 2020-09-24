---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: ce8be6eea5469b099a368a0b62e791faa7e3cbfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156996"
---
# \<serviceCertificate>

<span data-ttu-id="e9db7-101">Настраивает сертификат X. 509, используемый для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="e9db7-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="e9db7-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9db7-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9db7-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9db7-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e9db7-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e9db7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9db7-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9db7-105">Attributes</span></span>  

 <span data-ttu-id="e9db7-106">Нет</span><span class="sxs-lookup"><span data-stu-id="e9db7-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9db7-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9db7-107">Child Elements</span></span>  
  
|<span data-ttu-id="e9db7-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9db7-108">Element</span></span>|<span data-ttu-id="e9db7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e9db7-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="e9db7-110">Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e9db7-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9db7-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9db7-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e9db7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9db7-112">Element</span></span>|<span data-ttu-id="e9db7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e9db7-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="e9db7-114">Содержит параметры, которые настраивают свойства <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="e9db7-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e9db7-115">Пример</span><span class="sxs-lookup"><span data-stu-id="e9db7-115">Example</span></span>  

 <span data-ttu-id="e9db7-116">В следующем коде XML показано использование \<serviceCertificate> элемента.</span><span class="sxs-lookup"><span data-stu-id="e9db7-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="e9db7-117">XML взят из `CustomToken` примера.</span><span class="sxs-lookup"><span data-stu-id="e9db7-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
