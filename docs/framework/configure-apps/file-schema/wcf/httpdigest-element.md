---
title: Элемент <httpDigest>
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 523df7d5847ba7003e60f3882183b50cb18f6b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202491"
---
# <a name="httpdigest-element"></a><span data-ttu-id="0aeae-102">Элемент \<httpDigest></span><span class="sxs-lookup"><span data-stu-id="0aeae-102">\<httpDigest> Element</span></span>

<span data-ttu-id="0aeae-103">Задает учетные данные, используемые для дайджест-проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="0aeae-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a><span data-ttu-id="0aeae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0aeae-104">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0aeae-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0aeae-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0aeae-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0aeae-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0aeae-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0aeae-107">Attributes</span></span>  
  
|<span data-ttu-id="0aeae-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0aeae-108">Attribute</span></span>|<span data-ttu-id="0aeae-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0aeae-109">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="0aeae-110">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="0aeae-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="0aeae-111">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="0aeae-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="0aeae-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="0aeae-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0aeae-113">-Identification: сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="0aeae-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="0aeae-114">— Олицетворение. сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="0aeae-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="0aeae-115">-Делегирование. сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="0aeae-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="0aeae-116">— Анонимно: сервер не может олицетворять или опознать клиента.</span><span class="sxs-lookup"><span data-stu-id="0aeae-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="0aeae-117">-None: уровень олицетворения не назначен.</span><span class="sxs-lookup"><span data-stu-id="0aeae-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="0aeae-118">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="0aeae-118">The default is Identification.</span></span> <span data-ttu-id="0aeae-119">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="0aeae-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0aeae-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0aeae-120">Child Elements</span></span>  

 <span data-ttu-id="0aeae-121">Нет</span><span class="sxs-lookup"><span data-stu-id="0aeae-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0aeae-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0aeae-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0aeae-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="0aeae-123">Element</span></span>|<span data-ttu-id="0aeae-124">Описание</span><span class="sxs-lookup"><span data-stu-id="0aeae-124">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="0aeae-125">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="0aeae-125">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aeae-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="0aeae-126">Remarks</span></span>  

 <span data-ttu-id="0aeae-127">Хэш-кода — это хэш, определяемый с помощью алгоритма и набора входных данных.</span><span class="sxs-lookup"><span data-stu-id="0aeae-127">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="0aeae-128">Структура проверки подлинности и проверяемый объект согласуют алгоритм и обмениваются данными, используемыми в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="0aeae-128">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="0aeae-129">Клиент может вычислить хэш и отправить его службе.</span><span class="sxs-lookup"><span data-stu-id="0aeae-129">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="0aeae-130">Служба также вычисляет хэш и сравнивает значения.</span><span class="sxs-lookup"><span data-stu-id="0aeae-130">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="0aeae-131">Совпадение значений подтверждает подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="0aeae-131">A match validates the client.</span></span>  
  
 <span data-ttu-id="0aeae-132">Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS.</span><span class="sxs-lookup"><span data-stu-id="0aeae-132">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="0aeae-133">Дополнительные сведения см. [в статье дайджест-проверка подлинности в IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="0aeae-133">For more information, see [Digest Authentication in IIS 6.0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aeae-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0aeae-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="0aeae-135">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="0aeae-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0aeae-136">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="0aeae-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0aeae-137">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0aeae-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0aeae-138">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0aeae-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
