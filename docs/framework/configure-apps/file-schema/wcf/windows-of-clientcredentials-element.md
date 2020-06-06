---
title: <windows> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399117"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="81d11-102">\<windows> элемента \<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="81d11-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="81d11-103">Определяет параметры учетных данных Windows, которые используются для представления клиента.</span><span class="sxs-lookup"><span data-stu-id="81d11-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a><span data-ttu-id="81d11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81d11-104">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81d11-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="81d11-105">Attributes and Elements</span></span>  
 <span data-ttu-id="81d11-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="81d11-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81d11-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="81d11-107">Attributes</span></span>  
  
|<span data-ttu-id="81d11-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="81d11-108">Attribute</span></span>|<span data-ttu-id="81d11-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="81d11-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="81d11-110">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="81d11-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="81d11-111">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="81d11-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="81d11-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="81d11-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="81d11-113">-Identification: сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="81d11-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="81d11-114">— Олицетворение. сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="81d11-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="81d11-115">-Делегирование. сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="81d11-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="81d11-116">— Анонимно: сервер не может олицетворять или опознать клиента.</span><span class="sxs-lookup"><span data-stu-id="81d11-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="81d11-117">-None: уровень олицетворения не назначен.</span><span class="sxs-lookup"><span data-stu-id="81d11-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="81d11-118">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="81d11-118">The default is Identification.</span></span> <span data-ttu-id="81d11-119">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="81d11-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="81d11-120">Если установить для данного свойства значение `true`, то проверка подлинности может понижаться до NTLM в том случае, если проверка Kerberos недоступна.</span><span class="sxs-lookup"><span data-stu-id="81d11-120">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="81d11-121">Если задать для этого свойства значение `false` Windows Communication Foundation (WCF), лучше будет создавать исключение, если используется NTLM.</span><span class="sxs-lookup"><span data-stu-id="81d11-121">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="81d11-122">Обратите внимание, что установка для данного свойства значения `false` не предотвращает отправки учетных данных NTLM по сети.</span><span class="sxs-lookup"><span data-stu-id="81d11-122">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81d11-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="81d11-123">Child Elements</span></span>  
 <span data-ttu-id="81d11-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="81d11-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81d11-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="81d11-125">Parent Elements</span></span>  
  
|<span data-ttu-id="81d11-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="81d11-126">Element</span></span>|<span data-ttu-id="81d11-127">Описание</span><span class="sxs-lookup"><span data-stu-id="81d11-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="81d11-128">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="81d11-128">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81d11-129">См. также</span><span class="sxs-lookup"><span data-stu-id="81d11-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="81d11-130">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="81d11-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="81d11-131">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="81d11-131">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="81d11-132">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="81d11-132">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
